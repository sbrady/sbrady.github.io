---
layout: post
title:  "Groovy vs Ruby vs Java"
date:   2014-07-11 18:01:15
categories: groovy java ruby
---

I had spent a good deal of time working with Java, and some point around 2007 I became interesting in Ruby, and started
development Rails apps. I really enjoy the dynamic nature of Ruby. However I have come to miss the expressiveness of
static typing. Recently I did a little work on a Grails app and found that Groovy seemed to be doing everything I had
ever wanted. So I put together his language feature fight card below.
As you can Groovy comes up on top for my favourite language features.
 

<table>
<thead>
<tr>
  <th></th>
  <th>Groovy</th>
  <th>Ruby</th>
  <th>Java</th>
</tr>
</thead>
<tr>
  <td>Classical inheritance</td>
  <td>
{% highlight groovy %}
class Person {}  
class Engineer extends Person {}
      {% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
class Person end  
class Engineer < Person
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
class Person {}  
class Engineer extends Person {}
    {% endhighlight %}  
  </td>
</tr>



<tr>
  <td>Interfaces</td>
  <td>
{% highlight groovy %}
interface Person { void talk(name) }  
class Engineer implements Person{
  def talk(words) {
    println(words)
  }
}
//implement interface with map
def person = [
  talk: {words -> println words}
] as Person
      {% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
DERP..
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
interface Person 
{ 
  void talk(String name); 
}  
class Engineer implements Person{
  public void talk(String words) {
    System.out.println(words);
  }
}
    {% endhighlight %}  
  </td>
</tr>


<tr>
  <td>Mixin</td>
  <td>
{% highlight groovy %}
class Talk {
  def talk(word){
    println word
  }
}
@Mixin(Talk)
class Person {}
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
module Talk
  def talk(word)
    puts word
  end
end
class Person 
 include Talk
end  
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
DERP.
    {% endhighlight %}  
  </td>
</tr>


<tr>
  <td>Name Spaces</td>
  <td>
{% highlight groovy %}
package io.sbrady.people
@Mixin(Talk)
class Person {}
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
DERP. module namespaces  
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
package io.sbrady.people
    {% endhighlight %}  
  </td>
</tr>



<tr>
  <td>Dynamic Typing</td>
  <td>
{% highlight groovy %}
def talk(word){
  println word
}
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
def talk(word)
  puts word
end
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
DERP.
    {% endhighlight %}  
  </td>
</tr>

<tr>
  <td>Static Typing</td>
  <td>
{% highlight groovy %}
def talk(String word){
  println word
}
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
DERP.
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
public void talk(String word) {
System.out.println(word);
}
    {% endhighlight %}  
  </td>
</tr>


<tr>
  <td>Lambda/Closures</td>
  <td>
{% highlight groovy %}
static talk(talkFoodClosure) {
  talkFoodClosure("hi there");
}
static talkFood {
  def food = "pizza"
  talk({greeting->
    println "$greeting eat $food"
  })
}

{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
def talk(talkFoodlambda)
  talkFoodlambda.call("hi there")
end
food = "pizza"
talk(lambda{|greeting| 
  puts "#{greeting} eat #{food}"
})
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
public static void talk(
  Consumer<String> talkFoodlambda)
{
  talkFoodlambda.accept("hi there");
}    
String food = "pizza";
talk((greeting)-> { 
  System.out.println(
    greeting +" eat "+food
  );
});
    {% endhighlight %}  
  </td>
</tr>



<tr>
  <td>Collections (oldest person)</td>
  <td>
{% highlight groovy %}
people.max({person-> person.age})
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
people.max{|person|p.age }
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
people.stream()
  .max(
    (person1,person2) -> 
        (person1.getAge() 
           - person2.getAge())
   ).get();
   //better than it use to be..
    {% endhighlight %}  
  </td>
</tr>


<tr>
  <td>Monkey patching (make person 21)</td>
  <td>
{% highlight groovy %}
Person.metaClass.age = 21
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
class Person
  def age
    21
  end
end
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
DERP. DERP. AOP DERP.
REFLECTION DERP.
DO YOU REALLY WANT TO KNOW
    {% endhighlight %}  
  </td>
</tr>


<tr>
  <td>Named Arguments</td>
  <td>
{% highlight groovy %}
def add(params) {params.x+params.y}
add(x:100, y:99)
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
def add(x:0, y:0)
  x+y
end
add(x:100, y:99)
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
DERP. DERP. BuilderPattern
DERP.
    {% endhighlight %}  
  </td>
</tr>



<tr>
  <td>Score</td>
  <td>
{% highlight groovy %}
10/10
{% endhighlight %}
   </td>
  <td>
    {% highlight ruby %}
7/10
    {% endhighlight %}  
  </td>
  <td>
    {% highlight java %}
6/10
    {% endhighlight %}  
  </td>
</tr>



</table> 