[Main Page](README.md)

# Interfaces and Inheritance
-------------------------
C#
===
```C#
interface Shape
{
	int calculateArea();
	int x
	{
		get;
		set;
	}
	int y
	{
		get;
		set;
	}
}

class Circle : Shape
{
	private int radius;
	public int calculateArea()
	{
		return 3.14 * (radius * radius);
	}
}
```
C# does not support access level specifiers on extenstion.  

C++
===

C++ interfaces are where things start to get a little messy.  

C++ does not have interfaces but their functionality can be recreated by use of an abstract class.
An abstract class is made in C++ by making one of the class's functions a pure virtual function.

A pure virtual function is created by adding the keyword `virtual` before the return type specifier, and `= 0` after the function declaration. The Inheriting class can then override the functions in the abstract class.  

C++ allows for the overriding of functions only if the function is declared as a virtual function within the class by use of the keyword `virtual`. A virtual function is one that is expected to be overriden in the derived class, while a pure virtual function is one that MUST be overriden. Failure to to do will result in a compile error.  

Overriding can be done by having a function with the same signature as the virtual function in the base class. It is up to the programmer to decide whether or not to add the optional `override` keyword at the end of the function declaration.  
```C++
// assuming foo() exists in the base class and is a virtual function
void foo()
{
	// do something
}

```
or
```C++
// assuming foo() exists in the base class and is a virtual function
void foo() override
{
	// do something
}
```

Abstract classes cannot be instantiated, and a class inheriting from the abstract class must implement the pure virtual function. Note that only the pure virtual function must be overridden.

Extending a class in C++ is done by the following:  
```C++
class InheritingClass: public BaseClass
{
	// class specifications
}
```
The access level specifier on the BaseClass limits the access level of members that are inherited from the base class. What this means is that members with a higher access level will be inherited with the specified access level instead. Because public is the highest access level, specifying public effectively does nothing, but if private was used, any inherited member of BaseClass would become private inside of InheritingClass. If no access level specifier is given, `class` default to private inheritance, and `struct` defaults to public inheritance.  

An example abstract class and inheritance:
```C++
class Shape // base class
{
	public:
		virtual int calculateArea() = 0;

		void setLocation(int locx, int locy)
		{
			x = locx;
			y = locy;
		}
	protected:
		int x;
		int y;
};

class Circle : public Shape
{
	private:
		int radius;
	public:
		int calculateArea()
		{
			return 3.14 * (radius * radius);
		}

};
```
Abstract classes can have their own members. Note that when this class is extended, the subclass will have x and y as `private` members due to the private inheritance property of classes.  