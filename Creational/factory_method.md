<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/factory-method-mini.png" height="150px" />
</p>

# الگو طراحی :  Factory Method 🏭

# ✍️ توضیحات 

در این الگو، مسئولیت ساخت یک شیء به یک متد یا تابع خاص اختصاص داده می‌شود که به آن Factory Method گفته می‌شود. به عبارت دیگر، در این الگو، شیء‌سازی به یک کلاس جداگانه از کلاس‌هایی که نیاز به شیء دارند، منتقل می‌شود.

هدف اصلی الگوی Factory Method، ایجاد شیء به صورت پویا در زمان اجرا و بر اساس شرایط مختلف است. با استفاده از این الگو، می‌توانیم از تکراری شدن کد جلوگیری کنیم و باعث می‌شود که کد ما به صورت ماژولار و قابل توسعه‌تری باشد. همچنین، با استفاده از این الگو، می‌توانیم مسئولیت ساختار شیء را از کلاس‌هایی که از آن استفاده می‌کنند جدا کنیم و ماژولاریتی را افزایش دهیم.

در این الگو، یک کلاس سازنده یا Factory Class تعریف می‌شود که شامل یک یا چند Factory Method است. این Factory Method ها، به عنوان متد‌هایی در نظر گرفته می‌شوند که برای ساخت شیء مورد نیاز استفاده می‌شوند. در واقع، این متد‌ها به عنوان یک رابط برای ساخت شیء در نظر گرفته می‌شوند که باید در کلاس‌هایی که از آن استفاده می‌کنند، پیاده‌سازی شوند.

یکی از مزایای استفاده از الگوی Factory Method، این است که ما می‌توانیم با تغییر Factory Method، نوع شیء ساخته شده را تغییر دهیم. برای مثال، ما می‌توانیم یک Factory Method جدید برای ساخت شیء جدید اضافه کنیم و کد ما را بهبود بخشیم بدون اینکه نیاز به تغییر کد کلاس‌هایی که از شیء استفاده می‌کنند، داشته باشیم.

## چه زمانی استفاده کنیم ؟

 زمانی مفید است که در یک کلاس مقداری پردازش عمومی وجود داشته باشد اما زیر کلاس مورد نیاز به صورت پویا در زمان اجرا تصمیم گیری می شود. یا به عبارت دیگر، زمانی که مشتری نمی داند دقیقاً به چه زیر کلاسی نیاز دارد.

## مثال در دنیای واقعی:
یک مدیر استخدامی فرض کنید. او نمی‌تواند برای هر کدام از شغل‌ها مصاحبه کند، بلکه بر اساس شغل مورد نظر، باید تصمیم بگیرد و مراحل مصاحبه را به افراد مختلف واگذار کند.

 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **⭐⭐⭐**

**یک روش برای انتقال منطق نمونه‌سازی به کلاس‌های زیرمجموعه را فراهم می‌کند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python

class Vehicle:
    def __init__(self):
        self.num_wheels = None

    def drive(self):
        raise NotImplementedError

class Car(Vehicle):
    def __init__(self):
        self.num_wheels = 4
    
    def drive(self):
        print("Driving on 4 wheels")

class Bike(Vehicle):
    def __init__(self):
        self.num_wheels = 2

    def drive(self):
        print("Driving on 2 wheels")

class VehicleFactory:
    def create_vehicle(self, vehicle_type):
        if vehicle_type == "car":
            return Car()
        elif vehicle_type == "bike":
            return Bike()
        else:
            raise ValueError(f"Unsupported vehicle type: {vehicle_type}")

# Usage:
factory = VehicleFactory()
car = factory.create_vehicle("car")
car.drive() # Prints "Driving on 4 wheels"

bike = factory.create_vehicle("bike") 
bike.drive() # Prints "Driving on 2 wheels"
 
```
