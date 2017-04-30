[Main Page](README.md)

# Reflection
-------------------------
C#
===
C# supports reflection by use of `Type` in the `System` namespace, i.e: `System.Type`.  
Type is an object that holds an object type.  
```C#
int x = 1;  
System.Type type = x.GetType();  
System.Console.WriteLine(type);  //output is: System.Int32
```
`Type` isn't the only reflexive object in C#, many others are available to give details about elements in your project.  

C++
===
C++ as a base language does not support reflection. 