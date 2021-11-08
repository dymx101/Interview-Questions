# iOS Interview Script (for interviewer)

### Greetings 
Hi Phat Chiem, good morning!
How are you?
Nice to meet you online.


### Introduction of myself
My Name is Yiming
I am iOS Developer at Grab from Transport Team.
From China, Currently working in Singapore


### Candidate self introduction
Can you do a self introduction?
Listen and observe:
What’s the current product he’s working on? 
What architecture? MVVM
libraries? RxSwift, SnapKit

### RxSwift Questions:
1. What’s the difference between PublishSubject and BehaviorSubject? When to use them?
The main difference between PublishSubject and BehaviorSubject is that the latter one remembers the last emitted item. Because of that BehaviorSubject is really useful when you want to emit states. 

2. Difference between flatMap and flatMapLatest?
The difference between flatMap and flatMapLatest is that flatMapLatest will only produce elements from the most recent Observable sequence, so as the Observable sequence emits new Observable sequence, flatMapLatest switches to that new Observable sequence and ignores emissions from the previous sequence.
https://medium.com/@navdeepsingh_2336/transforming-operators-map-flatmap-and-flatmaplatest-c233a536b38b

### SWIFT questions:
1. What’s the difference between Struct and Class? 
Classes can inherit from another class, like you inherit from UIViewController to create your own view controller subclass
Classes can be deinitialized, i.e. you can invoke a deinit() function before the class is destroyed
Classes are reference types and structs are value types
https://learnappmaking.com/struct-vs-class-swift-how-to/

2. When Should You Use Structs?
When should you use classes?
 it’s smart to use classes if you need the features that only classes provide: inheritance, identity, Objective-C interoperability, and scenarios where copying a value doesn’t make sense.

3. What is value type and what is reference type?
Are these types Reference Type or value type? 
Basic types, enums, structs, optionals, closures, tuples, classes, function
In Swift, everything is a value type, unless it’s a class, function or closure.

4. Why closure is designed as reference type?
Closures capture values in their context. If a closure were copied every time it was passed around, it would lose context that it has access to. In other words, it would lose access to those local variables. Here’s an example: https://www.oreilly.com/library/view/learning-swifttm-programming/9780133950410/ch06lev2sec5.html
What if a reference type contains value types, and vice versa?
 In general, it’s perfectly OK if a reference type contains value types 
when a value types contains reference types, it’s easiest to avoid this. If you must, implement your own deep copy method for the reference type, or find a good way to compare equality between two reference type objects.

4. What are lazy var?
5. What is a lazy collection?
A lazy collection postpones calculations until they are actually needed. This can be beneficial in many different cases and prevent doing unneeded work i
When and why should we use a lazy collection? When shouldn't we use it?
f elements are never being asked in the end.
Advantage: 1. Handling output values on the go 2. save you from a lot of work if only a few items are used from a big collection.
Opt-in: 1.Don’t over optimize 2. Lazy Collections don’t cache 3. Take the delay into account 4. Consider using standard Swift APIs over lazy arrays
https://www.avanderlee.com/swift/lazy-collections-arrays/

6. MVVM (https://www.mytectra.com/interview-question/mvvm-interview-questions-and-answers)
- What is MVVM?
The Model View ViewModel (MVVM) is an architectural pattern used in software engineering as a specialization of the presentation model design pattern.Largely based on the model–view–controller pattern (MVC),  MVVM is targeted at UI development platforms which support event-driven programming.
- What are the benefits of MVVM?
The different layers View,ViewModel and Model are loosely coupled.This gives application developed using MVVM pattern following advantages:
Application is easer to maintain and extend
Application is easier to unit test

- If familiar with VIPER or RIBs:
Describe how VIPER or RIBs works?
How is it different from MVVM?
When and why to choose VIPER/MVVM/MVC? 
https://www.objc.io/issues/13-architecture/viper/


- If knows Flutter:
What are the advantages of Flutter Over Native?
Can Existing Native APP use Flutter? How?

- If knows swiftUI:
What are the advantages of using swiftUI?
What are the disadvantages or restrictions of using swiftUI?


### Encode and Decode the widget response
https://codeshare.io/dw6MDz


### Do you have any questions for me?


### End the interview




### Pro (G4)
Return all permutations of an array of integers
Input: [1, 2, 3]
Output: [[Int]]
https://leetcode.com/problems/permutations/


