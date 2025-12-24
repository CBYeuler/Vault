---
cssclasses:
  - cornell-border
  - cornell-left
---


>[!cue]
>1. what is an Object?
>2. What are Attributes?
>
>3. What are Methods?
>4. What is a Class?
>5. What is `__init__`?


>[!summary] 
An object is a bundle of attributes and methods related to a specific item.  
Attributes describe what an object **has**, while methods describe what it **does**.  
A class acts as a blueprint for creating objects, and `__init__` is the constructor that runs automatically when an object is created.


## Object

> [!definition]  
> An **object** is a _bundle_ of related **attributes** (variables) and **methods** (functions).

- **Attributes** → what the object **has**
    
- **Methods** → what the object **does**
    

---

###  Examples of Objects & Attributes

| **Object** | **Attributes (What it has)**             |
| ---------- | ---------------------------------------- |
| Phone      | `version_num`, `is_on`, `price`, `model` |
| Cup        | `liquid`, `temp`, `is_empty`             |
| Book       | `title`, `pages`                         |

---

###  Attribute

> [!note]  
> An **attribute** describes an object —  
> what it **has** and what it **does not have**.

- Stored as **variables**
    
- Represents the **state** of the object
    
- Example:
    
    - A phone **has** a price
        
    - A cup **has** a temperature
        

---
### Examples of Objects & Methods

| Object | Methods (What it does)                                             |
| ------ | ------------------------------------------------------------------ |
| Phone  | ``make_call()``, ``receive_call()``, ``turn_on()``, ``turn_off()`` |
| Cup    | ``fill_cup()``, ``empty_cup()``,`` drink_cup()``                   |
| Book   | ``open_book()``, ``close_book()``, ``read_book()``                 |

---

###  Method

> [!tip]  
> A **method** defines what an object **does**.

- A method is a **function that belongs to an object**
    
- It usually **uses or changes attributes**
    

**Examples:**

- A phone can `turn_on()`
    
- A cup can `empty()`
    
- A book can `open()`
    

---

###   Quick Comparison

| **Attribute**           | **Method**               |
| ----------------------- | ------------------------ |
| What the object **has** | What the object **does** |
| Variable                | Function                 |
| Describes state         | Describes behavior       |


## Class

> [!definition]  
> A **class** is used to design the **structure and layout** of an object —  
> basically, a **blueprint**.

A class defines:

- **Attributes** → what the object **has**
    
- **Methods** → what the object **can do**
    

---

###  Class Concept (Quick Overview)

| Concept   | Meaning                             |
| --------- | ----------------------------------- |
| Class     | Blueprint                           |
| Object    | Instance made from the blueprint    |
| Attribute | Data stored in the object           |
| Method    | Function that belongs to the object |

---

###  Example: Creating a Class

```python
class Car:
	def __init__(self, model, year, color, for_sale):
		self.model = model
		self.year = year
		self.color = color
		self.for_sale = for_sale

car1 = Car("Mustang", "1967", "Red", False)
```


> [!note]  
> The `__init__` method is a **constructor**.  
> It runs automatically when a new object is created.

---

###  Creating an Object from the Class

`car1 = Car("Mustang", "1967", "Red", False)`

> [!tip]  
> `car1` is an **object (instance)** created from the `Car` class blueprint.

---

###  Printing the Object

`print(car1)`

> [!warning]  
> This prints the **memory address** of the object,  
> not its actual data.

---

### Accessing Attributes

To access information inside an object, we use the **attribute access operator** (`.`)

`print(car1.model)`

**Output:**

`Mustang`

> [!important]  
> The dot (`.`) lets you access an object’s **attributes and methods**.

---

### Attribute Access Summary

| Code            | Meaning                      |
| --------------- | ---------------------------- |
| `car1.model`    | Accesses the model attribute |
| `car1.year`     | Accesses the year            |
| `car1.color`    | Accesses the color           |
| `car1.for_sale` | Accesses sale status         |
### Methods in a Class
>[!definition]  
A **method** is a function **defined inside a class** that gives an object **behavior**.
```python
class Car:
	def __init__(self, model, year, color, for_sale):
		self.model = model
		self.year = year
		self.color = color
		self.for_sale = for_sale
	def drive(self):
		print(f"you are driving {self.model}")

car1 = Car("Mustang", "1967", "Red", False)
```
####  What’s Happening Here?

- `drive()` is a **method**
    
- It belongs to the `Car` class
    
- It uses the object’s data via `self`
    

> [!note]  
> `self` refers to the **current object** calling the method.

---

#### Creating an Object

```python
car1 = Car("Mustang", "1967", "Red", False)`
```
- `car1` is an **object (instance)** of the `Car` class
    
- It now has:
    
    - Attributes (`model`, `year`, `color`, `for_sale`)
        
    - Methods (`drive()`)
        

---

#### Calling the Method

`car1.drive()`

**Output:**

`you are driving Mustang`

> [!important]  
> Calling a method uses the **dot operator (`.`)**, just like accessing attributes.

---

## Method vs Attribute

|**Attribute**|**Method**|
|---|---|
|Stores data|Performs an action|
|Variable|Function|
|`car1.model`|`car1.drive()`|
