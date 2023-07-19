

# الگو طراحی :  Simple Factory 🏠

# ✍️ توضیحات 
الگوی طراحی Simple Factory یکی از الگوهای اصلی طراحی نرم‌افزار است که در آن یک کلاس مسئولیت ایجاد شیء (Object) را بر عهده دارد. به عبارت دیگر، این الگو به ما این امکان را می‌دهد که ایجاد شیء را به یک کلاس مرکزی (Factory) واگذار کنیم.
این الگو به دلیل سادگی و قابلیت استفاده در موارد مختلف، به عنوان یک الگوی طراحی ساده و مؤثر شناخته می‌شود. در این الگو، یک کلاس Factory مسئول ایجاد شیء است، به طوری که کاربر (Client) با فراخوانی یک متد از کلاس Factory، شیء مورد نیاز را دریافت می‌کند.
با استفاده از الگوی طراحی Simple Factory، ما می‌توانیم کد خود را از ایجاد شیء مستقل کنیم و از این طریق، کدی ساده‌تر و قابل توسعه‌تر داشته باشیم. همچنین، با ایجاد یک کلاس Factory مرکزی، می‌توانیم کد خود را از تغییرات آینده در ایجاد شیء مستقل کنیم.

## مثال در دنیای واقعی:
تصور کنید که دارید خانه ای می سازید و به در نیاز دارید. می توانید لباس کار بپوشید و با چند تخته چوب، چسب، میخ و تمام ابزارهای لازم برای ساخت در، در را در خانه خود بسازید.اما اگر نمی خواهید با این دردسر ها که با ساخت در همراه است، سر و کار داشته باشید. میتوانید از یک مغازه در چوبی آماده ای خریداری کنید با این کار نیازی به یادگیری هیچ چیز در مورد ساخت در ندارید و با دریافت در آماده از مغازه ، وقت و انرژی خود را برای کارهای دیگر صرف خواهید کرد.

 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **⭐⭐⭐**

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
