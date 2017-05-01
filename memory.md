[Main Page](README.md)

# Memory Management
-------------------------
C#
===
For most objects that you create in C#, you don't have to worry about managing their memory. The .NET framework's garbage collector will take care of that for you. However, there are some types of unmanaged resources that the garbage collector does not know how to handle.


C++
===
In C++, you are pretty much left up to your own devices to allocate and deallocate memory.  
There is a `libgc` library that includes a garbage collector, but it is optional. This makes garbage collection in C++ a lot different than most other higher level languages, where garbage collection is imposed.

Memory allocation is usually handled by the objects themselves, so you wont't find youself calling `malloc()` everywhere like you would in C.  

Any `new` in your code should be followed by a `delete` to free the memory allocated to that new object.  

C++ does include some things to make cleaning up after yourself a little easier:  
    Destructors are implemented in a similiar fashion to constructors within a class:  
        `ClassA() {}` is a constructor of ClassA, `~ClassA() {}` is a destructor of ClassA.  
        Destructors are called when the object that it is a member of gets destroyed. The destructor is typically used to deallocate any resources that you might have allocated to the class over its lifetime.  
    Modern C++ also supports smart pointers:
        A smart pointer is similiar to modern garbage collection ideas, where an object will be deleted when it is no longer being referenced. A smart pointer will keep track of, and delete the memory of the raw pointer that it is assigned to.  

Smart pointer example:
```C++
// assume ClassA declaration

void func()
{
	unique_ptr<ClassA> objA();
	// use objA
}
	//	obj A is deleted on function exit
```