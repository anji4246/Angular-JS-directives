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
