[Main Page](README.md)

# Name Spaces
-------------------------
C#
===
Whether or not a namespace is declared in a C# file, the compiler will add a default one. 
To declare a namespace in C#, use the keyword "namespace" and include its members much like you would do for a class.
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