## Basic Class Construct

```python
class Person:
    # Constructor method to initialize the object
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # Method to display the person's details
    def display_details(self):
        print(f"Name: {self.name}, Age: {self.age}")

    # Method to increment the person's age by 1
    def have_birthday(self):
        self.age += 1
        print(f"Happy Birthday, {self.name}! You are now {self.age} years old.")

# Creating an instance of the Person class
person1 = Person("Alice", 30)

# Displaying the person's details
person1.display_details()

# Incrementing the person's age
person1.have_birthday()

# Displaying the updated details
person1.display_details()
```

## Inheritance
### Basic Inheritance

```python
# Parent class
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return f"{self.name} makes a sound."

# Child class inheriting from Animal
class Dog(Animal):
    def speak(self):
        return f"{self.name} barks!"

# Child class inheriting from Animal
class Cat(Animal):
    def speak(self):
        return f"{self.name} meows!"

# Creating instances
dog = Dog("Buddy")
cat = Cat("Whiskers")

# Calling methods
print(dog.speak())  # Output: Buddy barks!
print(cat.speak())  # Output: Whiskers meows!
```

### Using super() to Access Parent Class Methods

```python
# Parent class
class Vehicle:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

    def display_info(self):
        return f"This is a {self.brand} {self.model}."

# Child class inheriting from Vehicle
class Car(Vehicle):
    def __init__(self, brand, model, fuel_type):
        super().__init__(brand, model)  # Call the parent class constructor
        self.fuel_type = fuel_type

    def display_info(self):
        return f"{super().display_info()} It runs on {self.fuel_type}."

# Creating an instance
car = Car("Toyota", "Corolla", "Petrol")

# Calling methods
print(car.display_info())  # Output: This is a Toyota Corolla. It runs on Petrol.
```
The `super()` function is used to call methods from the parent class. This is useful when you want to extend the functionality of the parent class.
### Multilevel Inheritance

```python
# Base class
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def display_info(self):
        return f"Name: {self.name}, Age: {self.age}"

# Child class inheriting from Person
class Employee(Person):
    def __init__(self, name, age, employee_id):
        super().__init__(name, age)
        self.employee_id = employee_id

    def display_info(self):
        return f"{super().display_info()}, Employee ID: {self.employee_id}"

# Grandchild class inheriting from Employee
class Manager(Employee):
    def __init__(self, name, age, employee_id, department):
        super().__init__(name, age, employee_id)
        self.department = department

    def display_info(self):
        return f"{super().display_info()}, Department: {self.department}"

# Creating an instance
manager = Manager("John Doe", 45, "E123", "HR")

# Calling methods
print(manager.display_info())  # Output: Name: John Doe, Age: 45, Employee ID: E123, Department: HR
```
In multilevel inheritance, a class inherits from a child class, creating a chain of inheritance.
### Multiple Inheritance

```python
# First parent class
class A:
    def greet(self):
        return "Hello from class A!"

# Second parent class
class B:
    def greet(self):
        return "Hello from class B!"

# Child class inheriting from both A and B
class C(A, B):
    def greet(self):
        return super().greet()  # Calls the greet method from the first parent class (A)

# Creating an instance
obj = C()

# Calling methods
print(obj.greet())  # Output: Hello from class A!
```
In multiple inheritance, a class can inherit from more than one parent class.
### Method Resolution Order (MRO)

```python
class X:
    def greet(self):
        return "Hello from X!"

class Y:
    def greet(self):
        return "Hello from Y!"

class Z(X, Y):
    pass

# Creating an instance
obj = Z()

# Calling methods
print(obj.greet())  # Output: Hello from X! (because X comes first in MRO)

# Viewing the MRO
print(Z.__mro__)  # Output: (<class '__main__.Z'>, <class '__main__.X'>, <class '__main__.Y'>, <class 'object'>)
```

When using multiple inheritance, Python follows the Method Resolution Order (MRO) to determine which method to call. You can view the MRO using the .__mro__ attribute or the mro() method

Key Points:
- Inheritance allows a class to reuse code from another class.
- super() is used to call methods from the parent class.
- Multiple inheritance allows a class to inherit from multiple parent classes.
- MRO determines the order in which methods are resolved in inheritance hierarchies.
## Setters and Getters

```python
class Person:
    def __init__(self, name, age):
        self._name = name  # Private attribute (conventionally marked with an underscore)
        self._age = age    # Private attribute

    # Getter for name
    @property
    def name(self):
        return self._name

    # Setter for name
    @name.setter
    def name(self, value):
        if not isinstance(value, str):
            raise ValueError("Name must be a string.")
        self._name = value

    # Getter for age
    @property
    def age(self):
        return self._age

    # Setter for age
    @age.setter
    def age(self, value):
        if not isinstance(value, int) or value < 0:
            raise ValueError("Age must be a non-negative integer.")
        self._age = value

    def display_info(self):
        return f"Name: {self.name}, Age: {self.age}"

# Creating an instance
person = Person("Alice", 30)

# Using getters
print(person.name)  # Output: Alice
print(person.age)   # Output: 30

# Using setters
person.name = "Bob"  # Valid
person.age = 25      # Valid

# Displaying updated info
print(person.display_info())  # Output: Name: Bob, Age: 25

# Trying to set invalid values
try:
    person.name = 123  # Raises ValueError: Name must be a string.
except ValueError as e:
    print(e)

try:
    person.age = -5  # Raises ValueError: Age must be a non-negative integer.
except ValueError as e:
    print(e)
```

In Python, setters and getters are used to control access to the attributes of a class. They allow you to add validation, computation, or other logic when getting or setting the value of an attribute. This is particularly useful for ensuring data integrity and encapsulation.

Python provides the @property decorator to define getters and the `@<attribute>.setter` decorator to define setters.

Explanation:
1. **Getters**:
- Defined using the `@property` decorator
- Allow you to access the value of an attribute as if it were a public attribute.
- Example: `person.name` calls the `name` getter.

2. **Setters**:
- Defined using the `@<attribute>.setter` decorator.
- Allow you to set the value of an attribute with additional validation or logic.
	- Example: `person.name = "Bob"` calls the `name` setter.       

3. **Private Attributes**:
- By convention, attributes that should not be accessed directly are prefixed with an underscore (`_`), e.g., `_name` and `_age`.
- This is not enforced by Python but is a convention to indicate that these attributes are "private."

1. **Validation**:
- Setters allow you to validate input before assigning it to an attribute. For example, ensuring that `age` is a non-negative integer.

Why Use Setters and Getters?
- Encapsulation: Hide the internal representation of an object and expose only what is necessary.
- Validation: Ensure that only valid data is assigned to attributes.
- Computation: Perform calculations or transformations when getting or setting values.
- Flexibility: Change the internal implementation without affecting the external interface.

## Immutable class

```python
class ImmutablePoint:
    def __init__(self, x, y):
        # Use private attributes to store the values
        self._x = x
        self._y = y

    # Getter for x (no setter provided)
    @property
    def x(self):
        return self._x

    # Getter for y (no setter provided)
    @property
    def y(self):
        return self._y

    # Override __setattr__ to prevent modification after initialization
    def __setattr__(self, name, value):
        if hasattr(self, name):
            raise AttributeError(f"Cannot modify {name} after initialization.")
        super().__setattr__(name, value)

    def __repr__(self):
        return f"ImmutablePoint(x={self.x}, y={self.y})"

# Creating an instance
point = ImmutablePoint(3, 5)

# Accessing attributes
print(point.x)  # Output: 3
print(point.y)  # Output: 5

# Trying to modify attributes
try:
    point.x = 10  # Raises AttributeError: Cannot modify x after initialization.
except AttributeError as e:
    print(e)

try:
    point.y = 20  # Raises AttributeError: Cannot modify y after initialization.
except AttributeError as e:
    print(e)

# Displaying the object
print(point)  # Output: ImmutablePoint(x=3, y=5)
```

To create an immutable class in Python, you can:
- Use private attributes (by convention, prefixed with an underscore `_`.
- Avoid providing setters or methods that modify the attributes.
- Override the __setattr__ method to prevent modification of attributes after initialization.

```python
class ImmutablePerson:
    __slots__ = ('_name', '_age')  # Restrict attributes to only _name and _age

    def __init__(self, name, age):
        self._name = name
        self._age = age

    @property
    def name(self):
        return self._name

    @property
    def age(self):
        return self._age

    def __setattr__(self, name, value):
        if hasattr(self, name):
            raise AttributeError(f"Cannot modify {name} after initialization.")
        super().__setattr__(name, value)

    def __repr__(self):
        return f"ImmutablePerson(name={self.name}, age={self.age})"

# Creating an instance
person = ImmutablePerson("Alice", 30)

# Accessing attributes
print(person.name)  # Output: Alice
print(person.age)   # Output: 30

# Trying to modify attributes
try:
    person.name = "Bob"  # Raises AttributeError: Cannot modify _name after initialization.
except AttributeError as e:
    print(e)

# Displaying the object
print(person)  # Output: ImmutablePerson(name=Alice, age=30)
```

Key Points:
- Immutable classes ensure that objects cannot be modified after creation.
- Use private attributes, getters, and __setattr__ to enforce immutability.
- __slots__ can be used to restrict attribute creation and improve memory efficiency.

Explanations
1. **Private Attributes**:
- The attributes `_x` and `_y` are marked as private by convention (using an underscore `_`.        
- They are set during initialization and cannot be modified afterward.

2. **Getters**:
- The `@property` decorator is used to create getters for `x` and `y`.
- No setters are provided, so the attributes cannot be modified after initialization.

3. **`__setattr__` Override**:
- The `__setattr__` method is overridden to raise an `AttributeError` if an attempt is made to modify an attribute after initialization.
- This ensures that the object remains immutable.

4. **Immutability**:
- Once an instance of `ImmutablePoint` is created, its attributes (`x` and `y`) cannot be changed.



