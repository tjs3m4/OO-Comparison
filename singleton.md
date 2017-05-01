[Main Page](README.md)

# Singletons
-------------------------
C#
===
Creating a singleton in C#:  
```C#
public class Singleton
{
	private static Singleton instance
	{
		get
		{
			if (instance == null)
			{
				instance = new Singleton();
			}
			return instance;
		}
	}
	private Singleton()
	{
		//constructor
	}

}
```
The problem with the above implementation is that it is not thread safe.  

A thread safe implementation (from msdn.microsoft.com):
```C#
using System;

public sealed class Singleton
{
   private static volatile Singleton instance;
   private static object syncRoot = new Object();

   private Singleton() {}

   public static Singleton Instance
   {
      get 
      {
         if (instance == null) 
         {
            lock (syncRoot) 
            {
               if (instance == null) 
                  instance = new Singleton();
            }
         }

         return instance;
      }
   }
}
```
The above implementation uses the `lock` block to allow only a single thread to enter it, thus preventing multiple threads from creating an instance of the singleton at the same time.  

C++
==
Creating a singleton in C++:  
```C++
class Singleton
{
private:
	static Singleton *instance;
	Singleton()
	{
		// private constructor
	}
public:
	static Singleton* getInstance()
	{
		if (instance == nullptr)
		{
			instance = new Singleton();
			return instance;
		}
		else
		{
			return instance;
		}
	}
};

// static members cannot be initialized outside of the class
Singleton* Singleton::instance = nullptr;	//be sure to initialize the instance to nullptr

// to create the instance
Singleton *a = Singleton::getInstance();		// because this is a static funciton, we
												// use Singleton namespace and the function
```
In C++11, initialization of static local variables is thread-safe, so because the instance of our singleton is a static local variable, this singleton is also thread safe.