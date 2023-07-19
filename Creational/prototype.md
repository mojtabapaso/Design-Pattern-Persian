<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/prototype-mini.png" height="150px" />
</p>

# الگو طراحی :  Prototype 🐑

# ✍️ توضیحات 
توضیح بلند

## مثال در دنیای واقعی:
رویانا را میشناسید؟ گوسفندی که شبیه سازی شد! اجازه دهید وارد جزئیات نشویم، اما نکته کلیدی در اینجا این است که همه چیز در مورد شبیه سازی است.

⚠️ برای کسب اطلاعات بیشتر `رویانا شبیه سازی شده` در اینترنت جست و جو کنید.

## چه زمانی استفاده کنیم ؟

زمانی استفاده می‌شود که یک شیء مورد نیاز است که شبیه به یک شیء موجود باشد یا ایجاد آن هزینه‌بر باشد و بهتر است از روش کپی برداری از شیء موجود استفاده شود.
  

 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **★⭐⭐**

**ایجاد یک شیء جدید بر اساس یک شیء موجود با استفاده از کپی کردن (Clone) آن.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
import copy

class Prototype:
    def clone(self):
        pass

class Person(Prototype):
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def clone(self):
        return copy.copy(self)

# Create a prototype person
proto_person = Person("John", 30)

# Create a new person instance using the prototype
new_person = proto_person.clone()

# Display the information for the new person
print("Name:", new_person.name)
print("Age:", new_person.age)
```
