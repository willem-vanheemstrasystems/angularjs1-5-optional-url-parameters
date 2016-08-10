# angularjs1-5-optional-url-parameters
AngularJS 1.5 Optional URL parameters

Based on 'Optional URL Parameters' at https://www.youtube.com/watch?v=P0K3nEt-xAo&list=PL6n9fhu94yhWKHkcL7RJmmXyxkuFB3KSl&index=40

#Optional URL Parameters

Using the ```$location``` service and a custom method within the student controller, called 'searchStudent'.

```javascript
[...]
    .controller("studentsCtrl", function($http, $route, $location) {

        var vm = this;

        vm.searchStudent = function() {
            if(vm.name) {
                $location.url("/studentsSearch/" + vm.name);
            }
            else {
                $location.url("/studentsSearch";
            }
        }

        [...]
```

To make a URL parameter optional add a question mark (?) at the end of it

```javascript
    [...]
    .when("/studentsSearch/:name?", {
        templateUrl: "templates/studentsSearch.html",
        controller: "studentsSearchCtrl",
        controllerAs: "ctrl"
    })
    [...]
```


See script.js, index.html and styles.css how to implement this.