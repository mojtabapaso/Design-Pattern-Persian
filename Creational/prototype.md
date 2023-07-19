<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/prototype-mini.png" height="150px" />
</p>

# الگو طراحی :  Prototype 🐑

# ✍️ توضیحات 
در الگوی طراحی Prototype، ما یک شیء اولیه (پروتوتایپ) ایجاد می کنیم و سپس با کپی کردن آن، شیء های جدیدی ایجاد می کنیم. این کار به ما کمک می کند تا زمان ساخت شیء ها را کاهش دهیم و از منابع کمتری استفاده کنیم.

## مثال در دنیای واقعی:
رویانا را میشناسید؟ گوسفندی که شبیه سازی شد! اجازه دهید وارد جزئیات نشویم، اما نکته کلیدی در اینجا این است که همه چیز در مورد شبیه سازی است.

⚠️ برای کسب اطلاعات بیشتر `رویانا شبیه سازی شده`را در اینترنت جست و جو کنید.

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

  def __init__(self):
    self._objects = {}

  def register(self, name, obj):
    self._objects[name] = obj

  def unregister(self, name):
    del self._objects[name]

  def clone(self, name, **attr):
    obj = copy.deepcopy(self._objects.get(name))
    obj.__dict__.update(attr)
    return obj

class Car:
  def __init__(self):
    self.name = "Unknown"
  def __str__(self):
    return self.name

prototype = Prototype()
c1 = Car()
c1.name = "Ford"
prototype.register('ford', c1)

c2 = prototype.clone('ford', name="Ferrari")

print(c1) # Ford
print(c2) # Ferrari
```
