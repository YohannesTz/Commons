# Questions
those are my answers, feel free to add yours and correct me if I am wrong.

## what is a dataclass
a dataclass is a class in kotlin that is used to store data. it has all the nescessary getters and setters, toString() and equals methods.

## what is a singlton
a singleton is a software design pattern that restrict that there should be one instance of an object through out the life time of a program.this
can be achived by making the constructor of the class private (so it cannot be initialized from anywhere) and provide a public function to get the instance.

## what is companion object
In Kotlin, a companion object is an object that is associated with a class. It is similar to static methods in Java. The companion object can access 
private members of the class and can be used to define factory methods, constants, or other utility functions related to the class. 

## what is higher order function
In kotlin, functions are first-class. so by higher order function are functions that take as a parameter and/or return funtions.

## what is string interpolation
string interpolation is a way to concatinate or build strings elegantly

``
print("this is $somevar good for ${someOtherfun()} or ${Someclass.someString()}")
``
## destructuring
a convenient way to access members form an object:
``val (name, age) = person``

## late init keyword
late init helps us initialize a member variable later. this keyword assurs that we will initialize it later. avoiding null saftey checks.
primitives cannot be lateinitialized. how do we check if is initialized? we can use ``variable.isInitialize``

## 
