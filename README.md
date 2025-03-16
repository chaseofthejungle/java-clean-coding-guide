# Java Clean Coding Guide

#### Table of Contents (this guide will include detailed sections on the following items)

1. [Follow Naming Conventions](#conventions)
2. [Use Self-Documenting Variable Names](#documenting)
3. [Keep Methods to the Point](#methods)
4. [Keep Classes to the Point](#classes)
5. [Choose Constants for Non-Changing Values...](#constants)
6. [... and Use Enums with Constants](#enums)
7. [Handle Exceptions](#exceptions)
8. [Be Cautious of NullPointerException](#nulls)
9. [Utilize Streams Properly](#streams)
10. [Utilize Dependency Injection (DI)](#dependency)
11. [Supplemental Resources](#supplement)

<hr />

## 1. <a name="conventions">Follow Naming Conventions</a>

<hr />

## 2. <a name="documenting">Use Self-Documenting Variable Names</a>

<em>Self-documenting</em> code is easy to understand simply by reading it. Its purpose becomes apparent without needing extensive commenting.

<strong>Not a Great Idea:</strong>

```
String n = "Billy";
```

<strong>Better Idea:</strong>

```
String firstName = "Billy";
```

<hr />

## 3. <a name="methods">Keep Methods to the Point</a>

<hr />

## 4. <a name="classes">Keep Classes to the Point</a>
  
Classes should follow the Single Responsibility Principle (SRP): that is to say, they should 'have one job'. This is important for a variery of reasons, such as improving readability for oneself and other developers and clarifying the code's purpose.
  
<strong>Not a Great Idea:</strong>
  
```
public class Bookstore {
  // Customer logic
  // Order logic
  // Book logic
  // ... other responsibility here...
}
```
  
<strong>Better Idea:</strong>
  
```
public class Customer {
  // Customer logic
}
  
public class Order {
  // Order logic
}
  
public class Book {
  // Book logic
}
```

<hr />

## 5. <a name="constants">Choose Constants for Non-Changing Values...</a>

By declaring <em>constants</em> instead of variables, it is clarified that a value is not to be updated. Furthermore, accidental changes to the data are prevented.

<strong>Not a Great Idea:</strong>

```
int guesses = 5; 
```

<strong>Better Idea:</strong>

```
public static final int MAX_GUESSES = 5;
```

<hr />

## 6. <a name="enums">... and Use Enums with Constants</a>

<hr />

## 7. <a name="exceptions">Handle Exceptions</a>

<hr />

## 8. <a name="nulls">Be Cautious of NullPointerException</a>
  
<em>NullPointerException</em> is thrown when an uninitialized object is attempted to be accessed or modified.
  
<strong>Not a Great Idea:</strong>

```
String firstName = null;

if (firstName.equals("Bob"))
```

<strong>Better Idea:</strong>

```
String firstName = null;

if (StringUtils.isNotEmpty(firstName) && firstName.equals("Bob"))
```

Consider using `equalsIgnoreCase()` for conditional logic, if the value should be evaluated the same way regardless of lowercase or uppercase letter usage (e.g., if "Bob" and "bob" are to be handled the same way).

<hr />

## 9. <a name="streams">Utilize Streams Properly</a>

<hr />

## 10. <a name="dependency">Utilize Dependency Injection (DI)</a>

<hr />

## 11. <a name="supplement">Supplemental Resources</a>

<a href="https://github.com/chaseofthejungle/intro-to-java">Intro to Java Overview Guide</a>  
<a href="https://github.com/chaseofthejungle/java-quick-reference-guide">Java Quick Reference Guide</a>
