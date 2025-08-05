#### Classes
- Class is a user-defined template to create a object.
- It bundles data and functions together

```
# define a class
class Dog:
    sound = "bark"  # class attribute
```

#### Object
- Object is a instance of class.
- It contains its specific attributes and can invoke methods inside the class
```
class Dog:
sound = "bark"


# Create an object from the class
dog1 = Dog()

# Access the class attribute
print(dog1.sound)
```

##### Why do we need Classes and Objects?
- Promotes code reusability and modular design with organized methods and attributes.
- Simplifies complex programs by grouping related data together.

#### What is '__ init __ () ' method ?
- In python this method automatically initializes object attributes when object is created.
- This method is the constructor in Python.
```
class Dog:
    species = "Canine"  # Class attribute

    def __init__(self, name, age):
        self.name = name  # Instance attribute
        self.age = age  # Instance attribute
```

#### What is '__ new __ ()' method()?
- Responsible for creating a new instance of class.
- It allocates memory and returns the new object.
- Called before __ init __ ().
#### What is 'self' parameter?
- It is the reference to object created during initialization.
- It represents the instance of the class being used.
- Whenever we create a object from a class, self refers to the current object instance.
```
# Also it is like
class Dog():
	def __init__(self,name):
		self.name = name
	def name_dog(self):
		return self.name
dog = Dog("Alex")
name = dog.name_dog() # Name of the dog
```

#### __ str __ () Method
- This method allows us to define a custom string representation of an object.
- So when we print a object it by default return the address in the string

```
class Dog:
    species = "Canine"  # Class attribute

    def __init__(self, name, age):
        self.name = name  # Instance attribute
        self.age = age  # Instance attribute
    def __str__(self):
	    return f"Name of dog is {self.name} and age is {self.age}"

dog = ("Alex",2)
print(dog) # Prints: Name of dog is Alex and age is 2
```

### Metaclasses
- **type**
	- The exact class that is used for class instantiation is called type
	- Normally, we define a class using a special syntax called the _class keyword_, but this syntax is a substitute for _type class_.
	- *Use of type*:``
```
def init(self, ftype):
    self.ftype = ftype

def getFtype(self):
    return self.ftype 

FoodType = type('FoodType', (object, ), {
    '__init__': init,
    'getFtype' : getFtype,
    })

fType = FoodType(ftype ='Vegetarian')
print(fType.getFtype())
```

- **Metaclass**
	- Python uses metaclass to make a class itself, same as we use class to create a object.
	- Metaclasses are classes that inherit directly from type
Ex:
```
class MetaCls(type):
    """A sample metaclass without any functionality"""
    def __new__(cls, clsname, superclasses, attributedict):
        print("clsname:", clsname)
        print("superclasses:", superclasses)
        print("attrdict:", attributedict)
        return super(MetaCls, cls).__new__(cls, \
                       clsname, superclasses, attributedict)

C = MetaCls('C', (object, ), {})
print("class type:", type(C))
```

- Arguments:
	- The first argument is the metaclass itself.
	- The second name is class name
	- The third argument is the super classes (in the form of tuple)
	- The fourth is the attributes of the classes.
- Also the super() method has arguments this arguments preserve the order of inheritance. This is done so that it wont cause any problem even if the order of inheritance changes.
