[Main Page](README.md)

# Unique Features
-------------------------
C#
===
C# runs off of microsofts .NET framework. The .NET framework provides a library of classes and functions for the C# language to use. The .NET framework also contains the common language runtime, which handles core services like memory management and threading during runtime.  

C++
===
Friend class:  
A friend class is capable of accessing the private and protected members of the class declared as its friend.
```C++
class B 
{
    friend class A;

	private:
    	int x;
};

class A 
{
	public: 
    	A(B b)
    	{
        	b.i = 0; 	//able to access due to friend
    	}
};
```
Note that friendships are not symmetric. If A is a friend of B, B is not a friend of A unless it is declared in the class.  
Friendships are not inherited, nor are they transitive.