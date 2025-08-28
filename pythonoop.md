# OOP in Python. Hello and welcome! Object-oriented… | by Taylor Berukoff | Medium



![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*Aepqo-jv2opyp0NzSaoa8w.jpeg)

Hello and welcome! **Object-oriented programming** (**OOP**) is a widely used programming paradigm that allows developers to create modular, reusable code that is easier to maintain and scale. Python, as a popular and versatile programming language, provides developers with powerful tools for implementing **OOP** concepts. In this article, we’ll explore the basics of **OOP** in Python, including **encapsulation**, **inheritance**, **polymorphism**, **abstraction**, and **best practices**. Whether you’re a seasoned Python developer or just starting out, understanding these **OOP** principles will help you write better, more organized, and more efficient code.

**Table of Contents**:
----------------------

1.  Intro to OOP
2.  Encapsulation
3.  Inheritance
4.  Polymorphism
5.  Abstraction
6.  Best Practices

**1\. Intro to OOP**
--------------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*K1qqTyj9AZsCbFufN7RGLg.jpeg)

**OOP** is an important programming paradigm that has **revolutionized** the way developers think about software design. By creating objects that encapsulate both data and behavior, developers can more **easily model** complex systems and create reusable code. **OOP** has become increasingly popular in recent years as more and more developers embrace its benefits.

One of the key advantages of **OOP** is its ability to create **modular**, **reusable code**. By breaking a system down into objects, developers can create smaller, more manageable pieces of code that can be reused in different parts of the system. This can lead to significant time savings and reduce the risk of bugs or errors in the code.

At the heart of OOP is the concept of a **class**, which is a **blueprint** for creating objects. A class defines a set of attributes and methods that describe the behavior and characteristics of an **object**. To create an **object** from a class, you must first **instantiate** it using the `__init__` method, which is a special method that is called when the object is created. This method allows you to initialize the object's attributes with default values.

Here is an example of a simple **class** in Python:

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")
```


In this example, we have defined a `Person` **class** with two attributes, `name` and `age`, and one method, `greet`. The `__init__` method is used to initialize the `name` and `age` attributes with values passed in as arguments. It will be run any time you try to instantiate (make an actual object from) your class. The `greet` method (a function associated with an object) is used to print a message that includes the person's name and age.

To create an instance of the `Person` class, we can simply call the class with the desired arguments:

```
person1 = Person("Alice", 25)
```


In this case, we have created a new `Person` object named `person1` with the `name` attribute set to "Alice" and the `age` attribute set to 25. We can now call the `greet` method on this object to print a message:

```
person1.greet()
```


This will output:

```
Hello, my name is Alice and I am 25 years old.
```


2\. Encapsulation
-----------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*gmT0r_SYxVvt5SljKp_zWw.png)

**Encapsulation** is one of the four fundamental principles of Object-Oriented Programming (OOP), alongside **inheritance**, **polymorphism**, and **abstraction**. It is the practice of **hiding** the implementation details of an object and allowing access to only the essential features that need to be used by other parts of the program. **Encapsulation** helps maintain the **integrity** of the object’s data and ensures that it is used only in the intended way.

In Python, **encapsulation** is achieved through the use of **access modifiers**. Access modifiers are keywords that determine the visibility of a variable or method. The two most common access modifiers in Python are public and private. A public variable or method can be accessed from anywhere in the program, while a private variable or method can only be accessed within the class that defines it.

Here’s an example of **encapsulation** in action:

```
class Person:
    def __init__(self, name, age):
        self.name = name
        self.__age = age   # private variable
    def get_age(self):
        return self.__age
    def set_age(self, age):
        if age > 0:
            self.__age = age
person = Person("Alice", 30)
print(person.name)
print(person.get_age())
person.set_age(-5)
print(person.get_age())
```


In this example, we have a class `Person` with two variables, `name` and `__age`. The `__age` variable is declared as private by prefixing it with two underscores. This means that it can only be accessed within the class `Person`. We have also defined two methods `get_age` and `set_age` which allow us to retrieve and modify the value of `__age` respectively.

When we create a new `Person` object, we pass in values for both `name` and `age`. We can access the `name` variable using dot notation, as it is a public variable. However, when we try to access the `__age` variable directly, we get an error because it is private. Instead, we use the `get_age` method to retrieve its value.

We can also modify the value of `__age` using the `set_age` method. However, we have added a check to make sure that the new value is greater than zero before assigning it to `__age`. This helps maintain the integrity of the object's data and ensures that it is used only in the intended way.

Overall, **encapsulation** is an essential aspect of OOP as it allows us to create objects with well-defined interfaces and maintain the integrity of their data. By using access modifiers to control the visibility of variables and methods, we can ensure that our objects are used only in the intended way.

3\. Inheritance
---------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*iP78XqAbkntOuzbHCoiubg.png)

**Inheritance** is a powerful Object-Oriented Programming concept that allows us to create a **new class** based on an **existing class**. The new class is called the **child class** or **subclass**, and the existing class is called the **parent class** or **superclass**. **Inheritance** is an essential aspect of **OOP** as it allows us to reuse code and establish a hierarchical relationship between classes.

In Python, inheritance is implemented using the syntax `class ChildClass(ParentClass):`. The child class inherits all the attributes and methods of the parent class, and it can also have additional attributes and methods that are specific to it. The child class can also **override** or **extend** the methods of the parent class.

Here is an example of inheritance in Python:

```
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
            def speak(self):
        print(f"{self.name} says hi!")
class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Dog")
        self.breed = breed
            def speak(self):
        print(f"{self.name} barks!")
```


In this example, we have a parent class called `Animal`, which has an `__init__` method that takes a name and a species and sets them as instance variables. The `Animal` class also has a `speak` method that prints out a message.

We then create a child class called `Dog`, which inherits from the `Animal` class. The `Dog` class has its own `__init__` method that takes a name and a breed and calls the parent class's `__init__` method to set the name and species. The `Dog` class also overrides the `speak` method to print out a different message.

Notice that we did not have to type out the initialization of the instance variables `name` and `species` for the subclass Dog. This is because Dog inherits all the attributes of the Animal class, and these instance variables are create upon running the `super().__init__(name, “Dog”)` function.

We can now create instances of the `Animal` and `Dog` classes and call their methods:

```
animal = Animal("Bob", "Cat")
animal.speak()  # Output: "Bob says hi!"
dog = Dog("Max", "Labrador")
dog.speak()  # Output: "Max barks!"
```


As we can see, the `Dog` class has inherited the `speak` method from the `Animal` class, but it has overridden it to print out a different message. This is an example of how **inheritance** can help us reuse code and create a **hierarchy** of classes.

4\. Polymorphism
----------------
![Rasim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*OGLbk0YoNHjr4NcKJKaxQw.jpeg)

**Polymorphism** is another essential feature of Object-Oriented Programming. It is the ability of objects to take on **different forms** or **behaviors**. In Python, **polymorphism** allows objects to share the **same interface**, but with **different implementations**.

One way to achieve **polymorphism** in Python is through the use of **method overriding**. **Method overriding** is when a subclass provides a **different implementation** of a method that is **already defined** in its superclass. When the method is called on an object of the subclass, the implementation in the **subclass** is used instead of the one in the **superclass**.

Here is an example of **method overriding** in Python:

```
class Animal:
    def speak(self):
        print("Animal is speaking...")
class Dog(Animal):
    def speak(self):
        print("Dog is barking...")
class Cat(Animal):
    def speak(self):
        print("Cat is meowing...")
# Create objects of the different classes
animal = Animal()
dog = Dog()
cat = Cat()
# Call the speak() method on each object
animal.speak()  # Output: Animal is speaking...
dog.speak()     # Output: Dog is barking...
cat.speak()     # Output: Cat is meowing...
```


In this example, we have a superclass `Animal` and two subclasses `Dog` and `Cat`. The `Dog` and `Cat` classes both have a `speak()` method that overrides the `speak()` method in the `Animal` class. When we create objects of the different classes and call the `speak()` method on them, the appropriate implementation is used based on the type of the object.

Another way to achieve **polymorphism** in Python is through the use of **duck typing**. **Duck typing** is a concept in dynamic programming languages where the type of an object is less important than the methods it implements. If an object has a method with a certain name and signature, it is considered to be of a certain type, regardless of its actual class.

Here is an example of **duck typing** in Python:

```
class Duck:
    def quack(self):
        print("Quack!")
class Person:
    def quack(self):
        print("I'm quacking like a duck...")
def make_quack(obj):
    obj.quack()
# Create objects of the Duck and Person classes
duck = Duck()
person = Person()
# Call the make_quack() function with the different objects
make_quack(duck)    # Output: Quack!
make_quack(person)  # Output: I'm quacking like a duck...
```


In this example, we have a `Duck` class and a `Person` class, both of which have a `quack()` method. We also have a `make_quack()` function that takes an object as a parameter and calls its `quack()` method. When we call the `make_quack()` function with objects of the `Duck` and `Person` classes, the appropriate implementation is used based on the methods that are available on the objects, rather than their actual class.

5\. Abstraction
---------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*-cJTFd3AosudzVr-QqrZ7A.jpeg)

**Abstraction** is an important concept in Object-Oriented Programming (OOP) that allows programmers to create **simplified** and **generalized models** of **complex systems**. The idea is to define a set of **common characteristics** or behaviors that multiple objects share, and then group them together into a higher-level class that can be used to represent them all.

One way to think of **abstraction** is to imagine a car. From a high level, we know that a car has certain **common characteristics**, such as wheels, an engine, and a steering wheel. However, the specifics of each car can vary greatly — some cars have four doors, some have two, some have sunroofs, etc. **Abstraction** allows us to focus on the **common characteristics** and **behaviors** of all cars while ignoring the specific details of each individual car.

In Python, abstraction is often achieved through the use of **abstract classes** or **interfaces**. These are classes that define a set of methods that must be implemented by any class that inherits from them. For example, consider the following abstract class:

```
from abc import ABC, abstractmethod
class Vehicle(ABC):
        @abstractmethod
    def start(self):
        pass
        @abstractmethod
    def stop(self):
        pass
```


This class defines two **abstract methods**, `start` and `stop`, that must be implemented by any subclass of `Vehicle`. Note that the `@abstractmethod` decorator is used to indicate that these methods are abstract and should not be called directly. Instead, they are meant to be **overridden** by subclasses.

Here is an example of a subclass of `Vehicle` that implements the `start` and `stop` methods:

```
class Car(Vehicle):
        def start(self):
        print("Starting the car")
        def stop(self):
        print("Stopping the car")
```


By **inheriting** from `Vehicle` and implementing the **abstract methods**, `Car` is able to share the common characteristics and behaviors of all `Vehicle` objects while still being able to define its own specific functionality.

**Abstraction** can be a powerful tool in OOP because it allows programmers to create generalized models that can be easily extended and modified. By focusing on the common characteristics of objects, abstraction can make code more flexible and easier to maintain over time.

6\. Best Practices
------------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*D-VHyiMoXsHGpYw-PkorNw.jpeg)

Object-oriented programming provides a powerful and flexible way to organize and structure your code. To ensure your code is **maintainable**, **scalable**, and **easy to understand**, it’s important to follow best practices when developing your programs. Here are some key best practices to keep in mind when working with object-oriented programming in Python.

1.**Keep Classes Focused.** Each class should have a single responsibility and should be focused on one specific task. This principle, known as the Single Responsibility Principle (SRP), helps to keep your code organized and maintainable. It also makes it easier to reuse and test your code.

For example, if you have a class that handles database connections, you should avoid adding methods that handle file I/O. Instead, you should create a separate class for file I/O operations. This keeps your code organized and ensures that each class has a clear and specific purpose.

Here’s an example of a class that handles database connections:

```
class DatabaseConnection:
    def __init__(self, host, port, username, password):
        self.host = host
        self.port = port
        self.username = username
        self.password = password
        self.connection = None
        def connect(self):
        # connect to the database using the provided credentials
        pass
        def disconnect(self):
        # disconnect from the database
        pass
        def execute_query(self, query):
        # execute the provided SQL query and return the results
        pass
```


2. **Use Meaningful Names.** The names you choose for your classes, methods, and variables should be descriptive and meaningful. This makes your code easier to read and understand. It also helps other developers who may need to work with your code in the future.

For example, if you have a class that represents a user, you should name it User rather than something generic like Object. Similarly, you should use descriptive names for methods and variables. For instance, a variable that stores a user’s age should be named user\_age instead of something like x or y.

Here’s an example of a class with meaningful names:

```
class User:
    def __init__(self, name, age, email):
        self.name = name
        self.age = age
        self.email = email
        def send_email(self, message):
        # send an email to the user using the provided message
        pass
```


3.**Avoid Overusing inheritance.** Inheritance can be a powerful tool in OOP, but it should be used judiciously. One common mistake is to create deep inheritance hierarchies that become difficult to manage and maintain. This can lead to issues such as tight coupling between classes, increased complexity, and reduced flexibility. Instead, strive for a flatter inheritance structure and consider other techniques such as composition to achieve the desired functionality.

Here’s an example of overusing inheritance:

```
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species
        class Mammal(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)
        class Reptile(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)
        class Fish(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)
        class Dog(Mammal):
    def __init__(self, name):
        super().__init__(name, "Canine")
        class Cat(Mammal):
    def __init__(self, name):
        super().__init__(name, "Feline")
        class Snake(Reptile):
    def __init__(self, name):
        super().__init__(name, "Serpent")
        class Goldfish(Fish):
    def __init__(self, name):
        super().__init__(name, "Goldfish")
```


In this example, we have a class hierarchy that goes several levels deep, with each subclass adding very little functionality to the parent class. This can make the code difficult to understand and maintain, especially if there are many more subclasses added over time. Instead, it may be better to use composition or interfaces to achieve the desired behavior, without creating a complex class hierarchy.

In conclusion, **understanding** and **utilizing** Object-Oriented Programming principles in Python is **crucial** for developing **efficient**, **scalable**, and **maintainable** code. **Encapsulation**, **Inheritance**, **Polymorphism**, and **Abstraction** are powerful tools that can help developers organize code, reduce code **duplication**, and **improve** code **reusability**.

While these principles are extremely valuable, it’s important to keep in mind that they should **not** be **overused**. It’s crucial to maintain a **balance** between using OOP principles and not over-engineering code. Additionally, following best practices such as writing **clean** and **readable** code, **commenting** code where necessary, and **testing** code regularly are essential for efficient development.

By practicing these OOP principles, developers can create **better**, more **scalable** applications that are easier to **maintain** over time. Python has a rich set of built-in tools and libraries that make implementing OOP principles simple and intuitive. The power of Python combined with OOP principles allows developers to create **elegant**, **efficient**, and **maintainable** code.

I hope you’ve enjoyed this article and I appreciate the time you’ve taken to read it!
