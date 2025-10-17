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
Definition

Polymorphism means “many forms.”
It allows objects of different classes to respond to the same method name in different ways.

👉 The term comes from:

poly → many

morph → forms

In programming, this means you can call the same method (like capture()) on different objects, and each will perform its own version of that method.

Real-Life Analogy (as from DataCamp example)

Think about various devices that can take photos —
📱 Smartphone, 🚁 Drone, 📷 DSLR, or even a basic Camera.

All have the same capability — they can capture photos,
but the way or quality of capturing is different for each.

That’s exactly what polymorphism represents in code.

```
class Camera:
    def __init__(self, name):
        self.name = name
    def capture(self):
        print("A photo is captured")

class Smartphone(Camera):
    def __init__(self, name, resolution):
        super().__init__(name)
        self.resolution = resolution
    def capture(self):
        print("Photo is captured by Phone")

class Drone(Camera):
    def __init__(self, name, resolution):
        super().__init__(name)
        self.resolution = resolution
    def capture(self):
        print("Photo is captured by Drone")

class Dslr(Camera):
    def __init__(self, name, resolution):
        super().__init__(name)
        self.resolution = resolution
    def capture(self):
        print("Photo is captured by Dslr")

# Creating objects
phone = Smartphone("iPhone", 30)
drone = Drone("Panther", 300)
dslr = Dslr("Canon", 200)

# Calling the same method 'capture()' for each
phone.capture()
drone.capture()
dslr.capture()

```

Breakdown of the Concept

Parent Class – Camera:
Has a common method capture() representing the general idea of taking a photo.

Child Classes – Smartphone, Drone, Dslr:
Each subclass overrides the capture() method to perform it differently.

Common Interface, Different Behavior:
Even though all objects have the same method name (capture()),
the output differs based on the object that calls it.

### Output
```
Photo is captured by Phone
Photo is captured by Drone
Photo is captured by Dslr

```

# Encapsulation

### Definition
Encapsulation means wrapping data (variables) and methods (functions) into a single unit (a class), and restricting direct access to some of the object’s components.
It helps to protect sensitive data and ensures that it is accessed or modified only through specific methods.

Word Breakdown
“Capsulate” → to enclose or wrap.
“Encapsulation” → enclosing data and methods together in one place (a class).
📦 In short: Our data and methods are encapsulated (contained) inside a class.
### Why Use Encapsulation?
✅ To protect data from direct modification.
✅ To control access to class variables using getter/setter methods.
✅ To hide internal details and expose only what’s necessary.
✅ To increase security and maintain consistency in code.


```
# Encapsulation
class Mobile:
  def __init__(self, name, model, imei):
    self.__name = name
    self.__model = model
    self.__imei = imei  # Protected by double underscore (__)

  def charge(self):
    print("Phone is charging")

  # Getter methods (to read private data)
  def imei_getter(self):
    return self.__imei

  def model_getter(self):
    return self.__model

  def name_getter(self):
    return self.__name

  # Setter method (to modify private data safely)
  def name_setter(self, name):
    self.__name = name


# Creating object
Iphone = Mobile("iPhone", "17", "1x32jd")

# Using setter to modify name safely
Iphone.name_setter("Samsung")

# Using getters to access private data
print(Iphone.name_getter())
print(Iphone.model_getter())
print(Iphone.imei_getter())

```

### Code Breakdown

Private Attributes:
__name, __model, and __imei are private variables.
They cannot be accessed directly (e.g., Iphone.__imei would cause an error).

Double Underscore (__):
Used before variable names to make them private and inaccessible outside the class.

Getter Methods:
Used to retrieve the value of private attributes safely.
Example → imei_getter() or model_getter()

Setter Methods:
Used to update the value of private attributes safely.
Example → name_setter("Samsung")

Encapsulation in Action:
We protect sensitive information (like IMEI) from being changed or leaked.


# Abstraction
related to designing part,our complex methods are hide and to operate we will provide function/method
In camera if we capture photo
