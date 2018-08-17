---
layout: post
title: Call ,  Apply and Bind
---

Call ,  Apply methods inherent to all functions allow you to execute any function in any desired context. This makes for incredibly powerful capabilities. The call function requires the arguments to be listed explicitly while the apply function allows you to provide the arguments as an array:

{% highlight js %}
function user(firstName, lastName, age) {
    // do something 
}

user.call(window, 'John', 'Doe', 30);
user.apply(window, ['John', 'Doe', 30]);
{% endhighlight %}

The result of both calls is exactly the same, the user function is invoked in the context of the window and provided the same three arguments.

>To use the call or apply function, you just need to call it on the function instead of invoking the function using a pair of parenthesis and pass the context as the first argument. 

Example 2:
{% highlight js %}
function hello() {
    // do something...
}

hello(); // the way you usually call it
hello.call(context); // here you can pass the context(value of this) as the first argument
hello.apply(context); // here you can pass the context(value of this) as the first argument
{% endhighlight %}

Example 3:
{% highlight js %}
function introduce(name, interest) {
    console.log('Hi! I\'m '+ name +' and I like '+ interest +'.');
    console.log('The value of this is '+ this +'.')
}

introduce('Hammad', 'Coding'); // the way you usually call it
introduce.call(window, 'Batman', 'to save Gotham'); // pass the arguments one by one after the contextt
introduce.apply('Hi', ['Bruce Wayne', 'businesses']); // pass the arguments in an array after the context

// Output:
// Hi! I'm Hammad and I like Coding.
// The value of this is [object Window].
// Hi! I'm Batman and I like to save Gotham.
// The value of this is [object Window].
// Hi! I'm Bruce Wayne and I like businesses.
// The value of this is Hi.
{% endhighlight %}

##Bind :
Unlike Call and Apply, Bind doesn't itself call the function, it can only be used to bind the value of context and other arguments before calling the function. Using Bind in one of the examples from above:

Example :
{% highlight js %}
(function introduce(name, interest) {
    console.log('Hi! I\'m '+ name +' and I like '+ interest +'.');
    console.log('The value of this is '+ this +'.')
}).bind(window, 'Hammad', 'Cosmology')();

// logs:
// Hi! I'm Hammad and I like Cosmology.
// The value of this is [object Window].
{% endhighlight %}