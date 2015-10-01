check this:

```
$stateProvider
  .state('todos', {
    url: '/todos',
    controller: 'TodosCtrl',
    templateUrl: 'todos.html',
    resolve: {
      todos: function(TodosService) {
        return TodosService.getTodos()
      }
    }
  })
  .state('todo', {
    url: '/todos/:todoId',
    controller: 'TodoCtrl',
    templateUrl: 'todo.html',
    resolve: {
      todo: function($stateParams, TodosService) {
        return TodosService.getTodo($stateParams.todoId)
      }
    }
  })
})
```

then

```
app.controller('TodosCtrl', function($scope, todos) {
  $scope.todos = todos
})

app.controller('TodoCtrl', function($scope, todo) {
  $scope.todo = todo
})
```

DT;LR;
