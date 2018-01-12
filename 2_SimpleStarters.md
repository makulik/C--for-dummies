[![[&lt;-]](./circled-left.png) 1 A bit of C++ History](./1_C++History) | [TOC ![[\^]](./circled-up.png)](./TOC) | [3 Some inevitable basics ![[->]](./circled-right.png)](./3_BasicFeatures)

# 2 Simple Starters

<a name="2_1"/>

## 2.1 The C++ _Hello World!_ example dissected

As probably every programming language does, C++ provides a minimal, valid and complete program, that actually does something 

```c++
#include <iostream>
int main() {
    std::cout << "Hello World!" << std::endl;
}
```

[**Live Demo**](https://wandbox.org/permlink/AURk59CGTaIBB3oP)<sup><a href="#footnote_1">1</a></sup>

Let's dissect this a bit further regarding the syntax you see:

 1. **Preprocessor Statements**  
    All lines introduced with a `#` are handled by the [c/c++ precprocessor](http://en.cppreference.com/w/cpp/preprocessor). The `#include` statement specifically replaces it's occurrence with the complete text found in the file specified in `<file>` angle brackets or `"file"` quotes.  
    These files contain declarations, that are needed to properly resolve stuff that's mentioned in the following code lines.
 2. **The `main()` program entry point**  
    Any executable C++ program needs to have a defintion for a function existing in the global `namespace ::` called `main`.  
    The full (and only valid) signature of this function looks like
    
    ```c++
    int main(int, char*[]);
    ```
    The parameters can be omitted in your definition, if you don't need to use them (as in the example above).  
    Also (unlike with any other typed function definitions), it's OK to omit the obligatory `return` statement in the `main()` function.
 3. **Function Definitions**  
    A statement like 
    ```c++
    int function_name() { /* ...*/ }
    ```
    is a function _definition_. All the code introduced between the `{}` curly braces will be executed, when that function is called somewhere (for the `main()` function this call is implicit when you run the compiled program).
 4. **Statements**  
    Generally any statements in C++ are closed up with a `;` semicolon. A bunch of statements can be grouped within a pair of `{}` curly braces. The latter group compounds are commonly called a _scope_.
 5. **What does that `std::` mean?**  
    C++ has a concept of [`namespace`s](http://en.cppreference.com/w/cpp/language/namespace), where any _symbol declarations_ can be made unique throughout a specific compilation context. A prefix like that makes the compiler looking up to resolve it within that specific qualified scope (either `namespace` or _type declaration_).
    The namespace `std` was chosen to indicate any guaranteed implementations of the C++ standard library according what's supported with your current C++ compiler
 6. **`std::cout`, what is that actually?**  
    That's the _standard output_ binding you can use to give some feedback from your program.  
    Usually this enables you to output some text to a terminal, when your program is executed in that terminal.  
   [`std::cout`](http://en.cppreference.com/w/cpp/io/cout) is a global object introduced with the `iostream` header, that implements the [`std::ostream`](http://en.cppreference.com/w/cpp/io/basic_ostream) interface.
 7. **... and what does the `<<` do?**  
    This calls an [overloaded `operator<<()` function](http://en.cppreference.com/w/cpp/io/basic_ostream/operator_ltlt) with a signature like follows:
    ```c++
    template<typename T>
    std::ostream& operator<<(std::ostream&, const T&);
    ```
    The type of the `"Hello World!"` character literal will be `const char[13]` and there's a specialization chosen from the [C++ standard library](http://en.cppreference.com/w/cpp/io/basic_ostream/operator_ltlt2):
    
    ```c++
    template< class Traits >
    basic_ostream<char,Traits>& operator<<( basic_ostream<char,Traits>& os, 
                                            const signed char* s );
    ```
    
    and `const char[13]` decays to a `const signed char*` pointer. Thus this function is called.
 8. **The `std::endl`**  
    Is a so called [I/O manipulator](http://en.cppreference.com/w/cpp/io/manip). It renders a line ending at it's `std::ostream&` parameter, and forces the (_buffered_) stream to commit the outputs to a physical device (like a terminal).
    
----------------------------------------------

After reading this, I almost could hear you scream (maybe even completely new to terms of programming at all):

**Are you serious?? _"Simple starters"_?!?**  
_"You use a bunch of confusing terms, completely beyond my knowledge!"_

The **good things** for you to know now are:  
 - You should't bother too much about in depth understanding of that dissected syntax above, and how that works in detail
 - It simply works out of the box, and using the C++ standard library can keep it portable
 - You can concentrate about your custom data structures and how best to represent these by means of using C++ standard library containers and Dynamic memory Management.
 
There are two paths from here:
 1. You need to gather more knowledge about _programming_, _programming languages_ _data structures_ and _algorithms_ in general, before digging deeper into the concepts of any specific programming language
 2. You follow further, and just use the C++ language
 
<a name="2_2"/>

## 2.2 The C++ _Hello Universe!_ example

The above example only interacts with _the world_ in one direction. Naturally the purpose of a program is to 

 - take some _input_ ... 
 - ... _process it_ ...
 - ... and _produce_ some _output_.

Here's a very simple example of one way to achieve that with C++ code:

```c++
#include <iostream>
#include <string>

int main() {
    std::string username;
    std::cout << "Enter your name please: ";
    std::getline(std::cin,username);
    
    std::cout << "\nHello Universe! My name is '" << username << '\'' << std::endl;
}
```

Let's dissect further what was added there:

 1. **`#include <string>`**  
    Another included C++ standard class declaration. [`std::string`](http://en.cppreference.com/w/cpp/string) is the class you use to deal with text data.
 2. **`std::string username;`**  
    This is a _variable_ declaration. `username` is an object instance of the `std::string` class, wich is capable to store an arbitrary sequence of characters, just as they appeared in the in the `"Hello World!"` character literal.
 3. **`std::getline(std::cin,username);`**  
    Takes the characters typed in at the terminal until the <kbd>ENTER</kbd> key is hit, and stores these in the `username` variable.
    
 4. The rest is much as from the _Hello World!_ example. A variable (like `username`) can be rendered as text output using the `std::ostream& operator<<(std::ostream&,T)` overload, and that will work for certain variable types (like e.g. `int`, `double`, `std::string`, etc.).

 5. **So what's this `\` stuff used there?**  
    That's called _character literal escaping_. To render special characters like a line ending (`'\n'`), or even characters that are used to define _literals_, these can be represented in the code using a prefixed `\`.  
    Think about the literal delimiter characters `"` and `'` in particular. To represent these inbetween those delimiters, they need to be _escaped_ from being counted as delimter characters.
 
----------------------------------------------

<a name="footnote_1" />

<sup>1)</sup>
Most code examples can be explored without having a c++ compiler toolchain or IDE installed at your local machine. Feel free to fork from these example codes, and play around with them using [Wandbox](https://wandbox.org)
