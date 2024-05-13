# The Ultimate Guide To Java Programming

- Dylan Rogers

## Introduction

In this course, you will learn everything you need to know to become an expert Java developer.  
We will discuss the syntax of Java, as well as the many useful libraries and classes Java provides us with.

## Contents

[Chapter 1 - Hello World](#)

## Chapter 1 - Hello World

In this chapter, we will learn how to create a 'hello world' program - a simple program that prints the text `"Hello, World!"` to the screen.

This will allow us to understand the basics of Java programming, which is vital for understanding the programs we will build later on.

### Key concepts

* Packages
* Classes
* The 'main' method
* Printing text

### Project setup

For these lessons, I'd recommend that you use an *IDE* (integrated development environment) such as [Eclipse](https://eclipseide.org) or [IntelliJ](https://www.jetbrains.com/idea/). While it's not required, it will allow us to get started with programming much faster than it would be to do everything from the command line.

In an IDE of your choice, do the following:

1. Create a new Java project ('HelloJava').
2. Create a new source folder called `src` in that project.
3. Create a package inside the `src` folder called `hello`.
4. Create a class called `Hello` inside the `hello` package (capitalise the `H`).

### Coding

Inside the `Hello.java` class file you just created, type the following code:

``` java
public class Hello
{
	public static void main(String[] args)
	{
		System.out.println("Hello, world!");
	}
}
```

We will explore how this code works later. For now, let's focus on running it.

### Running the code

In an IDE, running the code is very simple. Simply press the green 'run' button, or press the keyboard shortcut (usually `f5` or `f11`).

If you're using the command line, `cd` into your `hello` package and type the following:

``` bash
javac Hello.java  # compiles the code to a .class
java Hello        # runs the .class file
```

### Output

If you did everything correctly, you should see the following output printed to your console:

``` text
Hello, world!
```

... You've never been so happy to see some text printed to the terminal!

If you get any errors, reread this chapter and see if you can find the issue - most likely the issue will be one of these:

- You have mistyped the code
- You don't have the **Java Development Kit (JDK)** installed
- Your project file structure is incorrect

Hopefully, you can fix any errors you may have and continue with your programming journey.

### Explanation: classes

First, we'll look at this code snippet in more detail:

``` java
public class Hello
{
	...
}
```

The `class` keyword tells the Java compiler to define a new **class**. A class in this case is just a container for method(s).  
Classes can do a lot more as we will learn in future chapters, but for now, just think of classes as a container for different variables and methods (functions).

We follow the `class` keyword with the identifier `Hello` to show that our class is called `Hello`. We can name the class whatever we want, but it **must** match the file name.

The `public` keyword is an **access modifier**. These allow us to specify who and what can access our class, method or variable. In this case, we want everything to be able to access the `Hello` class, so we make it `public`.  
Access modifiers go **before** the `class` keyword.

The brackets `{ }` define the **class body**. Essentially, everything inside these brackets is part of the class, while anything outside of them is not.

### Explanation: the 'main' method

Now consider this code snippet:

``` java
public static void main(String[] args)
{
	...
}
```

Once again, the `public` access modifier is used to ensure that the OS can call our `main` method.

The `static` keyword states that our method is... well... static. Explaining what static methods are could get a bit complicated, but the essence is that static methods do not get called on an object. In other words:

* Imagine we have a 

## 
