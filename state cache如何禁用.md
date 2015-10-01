## ionic state 缓存刷新问题

[同样问题提问](http://ionichina.com/topic/55363ffa9ee76e05064d4b0b)

解决方案：
在`$stateProvider`中定义路由的时候，指定其cache为true或者false

例如在state provider中禁用缓存

```
$stateProvider.state('myState', {
   cache: false,
   url : '/myUrl',
   templateUrl : 'my-template.html'
})
```

至于说禁用全局缓存
```
$ionicConfigProvider.views.maxCache(0);
```
我没有试过，不过有的state页面还是需要缓存的，不建议采用。
