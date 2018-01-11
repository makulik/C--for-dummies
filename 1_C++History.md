[TOC ![[\^]](./circled-up.png)](./TOC) . [2 Simple Starters ![[->]](./circled-right.png)](./2_SimpleStarters)

# 1 A bit of C++ History

<a name="1_1"/>

## 1.1 The Origins

 - In **1979** [Bjarne Sroustrup](http://stroustrup.com/) a danish computer scientist began to work on an extension to the C programming language called _"C with Classes"_. In these years software engineers were researching about better ways of structuring larger software systems as these became of more importance in industry.  
The idea of _object oriented programming_ (basically: _"Encapsulate data structures together with the functions, that should operate on them, in modules called classes."_) came up, and a number of new programming languages were invented to realize these concepts (namely Simula, Smalltalk, Eiffel) around the decade of the C++ language origins.  
One of the strengths vs other languages C++ inherited from C until nowadays, is that it is a compiled language (i.e. everything is translated to executable machine code and no interpreter engine is needed to execute a program).
 - In **1983**, _"C with Classes"_ was renamed to _"C++"_, inspired from C's numerical increment operator, and the common usage to add a "+" to indicate enhancements for a software artifact.
 - In **1985** the 1st edition of Stroustrup's book _"The C++ Programming Language"_ was published, and commonly used as a reference before ISO standardization. At that time many basic language features like _type-safety_, _virtual-polymorphism_, _function-_ and _operator-overloading_ were already introduced at that time.
 - In **1989**, C++ 2.0 was released, followed by the updated second edition of The C++ Programming Language in **1991**. Some very essential language features like _templates_, _exceptions_ and _namespaces_ were introduced, and gave a stable base to evolve the language further using a _standard template library_. Some early contributors,- even before standardization -, were [Alexander Stepanov](https://en.wikipedia.org/wiki/Alexander_Stepanov), AT&T Bell Labs and Hewlett Packard Research Labs.
 - In **1998** C++ was established as an ISO standard. New language features or deprecation of language features is managed by an ISO Working Group (subcommittee) [ISO/IEC JTC 1/SC 22](https://en.wikipedia.org/wiki/ISO/IEC_JTC_1/SC_22)
 
<a name="1_2"/>

## 1.2 Standardization 

The original C++98 ISO standard evolved with a number of improvements and additions over the recent decades:

| Year | C++ Standard       | Informal Name |
|------|--------------------|:-------------:|
| 1998 | ISO/IEC 14882:1998 | c++98         |
| 2003 | ISO/IEC 14882:2003 | c++03         |
| 2011 | [ISO/IEC 14882:2011](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2012/n3337.pdf) | c++11         |
| 2014 | [ISO/IEC 14882:2014](https://github.com/cplusplus/draft/blob/master/papers/n4140.pdf?raw=true) | c++14         |
| 2017 | [ISO/IEC 14882:2017](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/n4659.pdf) | c++17         |
| 2020 | [ISO/IEC 14882:2020](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/n4713.pdf) | c++20         |

A major number of significant improvements and new language features were introduced with the c++11 standard, specifically

 - The [`auto`](http://en.cppreference.com/w/cpp/language/auto) keyword for automatic type deduction
 - Range based loop syntax [`for(auto item : container) {}`](http://en.cppreference.com/w/cpp/language/range-for)
 - Variadic templates (parameter packs) [`template<typename ...Types>`](http://en.cppreference.com/w/cpp/language/parameter_pack)
 - Threading support [`std::thread`](http://en.cppreference.com/w/cpp/memory/weak_ptr)
 - Dynamic memory management: [`std::unique_ptr`](http://en.cppreference.com/w/cpp/memory/unique_ptr), [`std::shared_ptr`](http://en.cppreference.com/w/cpp/memory/shared_ptr), [`std::weak_ptr`]()
 - Date and Time utilities: [`std::chrono`](http://en.cppreference.com/w/cpp/chrono)
 - and many more ...
 
 One frequent source of new standard proposals and standardized libraries is the [`boost` c++ libraries project](http://www.boost.org/). Beyond standards you can use these to cover up lacking features with many pre C++11 compilers.
 
 And there's more to come in the future (established) standards, like 
 
  - [`std::filesystem`](http://en.cppreference.com/w/cpp/filesystem) (c++17)
  - _monad_ like types as [`std::optional`](http://en.cppreference.com/w/cpp/utility/optional), [`std::variant`](http://en.cppreference.com/w/cpp/utility/variant), [`std::any`](http://en.cppreference.com/w/cpp/utility/any) (c++17)

