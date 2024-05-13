# The Ultimate Guide To C++ Programming

- By Dylan Rogers

## About this book

This document is a complete guide to the C++ programming language. It covers everything you need to know about programming in C++, and is a helpful guide to both beginners and more experienced developers.

Throughout the book, we will be creating programs and learning new language features, all using example. That way, you will learn not just how to code, but also how to apply that knowledge to programming problems.

There are also **challenges** throughout the book, which help to consolidate what you've learned.

Good luck, and enjoy the journey!

### Licence

You may use any content from this book in your work, with no limits.

If you are using content from this book in your own custom programs, you may use all content in this book **freely**.

However, if you are producing content similar to this book (and wish to use content from it) you must **explicitly** include the following attribution when using **each** section of content:

``` text
Source: The Ultimate Guide To C++ Programming by Dylan Rogers
```

You must also include this in any type of programming tutorial you produce. In a video containing content from this book, you must **audibly state** the book title and author.

## Chapter 1 - Setting Up

> No coding in this chapter yet... sorry :\(

In order to get everything ready, we need a few things:

* A code editor (vscodium)
* A compiler (g++)
* A terminal to run our program

### Windows setup

Windows is not the best platform to develop C++ applications on, as it fails to support many of the useful tools for development, such as a good compiler.

If you absolutely *must* use a Windows machine and cannot use or emulate a Linux or macOS system, you can get away with using 'Microsoft Visual Studio' (**not** VS Code).

Install that [here](https://visualstudio.microsoft.com/) and make sure to select the option for C++ development in the installer.

Open VS, create a new C++ project, and you should be able to follow along with the rest of the tutorial!

### Code editor setup

> Note: Skip this step if you're on Windows and you have Microsoft Visual Studio (**not** code) installed.

The first thing we need to do before we start coding in C++ is to install a code editor. This is essentially just a fancy text editor that gives us some extra features.

My two preferred editors are:

* Neovim
* VSCodium

... but feel free to use whichever editor you want. They're not too complicated to understand.

Throughout this tutorial, we will use VSCodium, as it's slightly easier to get it set up than it is to create an entire nvim config from scratch...

Head over to [VSCodium's GitHub release page](https://github.com/VSCodium/vscodium/releases) and download the latest release (you may need to 'show all assets'). You can also install it from your package manager, although the versions stored in package repos tends to be quite old, so I'd recommend downloading the GitHub release.

Install the downloaded file as you normally would.

> Note: VSCodium is the open-source version of Microsoft's Visual Studio Code. You can download the proprietary version if you wish, but VSCodium is the same thing but without Microsoft's bloat.

You will likely want to install a C++ extension in your code editor. My favourite is `clangd` as it's extremely fast and works very well, but there are alternatives if `clangd` doesn't work well for you.

### Installing a compiler

> If you are on Windows, you can use Visual Studio to compile your program. Just click the 'run' button at the top of the window. If not, read the steps below to install `g++`.

To compile our projects, we will use a compiler called `g++`. This tool will allow us to build our C++ source code into an executable file.

Using your default package manager, install the `g++` package. For example:

* sudo pacman -S g++
* sudo apt install g++

If the `g++` package is not found, try instead installing the `gcc` package. Often, this will contain the `g++` compiler.

When we've written our code file, we will use this command to compile it:

``` sh
g++ src/hello.cpp -o build/hello
```

This will compile the `hello.cpp` file in the `src` directory and create the `hello` executable inside the `build` directory.

### Running our program

Once the program is compiled, use the following command to run it:

``` sh
./build/hello
```

... where `hello` is the name of the executable (filename after the `-o` when building with `g++`).

> Note: You must be in the project directory to run the program like this, or the shell won't be able to find the executable.

## Chapter 2 - Hello C++

In this chapter, we will build our first C++ program - a program that simply prints text to the console!

### Project setup

Create a new directory (folder) somewhere on your system. This will be your project directory.

Inside your project directory, create two new directories:

* src/
* build/

Finally, create a file inside `src/` called `hello.cpp`. This will be our main source code file for the program.

### Coding

Inside `hello.cpp`, type the following code:

``` cpp
#include <iostream>

int main(int argc, char* argv[])
{
	std::cout << "Hello C++";
	return 0;
}
```

We will explain it in a second, but for now, 

### Running the program

Open a terminal and navigate to the project directory:

``` sh
cd /home/yourname/coding/hello/
```

Finally, run these two commands:

``` sh
g++ src/hello.cpp -o build/hello  # compile the program

./build/hello                     # run the program
```

You should see the program printing to the terminal.

### Output

Our 'Hello C++' program gives the following output:

``` text
Hello C++
```

Success! You have written and compiled your first C++ program. Now to apply for a Google interview as a 'senior developer'...

Wait a sec. Let's actually go through how this all works.

### Explanation

We'll look at our program in small snippets of our code to fully break down what's going on.

``` cpp
#include <iostream>
```

* Here, we 'include' the `iostream` (input output stream) library.
* This library provides us with many features, such as the `cout` stream for printing text.
* The hashtag (`#`) tells us that this is a **preprocessor directive**. You don't need to understand the details, but this is essentially a program that's run **before** the compiler.
* `#include` essentially just brings in the code from a **header file** and allows us to use that code in our own program. Think of it as similar to an `import` statement in other languages.
* We use the **angle brackets** (`<>`) here instead of quotation marks (`"`) because the `iostream` library is located in the **system packages**, not the current directory.
* Just remember - use quotes for local, project-specific headers, and angle brackets for global system headers such as `iostream`.

``` cpp
int main(int argc, char* argv[])
{

}
```

* This snippet defines the `main` function.
* This function is the **entry-point** of the program. When the program starts, **main** is always called.
* `int` means that the `main` function **returns** an **integer**. This function returns an integer **exit-code**, which tells the OS whether the program succeeded or not.
* We place brackets / parenthesis `()` after the function name to show that this is a function we are declaring, not just a variable.
* Inside these brackets, we can place **parameters**. Parameters are essentially bits of data that a function can recieve, in order to tell it what to do. This way, functions can return or do different things based on the **arguments** (data) they were given.
* `int argc` declares an **integer** parameter called `argc`. This parameter stores the **number of command-line arguments** that were passed to the program. We will learn more about this in a later chapter.
* `char* argv[]` does a similar thing, but instead stores an **array** of the command-line arguments. Once again, we will learn more about this parameter in a future chapter.
* Finally, the **curly braces** `{}` are used to define the **function body**. Essentially, anything inside the braces is part of that function body. The curly braces go **after** the function parameters.

``` cpp
std::cout << "Hello C++";
```

* The `cout` stream 
