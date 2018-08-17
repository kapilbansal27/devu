---
layout: post
title: Java Script Closure with Real Time Examples?
---

Accessing variables outside of the immediate lexical scope creates a closure. In other words, a closure is formed when a nested function is defined inside of another function, allowing access to the outer functions variables. Returning the nested function allows you to maintain access to the local variables, arguments, and inner function declarations of its outer function. This encapsulation allows us to hide and preserve the execution context from outside scopes while exposing a public interface and thus is subject to further manipulation. A simple example of this looks like the following:

{% highlight js %}
function foo() {
    var localVariable = 'private variable';
    return function() {
        return localVariable;
    }
}

var getLocalVariable = foo();
getLocalVariable() // "private variable"
{% endhighlight %}


A closure can not only access the variables defined in its outer function but also the arguments of the outer function.

A closure can also access the variables of its outer function even after the function has returned. This allows the returned function to maintain access to all the resources of the outer function.

When you return an inner function from a function, that returned function will not be called when you try to call the outer function. You must first save the invocation of the outer function in a separate variable and then call the variable as a function. Consider this example:

{% highlight js %}
function greet() {
    name = 'Hammad';
    return function () {
        console.log('Hi ' + name);
    }
}

greet(); // nothing happens, no errors

// the returned function from greet() gets saved in greetLetter
greetLetter = greet();

 // calling greetLetter calls the returned function from the greet() function
greetLetter(); // logs 'Hi Hammad'
{% endhighlight %}

The key thing to note here is that greetLetter function can access the name variable of the greet function even after it has been returned.

The Module Pattern :
One of the most popular types of closures is what is widely known as the module pattern; it allows you to emulate public, private, and privileged members:

{% highlight js %}
var Module = (function() {
    function privateMethod() {
        // do something
    }

    return {
        publicMethod: function() {
            // can call privateMethod();
        }
    };
})();
Module.publicMethod(); // works
Module.privateMethod(); // Uncaught ReferenceError: privateMethod is not defined
{% endhighlight %}

Immediately-Invoked Function Expression (IIFE):
Another type of closure is what is called an immediately-invoked function expression (IIFE) which is nothing more than a self-invoked anonymous function executed in the context of the window:

The value of this is set window. This exposes a single global interface to interact with.

This is how it looks:
{% highlight js %}
(function(window) {
    // do anything
})(this); 
{% endhighlight %}
 
