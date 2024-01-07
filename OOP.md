# Object Oriented Programming Using Python

<hr>

### Object Oriented Programming in Python
Object-oriented programming (OOP) is a programming paradigm that allows you to create modular and reusable code by organizing data and behavior into objects. Python supports OOP, and in this answer, we'll cover some of the basic concepts of OOP in Python.

**Classes and Objects**
The building block of OOP in Python is a class. A class is a blueprint or template for creating objects. An object is an instance of a class, and it has its own unique data and behavior.

Here's an example of a simple class in Python:

<pre>
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")
</pre>

In this example, we have defined a class called Person. The &lowbar;&lowbar;init&lowbar;&lowbar; method is a special method in Python that is called when an object is created. It initializes the object with the given name and age attributes. The greet method is a simple method that prints a message introducing the person.

To create an object of the Person class, we can do the following:

<pre>
person = Person("Alice", 25)
person.greet()  # prints "Hello, my name is Alice and I am 25 years old."
</pre>

In this example, we have created a Person object with the name "Alice" and the age 25. We have then called the greet method on the person object, which prints a message introducing the person.

**Inheritance**<br><br>
One of the key features of OOP is inheritance. Inheritance allows you to create a new class that is a modified version of an existing class. The new class inherits the data and behavior of the existing class, but can also add its own data and behavior.

Here's an example of a Student class that inherits from the Person class:

<pre>
class Student(Person):
    def __init__(self, name, age, grade):
        super().__init__(name, age)
        self.grade = grade

    def study(self):
        print(f"{self.name} is studying hard for the {self.grade} exam.")
</pre>

In this example, we have defined a Student class that inherits from the Person class. The &lowbar;&lowbar;init&lowbar;&lowbar; method of the Student class calls the &lowbar;&lowbar;init&lowbar;&lowbar; method of the Person class using the super() function, and then sets the grade attribute. The study method is a new method that is specific to the Student class.

To create a Student object, we can do the following:

<pre>
student = Student("Bob", 20, "history")
student.greet()  # prints "Hello, my name is Bob and I am 20 years old."
student.study()  # prints "Bob is studying hard for the history exam."
</pre>

In this example, we have created a Student object with the name "Bob", the age 20, and the grade "history". We have then called the greet method on the student object, which prints a message introducing the student, and the study method, which prints a message indicating that the student is studying.

**Polymorphism**<br><br>
Another key feature of OOP is polymorphism. Polymorphism allows you to use a single interface to represent multiple types of objects. In Python, polymorphism is achieved through method overriding and method overloading.

Method overriding is when a subclass provides its own implementation of a method

<hr>

### Static and Instance variables in Python
In Python, there are two types of variables: static variables and instance variables.

Static variables are shared across all instances of a class. They are defined inside the class, but outside of any method. You can access a static variable using the class name or an instance of the class. Here's an example:

<pre>
class MyClass:
    static_var = 0  # This is a static variable

    def __init__(self, instance_var):
        self.instance_var = instance_var  # This is an instance variable
</pre>

In this example, static_var is a static variable that is shared across all instances of the MyClass class. You can access it using the class name:

<pre>
print(MyClass.static_var)  # prints "0"
</pre>

You can also access it using an instance of the class:

<pre>
obj = MyClass(10)
print(obj.static_var)  # prints "0"
</pre>

However, if you change the value of a static variable using an instance of the class, it will only affect that instance and not the class as a whole:

<pre>
obj.static_var = 1
print(MyClass.static_var)  # prints "0"
print(obj.static_var)      # prints "1"
</pre>

Instance variables, on the other hand, are unique to each instance of a class. They are defined inside the &lowbar;&lowbar;init&lowbar;&lowbar; method and are accessed using the self keyword. Here's an example:

<pre>
class MyClass:
    static_var = 0  # This is a static variable

    def __init__(self, instance_var):
        self.instance_var = instance_var  # This is an instance variable
</pre>

In this example, instance_var is an instance variable that is unique to each instance of the MyClass class. You can access it using an instance of the class:

<pre>
obj = MyClass(10)
print(obj.instance_var)  # prints "10"
</pre>

Each instance of the class has its own copy of the instance variable, which can be set independently:

<pre>
obj1 = MyClass(10)
obj2 = MyClass(20)
print(obj1.instance_var)  # prints "10"
print(obj2.instance_var)  # prints "20"
</pre>

In summary, static variables are shared across all instances of a class, while instance variables are unique to each instance of a class. Both types of variables can be useful in different situations, depending on the needs of your program.

<hr>

### Instance, Class and Static methods in Python
In Python, there are three types of methods that can be defined within a class: instance methods, class methods, and static methods.

**Instance Methods:**
Instance methods are the most common type of method in Python. They are defined inside a class and operate on an instance of that class. An instance method takes the instance itself as the first argument, which is usually called "self". Using the "self" parameter, instance methods can access and modify the attributes of the instance.
Here's an example of an instance method:

<pre>
class MyClass:
    def instance_method(self, arg1, arg2):
        self.arg1 = arg1
        self.arg2 = arg2
</pre>

In this example, "instance_method" is an instance method that takes two arguments "arg1" and "arg2". It also modifies the attributes "arg1" and "arg2" of the instance using the "self" parameter.

**Class Methods:**
Class methods are methods that are bound to the class and not the instance of the class. They are defined with a special decorator "@classmethod" and take the class itself as the first argument, which is usually called "cls". Class methods can access and modify the class-level attributes and perform operations that are specific to the class.
Here's an example of a class method:

<pre>
class MyClass:
    class_attr = 0
    
    @classmethod
    def class_method(cls, arg):
        cls.class_attr += arg
</pre>

In this example, "class_method" is a class method that takes one argument "arg". It modifies the class-level attribute "class_attr" using the "cls" parameter.

**Static Methods:**
Static methods are methods that do not depend on the instance or the class. They are defined with a special decorator "@staticmethod" and do not take any special parameters. Static methods can be used to group related utility functions within a class.
Here's an example of a static method:

<pre>
class MyClass:
    @staticmethod
    def static_method(arg):
        return arg * arg
</pre>

In this example, "static_method" is a static method that takes one argument "arg". It returns the square of the argument.

To call these methods, you need to create an instance of the class for instance methods, use the class name for class methods and static methods:

<pre>
obj = MyClass()
obj.instance_method(1, 2)
MyClass.class_method(3)
MyClass.static_method(4)
</pre>

<hr>

### Magic Variables in Python (&lowbar;&lowbar;variablename&lowbar;&lowbar;)
In Python, magic variables refer to a set of predefined variables that are created and updated by the interpreter as you execute your code. These variables provide useful information about the current state of your program and can help you debug or optimize your code.

Here are some of the most commonly used magic variables in Python:

* **name:** This variable contains the name of the current module. If the module is being run as the main program, its value will be "main".

* **file:** This variable contains the filename of the current module.

* **doc:** This variable contains the docstring (documentation string) for the current module or function.

* **all:** This variable is a list of public names that should be imported when a module is imported using the "from module import *" syntax.

* **dict:** This variable contains the namespace of the current module or class.

* **dir:** This variable returns a list of all the names defined in the current namespace.

* **file and line:** These variables are used by the traceback module to report the file name and line number of an exception.

* **builtins:** This variable is a module containing all the built-in functions and variables of Python.

* **package:** This variable contains the name of the current package. If the module is not part of a package, its value will be None.

Magic variables in Python are identified by their double underscore prefix and suffix. These variables are created and updated by the Python interpreter and are not intended to be modified by the user. Instead, they provide useful information that can be used to improve the quality and efficiency of your code.

<hr>

### Magic Methods in Python (&lowbar;&lowbar;methodname&lowbar;&lowbar;)
Magic methods in Python are special methods that are identified by double underscores (e.g., init, str) and are used to define how objects of a class behave in certain situations. These methods are also known as dunder methods.

Here are some of the most commonly used magic methods in Python:

* **init(self, ...):** This method is called when an object is created and is used to initialize the object's attributes.

* **str(self):** This method is used to return a string representation of the object.

* **repr(self):** This method is used to return a string representation of the object that can be used to recreate the object.

* **eq(self, other):** This method is used to test whether two objects are equal.

* **lt(self, other):** This method is used to test whether one object is less than another.

* **gt(self, other):** This method is used to test whether one object is greater than another.

* **len(self):** This method is used to return the length of the object.

* **getitem(self, key):** This method is used to get the value of an item in the object, using the key.

* **setitem(self, key, value):** This method is used to set the value of an item in the object, using the key.

* **delitem(self, key):** This method is used to delete an item from the object, using the key.

* **iter(self):** This method is used to define an iterator for the object.

* **next(self):** This method is used to get the next item from the iterator.

* **call(self, ...):** This method is used to make an object callable like a function.

Magic methods in Python are a powerful tool for creating custom classes that behave like built-in types. By implementing these methods, you can define how objects of your class should behave in various situations, making your code more expressive and flexible.

<hr>

### Public, Protected and Private Access Modifiers in Python
In Python, there are three access modifiers that are used to control the visibility and accessibility of class members, including variables and methods. These access modifiers are:

* **Public:** By default, all class members are public in Python, which means they can be accessed from anywhere, inside or outside of the class. You can access public members using the dot notation, such as object_name.member_name.

* **Protected:** In Python, a single underscore (_) before a variable or method name indicates that it is protected. This means that the member can be accessed from within the class and its subclasses, but not from outside the class. However, this is more of a convention and not strictly enforced by the language.

* **Private:** In Python, a double underscore (__) before a variable or method name indicates that it is private. This means that the member can only be accessed from within the class, and cannot be accessed from outside the class, even from its subclasses. However, you can still access private members using the name mangling technique, which involves adding an underscore and the class name before the member name, such as object_name._class_name__member_name.

Here is an example to demonstrate these access modifiers in Python:

<pre>
class MyClass:
    def __init__(self):
        self.public_var = "This is a public variable"
        self._protected_var = "This is a protected variable"
        self.__private_var = "This is a private variable"
    
    def public_method(self):
        print("This is a public method")
    
    def _protected_method(self):
        print("This is a protected method")
    
    def __private_method(self):
        print("This is a private method")

obj = MyClass()

# Accessing public members
print(obj.public_var)  # Output: This is a public variable
obj.public_method()   # Output: This is a public method

# Accessing protected members
print(obj._protected_var)  # Output: This is a protected variable
obj._protected_method()   # Output: This is a protected method

# Accessing private members
# This will raise an AttributeError
#print(obj.__private_var)
#print(obj.__private_method)

# Accessing private members using name mangling
print(obj._MyClass__private_var)  # Output: This is a private variable
obj._MyClass__private_method()   # Output: This is a private method
</pre>

<hr>

### Inheritance in Python
Inheritance is one of the key concepts in object-oriented programming (OOP), and Python supports it fully. Inheritance allows you to define a new class that is a modified version of an existing class, which is called the parent or base class. The new class is called the child or derived class. The child class inherits all the attributes and methods of the parent class and can also add new attributes and methods or modify the existing ones.

To create a new class that inherits from an existing class, you can use the following syntax:

<pre>
class ChildClass(ParentClass):
    # class definition
</pre>

This defines a new class called ChildClass that inherits from ParentClass.

When a child class is created, it inherits all the attributes and methods of the parent class. To access these attributes and methods, you can use the super() function. For example, to call a method of the parent class, you can use:

<pre>
super().parent_method(args)
</pre>

This calls the parent_method of the parent class with the given arguments.

You can also override methods of the parent class in the child class by defining a method with the same name in the child class. This is useful when you want to modify the behavior of a method in the parent class for the child class.

In addition to methods, you can also override attributes of the parent class in the child class. For example, you can define a new value for an attribute or delete it altogether.

Inheritance in Python is a powerful feature that allows you to reuse code and create more flexible and modular programs. By using inheritance, you can create new classes that build upon existing classes, without having to rewrite code.

<hr>

### Different types of Inheritances in Python
Inheritance is a fundamental concept of object-oriented programming (OOP) that allows classes to inherit properties and methods from other classes. In Python, there are several types of inheritance, including:

* **Single inheritance:** Single inheritance is the simplest type of inheritance in which a class inherits from a single parent class. The child class can access all the properties and methods of the parent class. To implement single inheritance, the child class is defined by inheriting from a single parent class using the syntax: class ChildClass(ParentClass):

* **Multiple inheritance:** Multiple inheritance is a type of inheritance in which a class inherits properties and methods from multiple parent classes. To implement multiple inheritance, the child class is defined by inheriting from two or more parent classes using the syntax: class ChildClass(ParentClass1, ParentClass2, ...):

* **Multi-level inheritance:** Multi-level inheritance is a type of inheritance in which a child class inherits properties and methods from a parent class, which in turn, inherits from another parent class. To implement multi-level inheritance, the child class is defined by inheriting from a parent class, which is defined by inheriting from another parent class using the syntax: class ChildClass(ParentClass1):

* **Hierarchical inheritance:** Hierarchical inheritance is a type of inheritance in which multiple child classes inherit properties and methods from a single parent class. To implement hierarchical inheritance, multiple child classes are defined by inheriting from a single parent class using the syntax: class ChildClass1(ParentClass): and class ChildClass2(ParentClass):

* **Hybrid inheritance:** Hybrid inheritance is a combination of two or more types of inheritance, such as multiple inheritance and multi-level inheritance. It allows for more complex inheritance hierarchies and provides greater flexibility in designing class structures.

In Python, inheritance is implemented using the "super()" method to call the parent class constructor and methods. The "super()" method allows child classes to access and inherit properties and methods from their parent classes.

<hr>

### Operator Overloading in Python
Operator overloading is a feature in Python that allows you to redefine the behavior of operators (+, -, *, /, ==, etc.) for objects of your own classes. This means that you can make your objects behave like built-in types when used with these operators.

For example, let's say you have a class called Vector that represents a mathematical vector with x and y components. You can define the behavior of the addition operator (+) for the Vector class so that it performs vector addition instead of just adding the x and y components separately:

<pre>
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
</pre>

In this example, we have defined a Vector class with an &lowbar;&lowbar;add&lowbar;&lowbar; method that takes another Vector object as an argument and returns a new Vector object that represents the sum of the two vectors. We have used the + operator to call this method when adding two Vector objects together.

Here's an example of how to use this class:

<pre>
v1 = Vector(2, 3)
v2 = Vector(4, 5)
v3 = v1 + v2
print(v3.x, v3.y)  # prints "6 8"
</pre>

In this example, we have created two Vector objects v1 and v2, and added them together using the + operator. The result is a new Vector object v3 with x component of 6 and y component of 8.

In addition to the &lowbar;&lowbar;add&lowbar;&lowbar; method, there are many other methods that you can define to overload different operators in Python. Here are some common ones:

* **&lowbar;&lowbar;sub&lowbar;&lowbar;** (self, other): overload the subtraction operator (-)
* **&lowbar;&lowbar;mul&lowbar;&lowbar;(self, other):** overload the multiplication operator (*)
* **&lowbar;&lowbar;truediv&lowbar;&lowbar;(self, other):** overload the division operator (/)
* **&lowbar;&lowbar;eq&lowbar;&lowbar;(self, other):** overload the equality operator (==)
* **&lowbar;&lowbar;lt&lowbar;&lowbar;(self, other):** overload the less than operator (<)
* **&lowbar;&lowbar;gt&lowbar;&lowbar;(self, other):** overload the greater than operator (>)
* **&lowbar;&lowbar;str&lowbar;&lowbar;(self):** overload the string representation of an object (str())

Here's an example of overloading the multiplication operator for the Vector class:

<pre>
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __mul__(self, scalar):
        return Vector(self.x * scalar, self.y * scalar)
</pre>

In this example, we have defined a Vector class with an &lowbar;&lowbar;mul&lowbar;&lowbar; method that takes a scalar value as an argument and returns a new Vector object that represents the product of the vector and the scalar. We have used the * operator to call this method when multiplying a Vector object by a scalar.

Here's an example of how to use this class:

<pre>
v1 = Vector(2, 3)
v2 = v1 * 2
print(v2.x, v2.y)  # prints "4 6"
</pre>

In this example, we have created a Vector object v1 and multiplied it by a scalar value of 2 using the * operator. The result is a new Vector object v2 with x component of 4 and y component of 6.

Overall, operator overloading allows you to make your code more

<hr>

### Abstract Class in Python
In Python, an abstract class is a class that cannot be instantiated on its own and is meant to be subclassed by other classes. It provides a way to define a common interface for a set of subclasses, but allows each subclass to implement its own behavior.

To create an abstract class in Python, you need to use the abc module, which stands for "abstract base classes". Here's an example:

<pre>
import abc

class Shape(metaclass=abc.ABCMeta):
    @abc.abstractmethod
    def area(self):
        pass

    @abc.abstractmethod
    def perimeter(self):
        pass
</pre>

In this example, we have defined an abstract class called Shape that has two abstract methods: area and perimeter. These methods have no implementation and are marked with the @abc.abstractmethod decorator.

When you define an abstract class, you need to use the abc.ABCMeta metaclass, which tells Python that this class is abstract and cannot be instantiated directly.

Now, let's create a concrete subclass of Shape:

</pre>
class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)
</pre>

In this example, we have defined a concrete subclass of Shape called Rectangle. This class implements the area and perimeter methods, which are required by the Shape abstract class.

Note that if you try to create an instance of the Shape class directly, you will get a TypeError:

<pre>
s = Shape()  # Raises TypeError: Can't instantiate abstract class Shape with abstract methods area, perimeter
</pre>

This is because Shape is an abstract class and cannot be instantiated directly. Instead, you need to create an instance of a concrete subclass like Rectangle:

<pre>
r = Rectangle(2, 3)
print(r.area())       # prints "6"
print(r.perimeter())  # prints "10"
</pre>

In this example, we have created an instance of the Rectangle class and called its area and perimeter methods, which are implemented by the subclass.

Abstract classes are useful when you want to define a common interface for a set of related classes, but don't want to provide a concrete implementation for that interface. This allows you to create a flexible and extensible design that can be customized by subclasses.

<hr>

### Interface in Python
In Python, there is no built-in keyword for defining interfaces like in some other programming languages. However, you can create interfaces using abstract classes.

An interface in Python is a collection of abstract methods. These methods are declared but do not contain any implementation. A class that implements an interface must provide implementations for all the methods in the interface.

To create an interface in Python, you can use the abc module, which stands for "abstract base classes". Here's an example:

<pre>
import abc

class Shape(metaclass=abc.ABCMeta):
    @abc.abstractmethod
    def area(self):
        pass

    @abc.abstractmethod
    def perimeter(self):
        pass
</pre>

In this example, we have defined an interface called Shape that has two abstract methods: area and perimeter. These methods have no implementation and are marked with the @abc.abstractmethod decorator.

Now, let's create a class that implements the Shape interface:

<pre>
class Rectangle:
    def __init__(self, width, height):
        self.width = width
        self.height = height

    def area(self):
        return self.width * self.height

    def perimeter(self):
        return 2 * (self.width + self.height)
</pre>

In this example, we have defined a class called Rectangle that implements the Shape interface by providing implementations for the area and perimeter methods.

Note that if you try to create a subclass of Shape that does not implement all the abstract methods, you will get a TypeError:

<pre>
class Square(Shape):
    def __init__(self, side):
        self.side = side

    def area(self):
        return self.side ** 2

# Raises TypeError: Can't instantiate abstract class Square with abstract methods perimeter
</pre>

This is because Square is a subclass of Shape and is required to implement all the abstract methods defined in the Shape interface.

Using interfaces in Python can help you write more modular and reusable code. By defining a clear and well-defined interface, you can decouple the implementation details of your code from its usage, making it easier to change and maintain over time.

<hr>
