## How to choose the Right Java Collection?

## Introduction
Every Java programmer might have already used Collections Framework at some point. However, there are some parts in Collections that many of us are unaware of. Sometimes we end up choosing a data structure not well suited for our purpose or we end up writing lots of lines of code for a task which could be easily solved using Collections. Therefore, a basic understanding of Java Collections Framework and its implementations is necessary. Through this blog, you are going to get a clear picture of ‘How to decide which collection will be the right choice for a particular purpose?’. 

**Prerequisite** - A basic understanding of Classes and Interfaces is advisable.

## The architecture of Collections Framework

Before we jump on to the details, let’s look at the architecture of the Collections.

![new-hierarchy.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664853794422/ZzTsR8ZbF.png align="center")

As you can see, the Collection Interface is being extended by 3 sub-interfaces viz List, Queue and Set which are further being implemented by different classes such as ArrayList, HashSet and so on. Each of these sub-interfaces has a different purpose to serve which we will be looking at shortly. The same goes for Map Interface which is being implemented by 2 classes (HashMap and LinkedHashMap) and extended by a sub-interface ‘SortedMap’.

## But when to use which Interface? 🤔

As you can see from the architecture, there are mainly 4 top-level interfaces. Each of them has different use cases.

- If we are dealing with some data which are in the form of `Key-Value` pairs, then **Map** Interface would be the right choice.
- If we are trying to store data with `no duplicates`, then we can use **Set** Interface which will store unique values.
- If we need to store some data in a `FIFO` manner, then **Queue** Interface would do the job for us.
- Lastly, if we want `faster insertion/deletion` or `faster access` to each element from our data, then we can use **List** Interface.

Let's try to understand them better by taking a closer look at each of them.

## List Interface

The List Interface is being implemented by many classes. Three of them are `ArrayList`, `LinkedList` and `Vector`. An `ArrayList` is a resizable array meaning the size of the array can be resized when needed. Elements inside an ArrayList can be accessed with their index values and hence accessing the elements is O(1) time complexity. However, the addition/deletion of elements from an ArrayList has an average time complexity of O(N). That's where the LinkedList class is beneficial. A `LinkedList` is an implementation of List and Queue. It consists of nodes connected one after another. Hence, the addition/deletion operation in this class is of O(1) time complexity. `Vector` is another implementation which is further extended by the Stack class. `Stack` is used when we have to store elements in `LIFO (Last-In-First-Out)` order.

![Implementations of List Interface.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664545456319/feZdxL_6u.png align="center")

## Queue Interface

The Queue Interface is used to store elements which are about to be processed in `First-In-First-Out (FIFO)` order. `PriorityQueue` is an implementation class of Queue where it keeps elements according to priority (sorted according to their natural ordering). `Deque` (Doubly Ended Queue) is a sub-interface of Queue which supports the addition/deletion of data from/to either end of the data structure and thus `Deque (properties of both LIFO/FIFO)` can also be used as a `Stack (only LIFO)`. `ArrayDeque` is a resizable-array implementation of Deque.

![Implementations of Queue Interface.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664545499530/ouIpwSC7s.png align="left")


According to [Javadocs](https://docs.oracle.com/javase/7/docs/api/java/util/ArrayDeque.html),
> *ArrayDeque class is likely to be faster than Stack when used as a Stack, and faster than LinkedList when used as a Queue.*

Now you might be thinking how are LinkedList and Queue similar?😕  
Well, LinkedList is an implementation of both List and Deque (a subinterface of Queue) Interface. So it is having the functions of both Interfaces.

## Set Interface

The Set Interface is a Collection which does not store duplicate values. The basic implementation of Set is the `HashSet` class where it stores unique values. This class does not store the elements in any order. `LinkedHashSet` is an extension class of Set with the additional functionality of storing the elements in the same order as they were inserted. `TreeSet` is yet another extension which stores the elements in their natural ordering (sorted order). 

![Implementations of Set Interface.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664545475380/xcf4R_Qpz.png align="left")

## Map Interface

The Map Interface is an essential part of the Collections Framework. It helps us store elements in `key-value` pairs. The basic implementation of Map is the `HashMap` class. But it stores the elements in random order. `LinkedHashMap` is an extension of HashMap which stores the key-value pairs in the same order as they were inserted. `TreeMap` is another extension of HashMap that stores the elements sorted by keys.


![Implementations of Map Interface.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664545513004/aXLUb7GTR.png align="left")

## Flowchart 
Let’s have a quick look 👀 at how our decision tree 🌲 will look if we gather all of the information mentioned above.

![new-collections.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664853859860/2I8So9H6-.png align="center")

The above diagram consists of the most widely used collections. Some of the data structures in this are not thread-safe and not synchronised. For synchronised versions, we can use `Collections.synchronizedCollection(Collection<T> c)` .

![Usage of Synchronised Collection.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1664545523537/b769DVMhG.png align="left")
 N.B: It is recommended to first note down the requirements and then follow the flowchart accordingly.

## Conclusion

You might not need to use all of these collections, but it's good to have a basic knowledge about all of them. Sometimes, a problem can be solved with multiple approaches using multiple different data structures. Try to implement those and you will be able to figure out how they are co-related with each other.

If this article helped you, please like and share it with your friends 🤗. Feel free to connect with me on [LinkedIn](https://linkedin.com/in/suvradip-paul) and [Twitter](https://twitter.com/SuvradipP) 🚀 .

Happy Coding !!!😊
