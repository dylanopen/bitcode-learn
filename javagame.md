# Create 2D Games With Java

In this guide, we will create an entire game library from scratch.

We will not use any external packages, so the entire game is based upon built-in Java modules.

It's recommended that you have some idea of Java programming before starting this tutorial. If you'd like to learn Java, please read my [Ultimate Guide To Java Programming](java.md) course.

## Chapter 1.1 - Creating a Game Library

In this chapter, we will set up the basic structure for our library.

### Project structure

In an IDE or code editor of your choice, create a new Java project.

I'm going to be recreating my `Realms` game library I built recently, so I'll name my project `Realms2`. Wherever you see the word `realms`, make sure to change it to your own library name!

Inside the project, create a new package called `realms.game`. This package will contain the frontend for creating a window, as well as other classes in the future.

Inside the `realms.game` package, create a `Realm` class. This class will be responsible for managing many other classes in the library.

### Test package

Because we are creating a **library** and not directly a **game**, we can't directly run our project.  
Instead, we need to **export** the project to a `.jar` file and **import** it into a separate 'testing' project.

This can get tedious, so while our project is still in development, I'd recommend creating a new package called `realms.test`, which will contain a class with an entry-point `main` method.

This means that we can easily test whether our library is working without having to export anything!

Inside `realms.test`, create a new `Test` class.

### File tree

So far, our project file tree looks like this:

``` text
Realms2/
 \-- src/
      \-- realms.game/
           \-- Realm.java
      \-- realms.test/
           \-- Test.java
```

### Initial `Realm` class

Type this code into `Realm.java`:

``` java
package realms.game;

public class Realm
{
	public Realm()
	{
		System.out.println("Welcome to Realms!");
	}
}
```

This class has a constructor which simply prints some text to the terminal. It's a simple test to check we've got the file structure correct.

### Initial `Test` class

Next, add this code to `Test.java`:

``` java
package realms.test;

import realms.game.Realm;

public class Test
{
	public static void main(String[] args)
	{
		Realm realm = new Realm();
	}
}
```

This class contains the `main` method, so it's the file we will run when we test our program.

Make sure to import your main `Realm` class, or the JVM won't be able to find the `Realm` constructor.

This simple program essentially creates a new `Realm` object, which calls the constructor.

### Output

The program works sucessfully, outputting:

``` text
Welcome to Realms!
```

Now that we have the basic project structure working, we can start implementing a basic **window**.

## Chapter 2 - Creating a Window

### The `Window` class

If we want to make our code as clean as possible, we need to define a separate class to manage the window.

Create a new package, `realms.graphics`, and create the `Window` class inside it:

``` java
package realms.graphics;

public class Window
{
	private String title;
	private int width, height;
	
	public Window(String title, int width, int height)
	{
		this.title = title;
		this.width = width;
		this.height = height;
	}
}
```

Of course, this class is never actually used. We need to update our `Realm` class if we want the `Window` class to actually *do* something.

### Updating the `Realm` constructor

The next thing to do is to update the `Realm` constructor to take in the properties for the window.  
This will allow the user of our library (the game programmer) to customise the window to their liking.

Update the `Realm` class to contain the following code:

``` java
package realms.game;

import realms.graphics.Window;

public class Realm
{
	public static Realm realm;
	public Window window;
	
	public Realm(String title, int width, int height)
	{
		Realm.realm = this;
		window = new Window(title, width, height);
	}
}
```

This new code will automatically create a new `Window` object when we instantiate `Realm`.

Also notice that we store the current `Realm` object in a static variable. This allows us to easily access this object from any class, without constantly passing random objects between constructors.

### Creating a JFrame

The next step is to actually create the window. We do this by instantiating a `JFrame`, which is a part of Java's `swing` package.

In the `Window` constructor, after we assign `this.height`, add the following function call to `createJFrame()`:

``` java
createJFrame();
```

The entire constructor now reads:

``` java
public Window(String title, int width, int height)
{
	this.title = title;
	this.width = width;
	this.height = height;
}
```
