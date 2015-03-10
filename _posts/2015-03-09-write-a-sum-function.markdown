---
layout: post
title:  "Write a sum function"
date:   2014-03-09 21:17:55
categories: misc
tags: algorithm
---

I decided to blog about algorithm questions to be critical about my thought process while solving these problems. I am allowing my self to solve with any language even pseudo code to focus more on the correct thinking process, rather than syntax. Today we ll start with something simple.

Write code to sum 2 integer without using a+b, you have to use either ++ or --.(*think of negative numbers as well)

My final answer came out to be .. 

{% highlight js %}

function add(a,b){
  if(b < 0){
    for(var i = -1 ; i >= b ; i--){a--;}
  }else if(b > 0){
    for(var i = 1 ; i <= b ; i++){a++;}
  }
  return a ; 
};

print(add(3,2)) ; 
print(add(2,3)) ; 
print(add(-2,3)) ; 
print(add(2,-3)) ; 
print(add(0,-3)) ; 
print(add(100,1000))  ; 

{% endhighlight %}


I started off by focusing on the case where b is greater than 0. What I missed here that would have been better was starting off by writing all the tests for various cases, in this case when b is 0 , greater than 0 , and less than 0. I finished this question fairly quickly and got all the tests to pass but my method of approaching the problem could have been better.

More elegant solution could be ..

{% highlight js %}

function sum(a, b) {
  while(a > 0) { --a; ++b };
  while(a < 0) { ++a; --b };
  return b;
}

{% endhighlight %}

writing code that is readable and easy to understand is something I need to focus on so that in the future as my code gets more advanced it should still stay readable thus elegant. 