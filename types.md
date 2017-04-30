[Main Page](README.md)

# Types
-------------------------
C#
===
Value Types:  
--------
The following primitive data types are build into C#:  
`bool` `byte` `char` `decimal` `double` `float` `int` `long` `sbyte` `short` `uint` `ulong` `ushort`  

C# also supports the following value types:   
Enumerations, by use of the `enum` keyword:  
```C#
emnum Direction = {North, South, East, West};
```
Structs by use of the `struct` keyword:
```C#
public struct pencil
{
	public String color;
	public double price;
}
```

These types are assigned to a variable by value.  

C# also has the following Reference Types:  
---
'object' 'dynamic' `String`  

'object' and 'dynamic' types can hold any other type.  
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

The only difference between 'object' and 'dynamic' types is that, for 'dynamic' types, type checking takes place at run time, while for 'object' types, type checking takes place at compile time.  

Strings are derived from the object type:  
```C#
String someStr = "Some text";
``` 

C# and C++ both support pointers with the same functionality.

C++
===
Value Types:
---
The following primitive data types are build into C++:  
`bool` `char` `int` `float` `double` `void` `wchar_t`  
These primitive data types can be modified with the following keywords:  
`signed` `unsigned` `short` `long`  