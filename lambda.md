[Main Page](README.md)

# Lambda Expressions
-------------------------
C#
===
In C#, lambda expressions are declared by use of the token `=>`. Input variables go on the left side of the token, and the body of the expression goes on the right.  

A useful example (code from msdn.microsoft.com) shows two ways of displaying the length of the shortest string in an array of strings:  
First without a lambda expression:  
```C#
// Get the lengths of each word in the words array.  
var query = from w in words  
            select w.Length;  
// Apply the Min method to execute the query and get the shortest length.  
int shortestWordLength2 = query.Min();  
Console.WriteLine(shortestWordLength2);  
```
With a lambda expression:  
```C#
// Use method syntax to apply a lambda expression to each element of the words array.
int shortestWordLength = words.Min(w => w.Length);  
Console.WriteLine(shortestWordLength);
```

C++
===
C++11 brought lambda expressions to C++.  
In C++ a lambda function is specified by use of `[]` before the function declaration. For example:  
```C++
// basic lambda syntax
auto func = [] () 
{ 
	std::cout << "Hello world"; 
};
func(); // function call
```
Note that the type specifier `auto` allows us to let the compiler determine the type of variable, rather than us declaring the variable's specific type.

A more useful example (code from msdn.microsoft.com):  
the `std::sort` function uses a lambda expression as its third argument to specify how elements should be sorted:  
```C++
#include <algorithm>  
#include <cmath>  
  
void abssort(float* x, unsigned n) {  
    std::sort(x, x + n,  
        // Lambda expression begins  
        [](float a, float b) {  
            return (std::abs(a) < std::abs(b));  
        } // end of lambda expression  
    );  
} 
```
