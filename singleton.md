[Main Page](README.md)

# Singletons
-------------------------
C#
===

C++
==
```C++
class Singleton
{
	public:
		static Singleton& getInstance(); 	// will return a reference to the instance
		{									// see types page for more info on C++ references
			static Singleton instance;
			return instance;
		}
	private:
		Singleton();
};
```
In C++11, initialization of static local variables is thread-safe, so because the instance of our singleton is a static local variable, this singleton is also thread safe.