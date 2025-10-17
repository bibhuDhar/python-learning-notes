# Inheritence

### Definition:
Inheritance is a fundamental concept in object-oriented programming (OOP) where a class (child/subclass) can acquire properties and methods from another class (parent/superclass).
It allows code reuse, reduces redundancy, and enables hierarchical relationships between classes.
```
class Parent:
    def __init__(self, name):
        self.name = name
    
    def greet(self):
        print(f"Hello, I am {self.name}")
        
class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)  # Inherit properties from Parent
        self.age = age
    
    def show_age(self):
        print(f"I am {self.age} years old")

# Example usage
c = Child("Rafi", 15)
c.greet()      # Inherited method
c.show_age()   # Child method


```
###output
```
Hello, I am Rafi
I am 15 years old

```

### Breakdown
Parent class: Defines common properties/methods (name and greet()).
Child class: Inherits from Parent using Child(Parent).
super() function: Calls the parent class constructor to inherit properties.
Child-specific methods: show_age() is only available in the Child class.

```
class Phone:
    def __init__(self, model, battery, camera):
        self.model = model
        self.battery = battery
        self.camera = camera

    def charge(self, hour):
        print(f"Charging for {hour} hours")

class Smartphone(Phone):
    def __init__(self, model, battery, camera, processor):
        super().__init__(model, battery, camera)
        self.processor = processor

    def charge(self, hour):
        print("Fast charging process")
        super().charge(hour)

Pro = Smartphone("X", 5000, 100, "SnapDragon")
print(Pro.model)  # Inherited property
Pro.charge(2)     # Overridden method

```
### Breakdown
Parent class: Defines common properties/methods (name and greet()).
Child class: Inherits from Parent using Child(Parent).
super() function: Calls the parent class constructor to inherit properties.
Child-specific methods: show_age() is only available in the Child class.

###output
```
Hello, I am Rafi
I am 15 years old

```


```
class Phone:
    def __init__(self, model, battery, camera):
        self.model = model
        self.battery = battery
        self.camera = camera

    def charge(self, hour):
        print(f"Charging for {hour} hours")

class Smartphone(Phone):
    def __init__(self, model, battery, camera, processor):
        super().__init__(model, battery, camera)
        self.processor = processor

    def charge(self, hour):
        print("Fast charging process")
        super().charge(hour)

Pro = Smartphone("X", 5000, 100, "SnapDragon")
print(Pro.model)  # Inherited property
Pro.charge(2)     # Overridden method

```
###Breakdown
Phone class: Parent class with basic attributes (model, battery, camera) and method charge().
Smartphone class: Child class inherits Phone and adds processor.
Method overriding: The charge() method in Smartphone replaces the parent’s version but still calls it using super().charge(hour).
Property access: Pro.model shows that child objects can use parent properties directly.

###output
```
X
Fast charging process
Charging for 2 hours

```




# Polymorphism
Polymorphism = poly + morph + ism

poly- → “many”

From Greek polys, meaning many or multiple.

-morph- → “form” or “shape”

From Greek morphe, meaning shape or form.

-ism → “the concept or practice of”

Common suffix meaning a principle, practice, or phenomenon.

✅ Putting it together:
Polymorphism literally means “the concept of many forms”
