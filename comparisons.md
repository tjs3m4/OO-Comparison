[Main Page](README.md)

# Comparisons
-------------------------
C#
===

Even though strings are reference types in C#, the `==` operator can be used to compare their values. This is because the `==` operator is defined by the language to compare the values of string objects, not their references.  
For example:
```C#
string str1 = "abc";
string str2 = "abc";
Console.WriteLine(str1 == str2); 	// output is "True"
Console.WriteLine(str1 == str2);	// output is "False"
```
In the above example, str1 and str2 hold the same values but do not refer to the same instance of string.  

In addition to `==` C# has other built in functions that can compare the values of two strings, such as `String.Equals`. Note that this uses the `String` class, but in C# `string` is just an alias for the `String` class. Both keywords mean the exact same thing.  

To represent null/nil values, C# uses the value `null`.

C++
===
Because strings are value types in C++, the following comparison to check if two strings contain the same letters is valid:
```C++
std::string str1 = "abc";
std::string str2 = "abc";
if (str1 == str2)
	std::cout<<"The strings are the same!";

// output: "The strings are the same!"
```
```C++
std::string str1 = "abc";
std::string str2 = "xyz";
if (str1 == str2)
	std::cout<<"The strings are NOT the same!";

// output: "The strings are NOT the same!"
```
There are also built in string comparison functions you can use to compare strings. This would be more useful than `==` if you were dealing with something like a character array, where the variable holds a pointer.  

To represent null/nil values, C++ uses the values `nullptr` and `NULL`. For most cases, the two are equivalent, but for clarity and to prevent some possible issues, `nullptr` should be used for pointer types and `NULL` should be used for other types.