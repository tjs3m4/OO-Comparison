[Main Page](README.md)

# Classes
-------------------------
C#
===
A class in C#: 
```C#
class SomeClass
{
	SomeClass() //constructor
	{
		// do something
	}
	private	int data;
	public int data2;
	{
		get
		{
			return data2;
		}
		protected set
		{
			data2 = value;
		}
	}
}

// to create instance
SomeClass obj = new SomeClass();
```
`get` and `set` can be assigned access levels. By default, they have the same access level as the property they are assigned to.  

To refer to an instance of/in the class from within the class itself use the `this` keyword. 

C# supports the following access modifiers: `public` `protected` `interal` `private` and `protected internal`

The default access level for members of a class is the minimum possible access for a member of that class. This depends largely on the specific member of the class.

The differences between `struct` and `class`:  
	1: `struct` is a value type while `class` is a reference type  
	2: `struct` does not support inheritance or polymorphism, but a `class` does  
	3: default access for members of a `struct` is `public` while default access for members of a `class` is `private`  

Despite having the object type, there is no base class that all classes inherit from in C# as there is in Java. The object type is not a class.  

Like C++, C# also supports destructors, however; these are usually omitted because C# has a garbage collector. Because they are usually omitted, they will be left out of the class example.  

C++
===
A class in C++:  
```C++
class SomeClass
{
	private:
		int data1;
		int data2;
	public: 
		SomeClass() //constructor
		{
			// do something
		}
		~SomeClass() //destructor
		{
			// do something
		}
		int getData()
		{
			return data1;
		}
};

	// two ways to create an instance
	SomeClass b(1);
	SomeClass *a = new SomeClass(1);
	
	//using different instances
	std::cout << a->getData();
	std::cout << b.getData();
```
To refer to an instance of/in the class from within the class itself use the `this` keyword.

One difference you might notice right away is that C++ classes can have destructors. These are not required, but are usually used to release resources allocated by the class. Destructors are called when an object is destroyed or deallocated.   

The members of a class are declared in a list-like fashion accordin to their access level. This is different from the C# syntax of declaring the access level before evey member of the class.  

C++ supports three access modifiers: `public` `private` and `protected`  
The default access level for members of a class is `private`  

The only differences between a `struct` and a `class` in C++ are  
	1: Default access for a `struct` is `public` while default access for a `class` is `private`  
	2: On inheritance, `struct` defaults to public inheritance while `class` defaults to private inheritance  

An interesting difference between `struct` in C++ and C# is that in C++ `struct` supports inheritance.  

Private inheritance means that, when a derived class inherits from a base class, the public and protected members of the base class become private members of the derived class. For public inheritance, the access level of members derived from the base class remains the same.  

There is no base class that all classes inherit from in C++.