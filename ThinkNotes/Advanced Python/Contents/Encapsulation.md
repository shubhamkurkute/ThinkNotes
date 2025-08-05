- Encapsulation refers to the bundling of data (attributes) and methods (functions) that operate on the data into a single unit, typically a class.
- It also restricts direct access to some components, which helps protect the integrity of the data and ensures proper usage.

#### Public Access Modifier:
- The members of a class that are declared public are easily accessible from any part of the program.
- All data members and member functions are public by default.
```
class Car:
	def __init__(self,name,company):
		# Public members
		self.name = name
		self.company = company
	# Public member function
	def car_details(self):
		return f"Car name is {self.name} of company {self.company}"
	
```

#### Protected Access Modifier
- The members of a class that are declared protected are only accessible within the class where it is declared and its subclass.
- A single underscore is used to describe a protected data member or method of the class.
```
class Student:

    # protected data members
    _name = None
    _roll = None
    _branch = None

    # constructor
    def __init__(self, name, roll, branch):
        self._name = name
        self._roll = roll
        self._branch = branch

    # protected member function
    def _displayRollAndBranch(self):

        # accessing protected data members
        print("Roll:", self._roll)
        print("Branch:", self._branch)
```

#### Private Access Modifier
- The members of the class that are declared private are accessible within the class only
- Private access modifier is the most secure access modifier.
- The data members of a class are declared private by adding a double underscore ' __ ' symbol before the data member of the class.
```
class Geek:

    # private members
    __name = None
    __roll = None
    __branch = None

    # constructor
    def __init__(self, name, roll, branch):
        self.__name = name
        self.__roll = roll
        self.__branch = branch

    # private member function
    def __displayDetails(self):

        # accessing private data members
        print("Name:", self.__name)
        print("Roll:", self.__roll)
        print("Branch:", self.__branch)
```