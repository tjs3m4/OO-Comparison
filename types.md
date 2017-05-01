[Main Page](README.md)

# Types
-------------------------
C#
===
Value Types:  
--------
The following primitive data types are build into C#:  
`bool` `byte` `char` `decimal` `double` `float` `int` `long` `sbyte` `short` `uint` `ulong` `ushort`  

These types are aliases for their equivalents inside of the .NET framework. For example: `int` and `System.Int32` are the same thing.  

C# also supports the following value types:   
Enumerations, by use of the `enum` keyword:  
```C#
enum Direction = {North, South, East, West};
```
Structs by use of the `struct` keyword:
```C#
public struct Pencil
{
	public String color;
	public double price;

	//structs can also have constructors, although not necessary
	Pencil() {} //standard constructor
	Pencil(String col, int p)
	{
		color = col;
		price = p;
	}
}

static void Main()
{
	pencil1 = new Pencil();
	pencil2 = new Pencil("Red", 1.50);
	//...
}
```
Note that structs can also support functions.   

C# also has the following Reference Types:  
---
`object` `dynamic` `String`  

`object` and `dynamic` types can hold any other type.  
Converting a value type to an object type is called boxing.  

```C#
// an example of boxing
object obj;
int x = 50;
obj = x;
```

Converting an object type to a value type is called unboxing. 
```C#
// an example of unboxing
object obj = 50;
int x;
x = (int)obj;
``` 

The only difference between `object` and `dynamic` types is that, for 'dynamic' types, type checking takes place at run time, while for `object` types, type checking takes place at compile time.  

Strings are derived from the object type:  
```C#
String someStr = "Some text";
``` 
[Classes](class.md) (derived from object)

C# and C++ both support pointers with the same functionality.  

Creating a container to hold any type of object in C# can be done simply with the object data type. This is not so simple in C++.

C++
===
Value Types:
---
The following primitive data types are build into C++:  
`bool` `char` `int` `float` `double` `void` `wchar_t`  
These primitive data types can be modified with the following keywords:  
`signed` `unsigned` `short` `long`  

C++ also supports:  
Enumerations by use of the `enum` keyword:
```C++
enum Direction = {North, South, East, West};
```
Structs by use of the `struct` keyword:
```C++
struct Pencil
{
	std::string color;
	double price;

	//structs can also have constructors, although not necessary
	Pencil() {} //standard constructor
	Pencil(std::string col, int p)
	{
		color = col;
		price = p;
	}
};

void main()
{
	Pencil pencil1;
	Pencil pencil2("Red", 1.50);
	std::cout<<pencil2.color;
}
```
Strings by use of the keyword 'std::string' and include '#include<string>':
```C++
std::exampleStr = "Some text";
```

Note that structs can also support functions.  

[Classes](class.md)

C++ Reference Types: 
--- 
C++ by itself does not have any default reference types, but it does support a reference operator.  
In C++, a reference is just like a pointer, but after being initialized, a reference cannot be set to a different value. An lvalue reference is used to refer to a named variable, and an rvalue is used to refer to a temporary object.  
Creating lvalue references with the `&` operator:  
```C++
int &i;
std::string &str;
```
rvalue references are created using the `&&` operator.  

Because C++ is a type strict language, creating a container to hold objects of different types must be done using some sort of template class.