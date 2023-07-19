

# الگو طراحی :  Simple Factory 🏠

# ✍️ توضیحات 
توضیح بلند

## مثال در دنیای واقعی:
تصور کنید که دارید خانه ای می سازید و به در نیاز دارید. می توانید لباس کار بپوشید و با چند تخته چوب، چسب، میخ و تمام ابزارهای لازم برای ساخت در، در را در خانه خود بسازید.اما اگر نمی خواهید با این دردسر ها که با ساخت در همراه است، سر و کار داشته باشید. میتوانید از یک مغازه در چوبی آماده ای خریداری کنید با این کار نیازی به یادگیری هیچ چیز در مورد ساخت در ندارید و با دریافت در آماده از مغازه ، وقت و انرژی خود را برای کارهای دیگر صرف خواهید کرد.

 # 📝 خلاصه :
**پیچیدیگی** : **خالی** 

م**حبوبیت** : **خالی**

**توضیح کوتاه**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class Animal:
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return "Woof!"

class Cat(Animal):
    def speak(self):
        return "Meow!"

class AnimalFactory:
    def create_animal(self, animal_type):
        if animal_type == "dog":
            return Dog()
        elif animal_type == "cat":
            return Cat()
        else:
            raise ValueError("Invalid animal type")

# Create an AnimalFactory instance
animal_factory = AnimalFactory()

# Create a dog and a cat using the factory
dog = animal_factory.create_animal("dog")
cat = animal_factory.create_animal("cat")

# Make the dog and cat speak
print(dog.speak())
print(cat.speak())
```
