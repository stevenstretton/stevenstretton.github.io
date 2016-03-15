---
published: true
title: The confusing world of an Abstract Class
layout: post
---
##What is an Abstract Class?
A abstract class basically means that nobody can make a new instance of that class. 
* It can be used to declare a reference type, for polymorphism purposes
* You don't have to worry about someone making objects of that type, this is guaranteed by the compiler.

Below we set out our abstract type:

`abstract public class Canine extends Animal
{
    public void roam() { }
}

public class MakeCanine {    //This code would work
      public void go() {
          Canine c;
          
          c = new Dog();
          c.roam();
      }
}`

However the following would fail:
`abstract public class Canine extends Animal
{
    public void roam() { }
}

public class MakeCanine {    
      public void go() {
          Canine c;
          
          c = new Canine();    //BOOM! - Errors here because Canine is abstract 
          c.roam();
      }
}`