# Angular-JS-directives

What is Directive?
In Angular, Directives are markers on DOM elements (attributes, elements, css class names and comments) that attach special behaviour to DOM elements or even transform the elements

In simple words, directives extends the HTML capabilities to do new things


angular.module('myApp', [])
.directive('directive name', function() {
  return {
    restrict: String,
    priority: Number,
    terminal: Boolean,
    template: String or Template Function:
      function(tElement, tAttrs) (...},
    templateUrl: String,
    replace: Boolean or String,
    scope: Boolean or Object,
    transclude: Boolean,
    controller: String or
      function(scope, element, attrs, transclude, otherInjectables) { ... },
    controllerAs: String,
    require: String,
    link: function(scope, iElement, iAttrs) { ... },
    compile:  // return an Object OR the link function
              // as in below:
      function(tElement, tAttrs, transclude) {
        return {
          pre: function(scope, iElement, iAttrs, controller) { ... },
          post: function(scope, iElement, iAttrs, controller) { ... }
        }
        // or
        return function postLink(...) { ... }
    }
  };
});


Directive Method takes 2 parameters
1. name (string)
2. a Factory function

angular.module('myApp', [])
.directive('myDirective', function() {
  // A directive definition object
  return {
    // directive definition is defined via options
    // which we'll override here
  };
});

We can also return a function instead of an object to handle this directive definition, but it is best practice to return an object as we’ve done above. 

When Angular bootstraps our app, it will register the returned object by the name provided as a string via the first argument. The Angular compiler parses the DOM of our main HTML document looking for elements, attributes, comments, or class names using that name when looking for these directives. When it finds one that it knows about, it uses the directive definition to place the DOM element on the page.
