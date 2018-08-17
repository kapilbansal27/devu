---
layout: post
title: Javascript this, self and .bind(this)
---

Function binding is probably your least concern when beginning with JavaScript, but when you realize that you need a solution to the problem of how to keep the context of “this” within another function.

1.  Using var self = this;


 then you might not realize that what you actually need is Function.prototype.bind().