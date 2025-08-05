- Python's dynamic typing and duck typing make it inherently polymorphic.
- Polymorphism allows methods in different classes to share the same name but perform distinct tasks.
```
class Shape:
    def area(self):
        return "Undefined"

class Rectangle(Shape):
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def area(self):
        return self.length * self.width

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius

    def area(self):
        return 3.14 * self.radius ** 2
```

- In above example area method is overridden.

### Types of Polymorphism.
#### Compile-time polymorphism
- In this behavior of a function or operator is resolved during the program's compilation phase
- Examples are: Method Overloading and Operator Overloading.
- In this multiple function or operator can share the same name but perform different tasks based on the context.
- Compile time polymorphism is not supported natively due to dynamic typing nature.

#### Runtime Polymorphism
- When the behavior of a method is determined at runtime based on the type of the object.
- For Example is : Method Overriding
- In this a child class can redefine a method from its parent class to provide its own specific implementation.
```
# Runtime Polymorphism
class Animal:
    def sound(self):
        return "Some generic sound"

class Dog(Animal):
    def sound(self):
        return "Bark"

class Cat(Animal):
    def sound(self):
        return "Meow"
```


### Method Overloading
- in many programming languages like C++ or Java, you can define multiple methods with the same name but different parameter lists. This concept is called **method overloading***.
- Python does not support method overloading by default. If you define multiple methods with the same name, only the latest definition will be used.
```
def product(a, b):
    p = a * b
    print(p)

def product(a, b, c):
    p = a * b*c
    print(p)

product(4, 5, 5)
```

- Python only recognizes the latest definition of product()
- The earlier definition of product(a,b) gets overwritten.
- If you call it, it will raise an error because the latest version expects 3 arguments.
- There are several ways to perform method overloading:
1. **Using Variable Arguments ( * args) **
	- In this approach, we use variable-length arguments to accept any number of arguments and handle them inside the function.
```
def add(datatype, *args):
    if datatype == 'int':
        res = 0
    elif datatype == 'str':
        res = ''
    
    for item in args:
        res += item

    print(res)
```

2. **Using Default Arguments (None as default value)**
	- In this approach we pass set default arguments as None.
```
def add(a=None, b=None):
    if a is not None and b is None:
        print(a)
    else:
        print(a + b)

```

3. **Operator Overloading**
	- Python allows operator overloading. This is done by redefining special methods in your class.
	- Such as: __ add __ for addition and __ mul __ for * etc.
```
class Point:  
    def __init__(self, x=0, y=0):  
        self.x = x  
        self.y = y  
  
    def __str__(self):  
        return f"({self.x}, {self.y})"  
  
    def __add__(self, other):  
        x = self.x + other.x  
        y = self.y + other.y  
        return Point(x, y)  
  
p1 = Point(1, 2)  
p2 = Point(2, 3)  
print(p1 + p2)  # Output: (3, 5)
```

### Method Overriding
- Method overriding is the ability of python that allows a subclass or child class to provide a specific implementation of a method that is already provided by its super class or parent class.
- When the method in a class has the same name, same parameters or signature, and same return type as a method in its super-class, then the method in the subclass is said to override the method in the super-class.
```
class Parent(): 
	
	# Constructor 
	def __init__(self): 
		self.value = "Inside Parent"
		
	# Parent's show method 
	def show(self): 
		print(self.value) 
		
# Defining child class 
class Child(Parent): 
	
	# Constructor 
	def __init__(self): 
		super().__init__()  # Call parent constructor
		self.value = "Inside Child"
		
	# Child's show method 
	def show(self): 
		print(self.value) ```
