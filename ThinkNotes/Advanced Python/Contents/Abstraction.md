- Abstraction is a method in which irrelevant details are hidden from the user and show the details that are relevant to user.

#### Abstract classes in Python
- Abstract class is a class in which one or more abstract method are defined.
- **Abstract Method**: In python abstract method feature is not a default feature. To create abstract method and abstract classes we have to import the "ABC" and abstract method classes from abc (Abstract Base Class).
```
from abc import ABC, abstractmethod  
class BaseClass(ABC):  
    @abstractmethod  
    def method_1(self):  
         #empty body  
         pass
```

