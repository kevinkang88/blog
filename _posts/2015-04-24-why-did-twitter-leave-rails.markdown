---
layout: post
title:  "Why Did Twitter Move From Rails"
date:   2014-04-23 14:34:25
categories: misc
tags: misc
<!-- image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg -->
---
It is worth while to go over how Javascript delay mechanism behaves inside the loop since it may output unexpected results if not understood correctly. Let me break this down using simple examples.
If I were to produce delayed results in Ruby within a loop, it would be like below.

{% highlight ruby %}
def print_nums_after_one_sec
  5.times do |i|
    print i 
    sleep(1)
  end
end
print_nums_after_one_sec
#=> prints 012345 1second from each other to STDOUT.
{% endhighlight %}

So in Javascript it would be natural to write as below to produce similar results.

{% highlight js %}

function printNumsAfterOneSec(){
  for(var i=0; i<5; i++){
    setTimeout(function(){console.log(i)},i*1000)     
  }
}
printNumsAfterOneSec(); 
//=> prints 666666 1second from each other in Console.

{% endhighlight %}

It is displaying results at the right time but with wrong numbers. This is because for loop has already gone through the cycle and is passing in 6 inside of the anonymous function in the first parameter of setTimeout. In order to solve this problem, you must wrap the anonymous function inside another and immediately invoke it with  'i' like so. 

{% highlight js %}

function printNumsAfterOneSec(){
  for(var i=0; i<6; i++){
    setTimeout(function(x){return function(){console.log(x)}}(i),i*1000)     
  }
}
printNumsAfterOneSec(); 
//=> prints 012345 1second from each other in Console.

{% endhighlight %}

Easy way to remember this is that in order to utilize the increments in an ongoing loop, it cannot be hidden inside the function, because it will be referenced after it is done looping around.