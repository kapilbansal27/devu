---
layout: post
title: Scope vs Context
---

Scope is a set of rules which defines from where and how the variable could be accessed. Javascript has a lexical scope which means that scope is based on where functions are declared. It is defined during the compilation time. 

>In other words, scope pertains to the variable access of a function when it is invoked and is unique to each invocation.  

Executional context refer to where and how the function was invoked and is created during the execution time. Context has nothing to do with the lexical scope. 
Context is always the value of the this keyword which is a reference to the object that “owns” the currently executing code.

>Scope refers to the visibility of variables and context refers to the value of this in the same scope. 

OR

>Fundamentally, scope is function-based while context is object-based. 

**Execution Context**:- The word context in Execution Context refers to scope and not context. 
JavaScript is a single-threaded language so it can only execute a single task at a time. The rest of the tasks are queued in the Execution Context. As I told you earlier that when the JavaScript interpreter starts to execute your code, the context (scope) is by default set to be global. This global context is appended to your execution context which is actually the first context that starts the execution context.
After that, each function call (invocation) would append its context to the execution context. The same thing happens when an another function is called inside that function or somewhere else.

Each function creates its own execution context.
Once the browser is done with the code in that context, that context will then be popped off from the execution context and the state of the current context in the execution context will be transferred to the parent context. The browser always executes the execution context that is at the top of the execution stack (which is actually the innermost level of scope in your code).

<div class="message">There can only be one global context but any number of function contexts.</div>

**Lexical Scope** :  Lexical Scope means that in a nested group of functions, the inner functions have access to the variables and other resources of their parent scope. This means that the child functions are lexically bound to the execution context of their parents. Lexical scope is sometimes also referred to as Static Scope.


What is “this” Context : Link to another Blog





