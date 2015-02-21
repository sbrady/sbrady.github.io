---
layout: post
title:  "The evolution of a FizzBuzz"
date:   2015-02-20 01:01:15
categories: FizzBuzz Go Golang
---

I recently read that the classic FizzBuzz is still often used in job interviews. I have to admit that I had to look up
exactly what, the "FizzBuzz" problem was. It does seems like a reasonable way to gauge if a developer has some knowledge 
of basic control structures and operations etc. So played with it a bit. When I compared my solution too others,
I realised that I naturally attempted to apply [Domain-driven design](http://en.wikipedia.org/wiki/Domain-driven_design) and
[SOLID](http://en.wikipedia.org/wiki/Domain-driven_design). (see below)
{% gist sbrady/cc4d973346627b804f2c 1standard_fizzBuzz.go %}
Here I have functions such as `getFizz` etc in attempt to use the same language, as was given. Also I know I could have a
multiple of 15 to catch the case when it is a multiple of 3 and 5. I chose not to do this as the language of the business
only knows about 3 and 5.

Next the Requirements change.
Bigger number and a new word.
{% gist sbrady/cc4d973346627b804f2c 2add_baz_fizzbuzz.go %}
So I see a pattern in how the business is likely to change now. I have refactored `getBuzz`, `getFizz` etc. to use a 
domain model of a `Word`, a word has a relation ship with a multiple of. This now allows the code change easily when
the business wants to add more words.

Sure enough the requirements change. Even more words 
{% gist sbrady/cc4d973346627b804f2c 3add_more_changes.go %}
Now it was straight forward to add the new words. By simply adding:  
{% highlight go %}
Word{value: "Foo", multipleOf: 11},
Word{value: "Bar", multipleOf: 15},
Word{value: "Bam", multipleOf: 19}
{% endhighlight %}
to the `Words` repository. This approch to "FizzBuzz" shows not only understanding of control structures and operations, 
but also, the ability to write flexible, clear and maintainable code. 