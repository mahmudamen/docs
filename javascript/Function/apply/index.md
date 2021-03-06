---
title: 'apply'
attributions:
  - 'Microsoft Developer Network: [Article](http://msdn.microsoft.com/en-us/library/ie/4zc42wh1(v=vs.94).aspx)'
compatibility:
  feature: apply
  topic: javascript
readiness: 'Ready to Use'
summary: 'Calls the function, substituting the specified object for the this value of the function, and the specified array for the arguments of the function.'
tags:
  - JS_Basic
uri: javascript/Function/apply

---
## Summary

Calls the function, substituting the specified object for the this value of the function, and the specified array for the arguments of the function.

## Syntax

    apply([ thisObj [, argArray ]])

**thisObj**
:   Optional. The object to be used as the this object.

**argArray**
:   Optional. A set of arguments to be passed to the function.

## Examples

The following code shows how to use the apply method.

``` js
function callMe(arg1, arg2){
     var s = "";

     s += "this value: " + this;
     s += "<br />";
     for (i in callMe.arguments) {
         s += "arguments: " + callMe.arguments[i];
         s += "<br />";
     }
     return s;
 }

 document.write("Original function: <br/>");
 document.write(callMe(1, 2));
 document.write("<br/>");

 document.write("Function called with apply: <br/>");
 document.write(callMe.apply(3, [ 4, 5 ]));

 // Output:
 // Original function:
 // this value: [object Window]
 // arguments: 1
 // arguments: 2

 // Function called with apply:
 // this value: 3
 // arguments: 4
 // arguments: 5
```

## Remarks

If argArray is not a valid object, then an "Object expected" error occurs.

If neither argArray nor thisObj are supplied, the original this object is used as thisObj and no arguments are passed.

## See also

### Other articles

-   [Function Object](/javascript/Function)

