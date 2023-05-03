# Questions
those are my answers, feel free to add yours and correct me if I am wrong.

## what is a dataclass
a dataclass is a class in kotlin that is used to store data. it has all the nescessary getters and setters, toString() and equals methods.

## what is a singleton
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

## lateinit keyword
late init helps us initialize a member variable later. this keyword assurs that we will initialize it later. avoiding null saftey checks.
primitives cannot be lateinitialized. how do we check if is initialized? we can use ``variable.isInitialized``

## lateinit Vs lazy
lateinit can only be used with a var property whereas lazy will always be used with val property. a lateinit property can be reinitialised again and again as per the use whereas the lazy property can only be initialised once.lateinit properties can't be of primitive data types whereas lazy properties can be of primitive date types also.

# equivalent of java's static methods in kotlin?
companion objects are the equivalent. we can also annotate it with @Jvmstatic so that bytcode implementation can translate to Java's static methods.

# the difference of map and flat map in kotlin?
In Kotlin, map() and flatMap() are both higher-order functions used to transform collections. However, there are some differences between the two:

1. Return Type: The map() function returns a new collection of the same size as the original collection, whereas flatMap() returns a flattened collection.

2. Nested Collections: If the original collection contains nested collections, map() will return a new collection of nested collections with the same structure as the original, whereas flatMap() will flatten all nested collections into a single collection.

3. Functionality: The map() function applies a transformation function to each element of the collection and returns a new collection with the transformed elements. On the other hand, flatMap() applies a transformation function to each element of the collection and then flattens all resulting collections into a single flattened collection.

4. Performance: In terms of performance, flatMap() can be more efficient than using multiple map() calls followed by flatten(), especially when dealing with large collections or deeply nested structures.

In summary, while both map() and flatMap() are used for transforming collections in Kotlin, they have different functionalities and return types. Map() is used to transform each element in a collection while maintaining its structure, while flatMap() is used to transform each element in a collection and flatten any resulting nested collections into one flattened list.

# what are the visibility modifiers in kotlin
There are four visibility modifiers in Kotlin: private, protected, internal, and public. The default visibility is public.

# difference between internal and protected
protected means that the member has the same visibility as one marked as private, but that it is also visible in subclasses.
internal means that any client inside this module who sees the declaring class sees its internal members.

# what is livedata
LiveData is a part of the architecture patterns. It's basically a data holder that contains primitive/collection types. It's used for observing changes in the view and updating the view when it is ACTIVE. Thus, LiveData is lifecycle aware.

# what are coroutines
coroutines are like "light weight threads" which handle context switching by themselves with suspension and resuming.

# what is suspend function
A suspending function is simply a function that can be paused and resumed at a later time. They can execute a long running operation and wait for it to complete without blocking.

# how would you use suspend function inside a normal function?
a suspend function can be use inside a normal function in many ways. one can be by marking the normal function as suspend function, by calling it inside a
coroutine scope after specifying a dispatcher or by using asyc/await.

# what is the difference between launch and async
launch starts a new coroutine and doesn't return the result to the caller. Any work that is considered "fire and forget" can be started using launch.
async starts a new coroutine and allows you to return a result with a suspend function called await.

# what is the difference between listView and recyclerView
well, both are used to display a list of items in Android. but recyclerView is much more advanced while listViews are more primitive. recyeclerview can
recycle views when item views are out of screenbounds. hence, improving performance over all. recyclerView can also be use with pagination libraries to 
display a lazy list where items are loaded in demand. recyclerview can also have different viewholders based on usecase and application state.

# what is viewHolder pattern
The ViewHolder pattern is a design pattern used in Android development to improve the performance of RecyclerViews. It involves creating a separate class that holds references to the views in a single item of the RecyclerView. This class is called the ViewHolder.

When a RecyclerView is scrolled, new items are created and old items are recycled. The ViewHolder pattern allows for the reuse of existing views, reducing the number of view creations and improving performance.

# major difference between views and viewgroups
View is the base class for widgets, which are used to create interactive UI components like buttons, text fields, etc. The ViewGroup is a subclass of View and provides invisible container that hold other Views or other ViewGroups and define their layout properties.

# how would you optimise recyclerview?
1. Use the ViewHolder pattern: This pattern helps to reduce the number of findViewById() calls and improves performance.
2. Implement DiffUtil: DiffUtil is a utility class that calculates the difference between two lists and updates only the necessary items in the RecyclerView.
3. Use a custom layout manager: A custom layout manager can help to optimize the layout of items in the RecyclerView.
4. Limit the number of views: Avoid creating too many views at once, as this can cause performance issues. Instead, use pagination or lazy loading to load data as needed.
5. Optimize item layouts: Make sure that item layouts are optimized for performance by using lightweight views and avoiding nested layouts.
6. Use RecyclerView.RecycledViewPool: This class helps to reuse views across multiple RecyclerViews, which can improve performance.
7. Avoid unnecessary animations: Animations can be resource-intensive, so avoid using them unnecessarily in your RecyclerView.
8. Use data binding: Data binding can help to reduce boilerplate code and improve performance by reducing the number of findViewById() calls.
9. Use an image loading library: If your RecyclerView contains images, consider using an image loading library like Glide or Picasso to improve performance and reduce memory usage.
10. Profile your app: Finally, use profiling tools like Android Profiler or Systrace to identify any performance bottlenecks in your app and optimize accordingly.

# what does okhttp interceptor mean?
OkHttp interceptor is something that intercept the http requests before/after they were made. good example of this would be the logging interceptor that is 
used when you want to log http-requests.

# how does http caching work in Android
when using HttpUrlConnection can be triggered by first setting setUseCaches to true, then the response must be bundled with caching strategy then calling 
HttpResponseCache.install() this will allow the implementation to create cache files in side the cache dir. it gets easier if using third party library like
okhttp or retrofit.

# can you give tell about rxJava? how it works and its functionalities?
RxJava is a Java based extension of ReactiveX. ReactiveX is a project which aims to provide reactive programming concept to various programming languages.
Reactive Programming refers to the scenario where program reacts as and when data appears. It is a event based programming concept and events can propagate to
registers observers. As per the Reactive, they have combined the best of Observer pattern, Iterator pattern and functional pattern.

Some of its features include:
 - Extends the observer pattern.
 - Support sequences of data/events.
 - Provides operators to compose sequences together declaratively.
 - Handles threading, synchronization, thread-safety and concurrent data structures internally.

# how would you handle errors in RxJava
First, keep in mind that the Observable typically does not throw exceptions. Instead, by default, Observable invokes its Observer's onError() method, notifying 
the observer that an unrecoverable error just occurred, and then quits without invoking any more of its Observer's methods. 
there are many ways:
 - onExceptionResumeNext()
 - onErrorResumeNext()
 - doOnError()
 - onErrorReturnItem()
 - onErrorReturn()
further reading, [here](https://www.geeksforgeeks.org/error-handling-in-rxjava/), [here](https://medium.com/swlh/master-error-handling-in-rxjava-crush-em-5cb66bb16ccd) and [here](https://www.baeldung.com/rxjava-error-handling)
