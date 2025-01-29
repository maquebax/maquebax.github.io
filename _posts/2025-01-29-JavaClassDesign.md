---
title: Java Class Design
date: 2025-01-29 5:23:30 +5:30
tags: [class design,java 8]
description: 1Z0-809 - Java Class Design
---


# Exam Objectives
#### Implement Encapsulation
##### Points to remembered 
- instance variables are kept private.  
- getters of the instance variables are public.  
- setter of the instance variables are protected.  


##### while using `a instanceof  B`
- object **a** has to be either of sameclass B, subclass of B or type implementing interface B
- the compiler allows checking an object of a type against any interface and
  only the classes that are directly related.
      
##### Virtual Method Invocation
when  we call a method of subclass from object of superclass.  
    
    void somemethod(SuperclassA objA){ 
        if(objA instanceof SubClassB)
            ((SubClassB) objA).doSomethodInB();
    }
    Class A objA = new ClassB();
    objA.printSound(); // prints Sound from Class B


##### In inheritance,
    -  method calls refer to overriden method of the type assigned.
        ClassA  objA = new ClassB();
        objA.printSound(); - prints sound from ClassB 

    -  instance variables refer to the type declared
        ClassA  objA = new ClassB();
        objA.name gets the name from ClassA   

##### Annotations
Though annotations are  only for  making the developers aware with extra information,  
it can also make the compile fail if the conventions intended is not followed.  
for eg; using @Override on a method which does not exist in superclass will give you a compilation error.  
 
#### Implement Inheritance with access modifiers composition
#### Implement Polymorphism

#### Override hashCode,equals and toString methods of the Object Class
Every Object has these 3 methods(toString, equals and hashCode ) by default.
##### toString()
    @Override
    public String toString() {
        return getClass().getName() + "@" + Integer.toHexString(hashCode());
    }  

this method allows us to summarise what the object of  this class is all about.  
when we do System.out.println(new ClassA()); the toString method of the class gets called.  
##### equals
    @Override
    public boolean equals(Object obj){
        return {this == obj};
    }  

We override the equals method mainly to check equality of two objects.  
When we use == on objects for eg: objA == objB  
the compiler checks only if the object referrences are same. Hence we use equals method  
to test equality of objects. When we override equals method, we check for values of desired instance variables.  
&emsp;The equals method must adhere to following properties.  
&emsp;&emsp;1.reflexive  x.equal(x) always true  
&emsp;&emsp;2.symmetric  if x.equals(y) true then y.equals(x) true - always  
&emsp;&emsp;3.transitive if x.equals(y) and y.equals(z) then x.equals(z) - either all true or all false.  
&emsp;&emsp;4.consistent x.equals(y) always true and x.equals(null) always false  
&emsp;&emsp;5.Also in practice, the hashCode of 2 equals objects should be same.  

##### hashCode
    @Override
    public native int hashCode();  

hashCode gives an unique integer to identify or classify an object into categories.  
hashCode should have conditions which is a subset of conditions written in equal.  
i.e when two objects are equal , their hashCodes should always be equal.  
but when hashCodes of two objects are equal, the objects need not be equal.  
hashCodes are mainly used in collections like maps to segagrate values in to buckets for faster indexing.  


#### Create and use  singleton classes and immutable classes
#### Use static keyword on initializer blocks,methods,variables and classes
