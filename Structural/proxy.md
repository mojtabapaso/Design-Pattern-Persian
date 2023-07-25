<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/proxy-mini.png" height="150px" />
</p>

# الگو طراحی :  Proxy 🎱

# ✍️ توضیحات 
الگوی طراحی پروکسی یک الگوی ساختاری است که در آن یک کلاس (یا شیء) دیگر را نمایندگی می‌کند و به عنوان یک واسط (interface) برای آن عمل می‌کند. این الگو برای کنترل دسترسی به یک شیء، بهینه سازی عملکرد و یا پوشش دادن به یک سیستم استفاده می‌شود.

در الگوی پروکسی، یک کلاس پروکسی از یک کلاس اصلی (واقعی) استفاده می‌کند و به عنوان یک پوشش برای آن کلاس عمل می‌کند. پروکسی همان عملکرد را دارد که کلاس اصلی دارد، اما ممکن است برخی از عملیات‌ها را برای بهبود عملکرد به صورت مجزا پیاده سازی کند.

## مثال در دنیای واقعی:
آیا تا به حال از کارت دسترسی برای عبور از در استفاده کرده‌اید؟ درهایی وجود دارند که چندین گزینه برای باز شدن دارند، به عنوان مثال می‌توان این درها را با استفاده از کارت دسترسی باز کرد یا با فشردن دکمه‌ای که اقدامات امنیتی را نادیده می‌گیرد، درها باز می‌شوند. عملکرد اصلی این درها باز کردن است، اما یک پروکسی بر روی آن‌ها قرار داده شده است تا برخی عملکردهای دیگر را به آن‌ها اضافه کند.

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **★★⭐**

**با استفاده از الگوی پروکسی، یک کلاس عملکرد یک کلاس دیگر را نمایان می‌کند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
from abc import ABC, abstractmethod

class Subject(ABC):
    @abstractmethod
    def request(self):
        pass

class RealSubject(Subject):
    def request(self):
        print("RealSubject: Handling request.")

class Proxy(Subject):
    def __init__(self):
        self._real_subject = RealSubject()

    def request(self):
        if self.check_access():
            self._real_subject.request()
            self.log_access()
        else:
            print("Proxy: Not authorized to fulfill request.")

    def check_access(self):
        print("Proxy: Checking access prior to firing a real request.")
        return True

    def log_access(self):
        print("Proxy: Logging the time of request.", end="")

proxy = Proxy()
proxy.request()```

