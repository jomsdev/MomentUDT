# libMoment

*libMoment* is a *C++* library for parsing, validating, manipulating, and formatting dates. It is heavely inspired in a Javascript library called [moment.js](http://momentjs.com/).

This library is an exemple for people who want to learn how to use the type system of *C++*, learning it from a real world example.

The **type system** in *C++* is very powerful and I have not seen many people using it. Using the features of *C++* can help us to **write better, safer and faster code**. 

A library for manipulating dates is a perfect example to show all the benefits of the User-Defined Types (UDT). Many people would use C and C++ primitives to write a library like that (ints, floats, etc). However many errors can be derived if you uses primitives, the compiler would not complain if you write something like this:

```cpp
auto year = 2017; // Actual year

// Add 10 years to the year variable
auto ten_years_ahead = year + 10; // Welcome to the future

// It does not make any seanse to add to years!!
auto another_year = year + ten_years_ahead;
```

It is well known that we want to catch as many bugs at **compile time** as possible and the type system can help us with it. 

The type system helps us to reason about our code in a more natural way. Given the constructor 

```cpp
Date(int, int, int);
```

we have no idea (without reading the documentation or the code comments) how that functions has to be used. Does Date receive the parameters as `Date(Year, Month, Day)`? Is it using the European format `Date(Day, Month, Year)` or the American one `Date(Month, Day, Year)`? A type alias can help with the expressivity but not the correctness

```cpp
using Year = int;
using Month = int;
using Day = int;

Date(Month, Day, Year);
```

