<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/facade-mini.png" height="150px" />
</p>

# الگو طراحی :  Facade 📦
 
# ✍️ توضیحات 
الگوی طراحی Facade یک الگوی ساختاری است که به شما این امکان را می‌دهد که یک واسط ساده و یکنواخت برای دسترسی به یک سیستم پیچیده‌تر ارائه دهید.

به عبارت دیگر، Facade یک لایه از سطح بالاتر برای دسترسی به سیستم پایین‌تر فراهم می‌کند و به شما این امکان را می‌دهد که با یک رابط ساده، به قابلیت‌های پیچیده‌تر سیستم دسترسی پیدا کنید. این الگو به شما این امکان را می‌دهد که با ابداع یک واسط ابتدایی، یک سیستم پیچیده را به راحتی کنترل کنید.
## مثال در دنیای واقعی:
برای روشن کردن رایانه کافیه دکمه پاور رو فشار بدهید. این کار ساده به نظر میاد، ولی درون رایانه کارهای پیچیده‌ای برای روشن شدن انجام میده. دکمه پاور یه رابط ساده برای سیستم پیچیده‌ست که بهش نمای نمایشی یا Facade میگویند.

 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **★⭐⭐**

**الگوی نمای نمایشی یا Facade، یک رابط ساده را برای دسترسی به یک سیستم پیچیده فراهم می‌کند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class ComplexSystem:
    def method1(self):
        print("ComplexSystem: Method 1")

    def method2(self):
        print("ComplexSystem: Method 2")

class Facade:
    def __init__(self):
        self.complex = ComplexSystem()

    def method_a(self):
        print("Facade: Method A")
        self.complex.method1()

    def method_b(self):
        print("Facade: Method B")
        self.complex.method2()

def client():
    facade = Facade()
    facade.method_a()
    facade.method_b()

if __name__ == "__main__":
    client()```

