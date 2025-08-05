- Inheritance allows a class to inherit attributes and methods from another class.

```
class ParentClass:

# Parent class code here  
pass

class ChildClass(ParentClass):

# Child class code here  
pass
```

- **Parent Class**
	- This is the base class from which other classes inherit
	- It contains attributes and methods that the child class can reuse.
- **Child Class**
	- This is the derived class that inherits from its parent class.
	- Child class automatically gets all the attributes and methods of the parent class unless overridden.

#### super() Method
- Function is used to refer to the parent class or superclass.
- It allows you to call methods defined in the superclass from the subclass.
- **Syntax**
	- super()
	- returns a proxy object which represents the parents class
```
class Emp():
    def __init__(self, id, name, Add):
        self.id = id
        self.name = name
        self.Add = Add

# Class freelancer inherits EMP
class Freelance(Emp):
    def __init__(self, id, name, Add, Emails):
        super().__init__(id, name, Add)
        self.Emails = Emails
```