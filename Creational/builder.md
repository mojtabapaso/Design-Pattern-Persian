<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/builder-mini.png" height="150px" />
</p>

# الگو طراحی :  Builder 👷
 
# ✍️ توضیحات 
توضیح بلند

## مثال در دنیای واقعی:
مثال

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **⭐⭐⭐**

**به طور خلاصه به شما اجازه می دهد نسخه های مختلفی از یک شیء را ایجاد کنید و در عین حال از آلودگی سازنده (Constructor Pollution) خودداری کنید. این الگو در مواردی که ممکن است چندین نسخه از یک شیء وجود داشته باشد یا وقتی که برای ایجاد یک شیء چندین مرحله لازم است، مفید است.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class Car:

    def __init__(self):
        self.wheels = None
        self.doors = None
        self.engine = None
        self.seats = None

class CarBuilder:

    def __init__(self):
        self.car = Car()

    def add_wheels(self):
        self.car.wheels = 4
        return self
    
    def add_doors(self):
        self.car.doors = 4
        return self

    def add_engine(self):
        self.car.engine = 'V8'
        return self 

    def add_seats(self):
        self.car.seats = 5
        return self

    def build(self):
        return self.car

builder = CarBuilder()
car = builder.add_wheels().add_doors().add_engine().add_seats().build()

print(car.wheels) # 4
print(car.doors) # 4
print(car.engine) # V8 
print(car.seats) # 5
```

