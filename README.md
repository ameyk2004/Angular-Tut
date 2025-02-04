# AngularJS Notes

## Introduction

- AngularJS uses `ngRoute` or `ui-router` to enable smooth navigation within the app without reloading the page.
- JavaScript framework, suitable for SPA (Single Page Applications), developed by Google.
- It uses the MVC architecture.

### Connecting to AngularJS

- We use a `<script>` tag to include AngularJS.
- AngularJS can be loaded from an external CDN (Content Delivery Network).
- It is hosted on Google's AJAX Libraries API.
- Use the minified version (`angular.min.js`) for faster loading by removing comments and unnecessary spaces.

## What Happens When This Script is Loaded?

- Defines a global `angular` object, which provides access to all AngularJS features.
- Enables AngularJS directives (`ng-app`, `ng-model`, `ng-controller`, etc.) to work in the HTML page.

## Angular Directives

### 1. `ng-app` (Next Generation)

- Marks the beginning of an AngularJS-controlled section in an HTML document.
- Without `ng-app`, AngularJS features (like binding and controllers) won't work.
- Example:

```html
<body ng-app="myApp">
```

### 2. `ng-model`

- The `ng-model` directive binds an HTML input field to a variable in AngularJS.
- Enables two-way binding (when the variable changes, the input field updates and vice versa).

### 3. `ng-bind`

- The `ng-bind` directive binds a variable to an HTML element (one-way binding).

### More Directives:

1. `ng-repeat`
2. `ng-click`
3. `ng-if`
4. `ng-init`

## Expressions (Dynamic Content Rendering)

### How Expressions Work:

- Expressions can contain variables, perform operations, and access data like arrays or objects.
- AngularJS evaluates the expression and outputs the result wherever it's written in the HTML.

## AngularJS Routing

AngularJS provides a powerful routing mechanism for navigating between different views or pages in a Single Page Application (SPA).

### Steps to Set Up Routing:

#### 1. Include AngularJS Route Script:

For routing, you need to include the `ngRoute` module.
Example:

```html
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.6.9/angular-route.min.js"></script>
```

#### 2. Configure the Routes:

Use the `$routeProvider` to define different routes for the application.
Example:

```javascript
var app = angular.module('myApp', ['ngRoute']);

app.config(function($routeProvider) {
    $routeProvider
        .when('/home', {
            templateUrl: 'home.html',
            controller: 'homeController'
        })
        .when('/about', {
            templateUrl: 'about.html',
            controller: 'aboutController'
        })
        .otherwise({
            redirectTo: '/home'
        });
});
```

#### 3. Create Views:

You need to create separate HTML views (`home.html`, `about.html`, etc.) for each route.

#### 4. Navigation:

Use AngularJS's `ng-view` directive to display the routed view.
Example:

```html
<div ng-view></div>
```
