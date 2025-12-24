---
cssclasses:
  - cornell-left
  - cornell-border
---


>[!cue]
>1.What are Class Variables?
>2.What are Instance Variables?
>3.Why use Class Variables?
>4.Why use Instance Variables?
>5.Using Class Variables for Shared Data
>6.Best Practices



>[!summary] Class variables are shared across all instances of the Class and are defined outside of the constructor.
>Values of instance variables are unique to the Object not the class and they are defined within `__init__` constructor.
>Class variables should be accessed with the class name to avoid confusion.



## Class Variables vs Instance Variables

---

### Key Idea

> [!definition]  
> **Class variables** are shared among **all instances** of a class.  
> **Instance variables** belong to **one specific object**.

---

### Where They Are Defined

| Variable Type     | Where it is defined                      | Scope                 |
| ----------------- | ---------------------------------------- | --------------------- |
| Class Variable    | Inside the class, **outside `__init__`** | Shared by all objects |
| Instance Variable | Inside `__init__` using `self`           | Unique to each object |
```python
class Car:
	wheels = 4 #=> Class Variable
	def __init__(self, model, year):
		self.model = model #=> instance variable
		self.year = year
```

>[!note]
>- `wheels` is shared by **all cars**  
>- `model` and `year` are **unique per car**

### Why Use Class Variables?

> [!tip]  
> Class variables are used to define **what is common across all instances** of a class.

**Car Example:**

- `model`  varies
- `year`  varies
- `wheels`  always the same
#### Example:
```python
class Student:
	
	species = "Human"
	
	def __init__(self, name, age):
		self.name = name
		self.age = age
		
student1 = Student("John", 23)
student2 = Student("Doe", 27)

print(student1.name)# John 
print(student2.name)# Doe

print(student1.species) # Human
print(student2.species) # Human
```
> [!important]  
> Even though `species` is accessed through objects here, it is still **shared**.


### Best Practice: Access Class Variables via the Class

> [!warning]  
> You _can_ access class variables through objects —  
> but it’s **better practice** to use the **class name**.

```python
class Student:
	
	species = "Human"
	
	def __init__(self, name, age):
		self.name = name
		self.age = age
		
student1 = Student("John", 23)
student2 = Student("Doe", 27)

print(student1.name)# John 
print(student2.name)# Doe

print(student1.species) # Human | => Bad Practice
print(student2.species) # Human | 


print(Student.species) # Human | Good Practice
```
>[!tip]  
This makes it **clear** that `species` is a **class variable**, not an instance variable.

### Using Class Variables for Shared Data

#### Counting Objects Created
Now we can utilize the class variable in all manner of ways:

```python
class Student:
	
	num_students = 0 
	
	species = "Human"
	
	def __init__(self, name, age):
		self.name = name
		self.age = age
		Student.num_students += 1
		
student1 = Student("John", 23)
student2 = Student("Doe", 27)

```
>[!note]  
`num_students` increases **every time a new object is created** because `__init__` runs automatically.

### Why We Use `Student.num_students` Instead of `self.num_students`

> [!important]  
> We use the **class name**, not `self`, because:
> 
> - `num_students` belongs to the **class**
>     
> - Using `self` would imply it belongs to **each object**
>

#### Correct
```python
Student.num_students += 1
```

#### Wrong
```python
self.num_students += 1
```


##  Quick Comparison

|Feature|Class Variable|Instance Variable|
|---|---|---|
|Belongs to|Class|Object|
|Shared?|Yes|No|
|Defined using|Class name|`self`|
|Example|`Student.num_students`|`self.name`|


what we do in the above code is that we initiate a class variable named` num_students` and set it's value to 0, after that within the constructor we increment the value whenever a new instance of the class (an object) is created as `__init__` gets automatically executed whenever a new instance is created.

!! also keep in mind that we didn't use the `self` key word on the last variable but rather we used the Class name as this variable (the last one) is intended to be in relation with the Class variable called `num_students`.