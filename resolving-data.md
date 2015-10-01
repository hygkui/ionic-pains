## Resolving Data the Right Way
[see this document](http://learn.ionicframework.com/formulas/data-the-right-way/)

通过使用resolve，可以在控制器之外处理promise，精简其代码，并将其逻辑抽象提升到路由层。

an example:
```
var app = angular.module('ionicApp', ['ionic'])

app.config(function($stateProvider, $urlRouterProvider) {
  $urlRouterProvider.otherwise('/')

  $stateProvider.state('root', {
    url: '/',
    template: '{{itemCtrl.item.name}}',
    controller: 'ItemCtrl as itemCtrl',
    resolve: {
      item: function(ItemsService) {
        return ItemsService.getItem()
      }
    }
  })
})

app.service('ItemsService', function($q) {
  return {
    getItem: function() {
      var dfd = $q.defer()

      setTimeout(function() {
        dfd.resolve({
          name: 'Mittens Cat'
        })
      }, 2000)

      return dfd.promise
    }
  }
})

app.controller('ItemCtrl', function(item) {
  this.item = item
})
```
