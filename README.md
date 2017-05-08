# MomentUDT

The **type system** in *C++* is very powerful and I have not seen many people using it. Using (correctly) the features of *C++* can help us to **write better, safer and faster code**. 

MomentUDT is a library prototype for people who want to learn how to use the type system of *C++*, learning it from a real world example.

A library for manipulating dates is a perfect example to show all the benefits of the **User-Defined Types (UDT)**. Many people would use C and C++ primitives to write a library like that (ints, floats, etc). However many errors can be derived if you uses primitives. The compiler would not be able to complain if you write something like this:

```cpp
auto year = 2017; // Actual year

// Add 10 years to the year variable
auto ten_years_ahead = year + 10; // Welcome to the future

// It does not make any seanse to add to years!!
auto another_year = year + ten_years_ahead;
```

It is well known that it is better to catch as many bugs at **compile time** as possible and the *type system* can help us with it. 

The *type system* helps us to reason about our code in a more natural way. Given the constructor: 

```cpp
Date(int, int, int);
```

we have no idea (without reading the documentation or the code comments) how that functions has to be used. Does Date receive the parameters as `Date(Year, Month, Day)`? Is it using the European format `Date(Day, Month, Year)` or the American one `Date(Month, Day, Year)`? A type alias can help with the expressivity but not the correctness:

```cpp
using Year = int;
using Month = int;
using Day = int;

Date(Month, Day, Year);
```

What we want is the compiler checking the types of each parameter, we want something like this:

```cpp
Day d(15);
Month m(1);
Year y(2017);

Date(m, d, y); // Compiles without any problem
Date(d, m, y); // Error, type of d shuld be Month and type of m should be Day
```
An we do not want to compromise our performance, or do it as little as possible, so we are looking for a zero-cost overhead solution


## User-Define Types in C++


```cpp

```

We can see a pattern in this class that. We do not want to copy and paste the same code again and again changhing the name of the classes so we are going to generalize it using templates:

```cpp

```

If we want to go even further we can add some range checking at compile time that will take care of having a Year which value is too big (or small):

```cpp

```


## Conclusion


