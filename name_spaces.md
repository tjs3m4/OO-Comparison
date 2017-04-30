[Main Page](README.md)

# Name Spaces
-------------------------
C#
===
Whether or not a namespace is declared in a C# file, the compiler will add a default one.
The default namespace for the file is determined by the file path.
To declare a namespace in C#, use the keyword `namespace` and include its members much like you would do for a class.
```C#
namespace ExampleNamespace  
{  
	class ExampleClass  
	{  
		void exampleFunction (int x)  
		{  
			System.Console.Write("Value of x: ")  
			System.Console.WriteLine(x);  
		}  
	}  
}  
```
To use a namespace, write its name, a ".", then the class, function, value, etc associate with that namespace.
```C#
ExampleNamespace.ExampleClass.exampleFunction(x);  
```
or
```C#
System.Console.WriteLine("System is a namespace!");  
```
Alternatively, use the keyword "using" followed by the name of the namespace you want to use.  
```C#
using ExampleNamespace;
ExampleClass.exampleFunction(x);
```
or
```C#
using System;  
Console.WriteLine("System is a namespace!");  
```

C++
===
To use a namespace, one can either use the keyword `using namespace` or by using the namespace specifier `::` where a namespace name is given before the first colon, and a member of that namespace is given after the second.  
All standard library functions in C++ are nested inside of the "std" namespace.  
```C++
using namespace std;
cout<<"Hello World!";
```
or
```C++
std::cout<<"Hello World!";
```
To declare a namespace in C++, use the `namespace` keyword just like in C#.
```C++
namespace ExampleNamespace  
{  
	class ExampleClass  
	{  
		void exampleFunction (int x)  
		{  
			std::cout<<"Value of x: "<<x;
		}  
	};
}  
```
To use it:
```C++
using namespace ExampleClass;
ExampleClass.exampleFunction(x);
```

```C++
ExampleNamespace::ExampleClass.exampleFunction(x);
```
An interesting difference in syntax between the two languages: C++ ends class declarations with a `;` while C# does not.  