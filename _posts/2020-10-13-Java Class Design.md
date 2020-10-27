---
title: Java Class Design
date: 2020-10-13 5:23:30 +5:30
tags: [class design,java 8]
description: 1Z0-809 - Java Class Design
---


# Exam Objectives
#### Implement Encapsulation
   ##### Points to remembered 
     1) instance variables are kept private.
     2) getters of the instance variables are public.
     3) setter of the instance variables are protected.


    ##### while using a instanceof  B
        - object a has to be either sameclass,subclass or implements interface B
        - the compiler allows an object of type to check against any interface and
           only the classes that are directly related.
      
    ##### Virtual Method Invocation
        is when method we call a method of subclass from object of superclass
        void somemethod(SuperclassA objA){ 
           if(objA instanceof SubClassB)
            ((SubClassB) objA).doSomethodInB();
        }
        
    ##### In inheritance,
        -  method calls refer to overriden method of the type assigned.
             ClassA  objA = new ClassB();
             objA.printSound(); - prints sound from ClassB 

        -  instance variables refer to the type declared
             ClassA  objA = new ClassB();
             objA.name gets the name from ClassA   

     ##### Annotations
         Though annotations are  only for  making the developers aware with extra information, 
         it can also make compile fail if the conventions intended is not followed.
         for eg; using @Override on a non existing method in superclass will give you compilation error.
 
##### Implement Inheritance with access modifiers composition
##### Implement Polymorphism
##### Override hashCode,equals and toString methods of the Object Class
##### Create and use  singleton classes and immutable classes
##### Use static keyword on initializer blocks,methods,variables and classes
