# Java面试题

## 语言核心
### 初级
#### difference between `==` and `equals`
#### String, StringBuffer and StringBuilder, difference and when to use them?
#### Is class `String` can be inherited? Why?
#### Sequence in object instantiation?
#### In what situation there will be stack overflow?

### 中级
#### the `intern`method in `String` class, what's its functionality and how it works?
#### What is `extends` and `super` usage in Java Generic Programming?
#### What is reflection in Java? image I'm not familiar with Java.
#### Concurrency in Java? Thread, Thread pool?

### 高级
#### Difference between `Lock` and `Synchronized`?
#### What is memory model in Java? 
Memory Barrier, happen-before, reorder...

## JVM internal
#### The structure of class file?
#### What is class loader and what's its functionality? Parent Delegation Model? How to break?
- Bootstrap class loader: <Java_Runtime_Home>/lib
- Extension class loader: < Java_Runtime_Home >/lib/ext
- System class loader: CLASSPATH

Thread Context ClassLoader: java.lang.Thread$setContextClassLoader
#### What is GC in Java?
#### Talk about GC you know and how they works.
G1, CMS, 

## JDK 
#### ArrayList and LinkedList
#### Maps in JDK and scenario to use them?
    HashMap
    Hashtable
    Properties
    LinkedHashMap
    IdentityHashMap
    TreeMap
    WeakHashMap
    ConcurrentHashMap

SortedMap and how to implement it? Check [Java Collection Framework](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/overview.html)

#### How is `ConcurrentHashMap` implemented since Java 8?
Check [ConcurrentHashMap分析](http://www.jasongj.com/java/concurrenthashmap/)

## Spring框架

## 消息队列
#### Why we need message broker? How can we use Kafka? What Kafka gurantee and not gurantee?
#### CAP and BASE
CAP: Consistance, Availability and Partition Tolerance. 
BASE: Basically Available, Soft State, Eventually Consistence.
Partition, Replica, Consistance. see DDIA.

## 数据库相关
#### What is ACID?
Atomic, Consitance, Isolation, Durability.

## 设计模式
#### List design patterns you are familar with.
##### Write a thread safe Singleton.

## 算法
#### Delete the last Nth element in a linked list?
#### Traverse Tree(Recursive and Iteration), Pre-order/In-order/Post-order
#### [maximum-length-of-pair-chain](https://leetcode.com/problems/maximum-length-of-pair-chain/)

Refer: [Questions](https://segmentfault.com/a/1190000016172470)
