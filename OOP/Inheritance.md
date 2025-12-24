---
cssclasses:
  - cornell-left
  - cornell-border
---
>[!cue] 
>1. what is a chid class
>2. what is a parent class
>3. how to define a child class

>[!summary] inheritance allows classes to reuse attributes and methods from a parent class. Child classes can also define their own behaviour while still sharing common functionality, making code more reusable and organized.



## Core Idea

> [!definition]  
> **Inheritance** allows a class to **inherit attributes and methods** from another class.

- Similar to how a **child inherits traits from a parent**
- Promotes **code reusability** and **extensibility**

```python
class Father:
	height = 182
	color = "pink"
	
class son(Father):
	pass
```
>[!note]  
`Son` automatically has access to `height` and `color`.



```python
class Animal:
	
	def __init__(self, name):
		self.name = name
		self.is_alive = True
		
	def eat(self):
		print(f"the animal {self.name} is eating.")
	
	def sleep(self):
		print(f"{self.name} is sleeping")

class Dog(Animal):
	pass
	
class Cat(Animal):
	pass
class Mouse(Animal):


dog = Dog("Scooby")
cat = Cat("Garfield")
mouse = Mouse("Mickey")


dog.eat()
cat.sleep()
mouse.is_alive

```
>[!important]  
Child classes must use **parentheses** to specify the parent class.

> [!tip]  
> All child classes automatically inherit:
> 
> - `name`
>     
> - `is_alive`
>     
> - `eat()`
>     
> - `sleep()`




##  Adding Unique Behavior to Child Classes

> [!definition]  
> Child classes can have **their own attributes and methods** not shared by the parent or siblings.



```python
class Animal:
	
	def __init__(self, name):
		self.name = name
		self.is_alive = True
		
	def eat(self):
		print(f"the animal {self.name} is eating.")
	
	def sleep(self):
		print(f"{self.name} is sleeping")

class Dog(Animal):
    def __init__(self, name, color):#will be covered later
        super().__init__(name)
        self.color = color

class Cat(Animal):
	def lick(self):
		print(f"{self.name} is cleaning")
class Mouse(Animal):
	def steamBoat(self):
		print("oh what a classic!")


dog = Dog("Scooby", "Brown")
cat = Cat("Garfield")
mouse = Mouse("Mickey")

print(dog.color())
cat.lick()
mouse.steamBoat()
```
>[!important]  
`super()` ensures the **parent constructor runs**.


##  Common Mistakes 

> [!warning]
> 
> -  Forgetting `super().__init__()`
>     
> -  Calling attributes like methods (`dog.color()`)
>     
> -  Missing `pass` in empty child classes


[[Multiple Inheritence]]

