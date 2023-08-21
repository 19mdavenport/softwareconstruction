# Java Generics

🖥️ [Slides](https://docs.google.com/presentation/d/1a3aELn5tIIfY-g4-wOQ1vackTD4RacDn/edit?usp=sharing&ouid=114081115660452804792&rtpof=true&sd=true)

📖 **Required Reading**: Core Java SE 9 for the Impatient

- Chapter 6: Generic Programming. _Only_ Sections 6.1-6.4

`Generic Programming` is a common programming language technic that is useful for strongly typed languages such as C++, C#, or Java. You can use generic programming to reuse class or function code that only differs by the type of variables they operate on.

For example, consider the standard JDK object `ArrayList<T>`. The `<T>` part of the class name refers to the `type parameter` for the class. When you create an object based on this class you specify what type you want the generic to use. This means you can create an `ArrayList` that only contains `String` objects or one that only contains `Integer` objects.

```java
var intList = new ArrayList<Integer>();
var stringList = new ArrayList<String>();

intList.add(3);
stringList.add("cow");

Integer integerItem = intList.get(0);
String stringItem = stringList.get(0);

```

If you attempt to put an integer into the stringList you will get a compile time error, and vice-versa. Also, because the compiler knows what its type parameter is bound to for the generic class, you don't need to do the type conversion.

Before generics were introduced to Java you had to either create a different class implementation for each type you wanted to support, or you had to use an `Object` to represent the type of the class and then typecast the `Object` before you could use it. Consider the follow use of the non-generic `ArrayList` class.

```java
var list = new ArrayList();
list.add(3);
list.add("cow");

Integer integerItem = (Integer) list.get(0);
String stringItem = (String) list.get(0); // Exception thrown at runtime
```

Not only does this code force the overhead of type casting, it is also dangerous because you never really know what type of object you are getting from the list unless you use reflection pervious to the type cast. If you guess wrong you will throw a runtime exception.

## Demonstration code

📁 [KeyValuePair.java](example-code/KeyValuePair.java)

📁 [Pair.java](example-code/Pair.java)

📁 [PairUser.java](example-code/PairUser.java)

📁 [StringPair.java](example-code/StringPair.java)

📁 [interfaceExample](example-code/interfaceExample)
