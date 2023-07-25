<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/decorator-mini.png" height="150px" />
</p>

  # الگو طراحی :  Decorator ☕

# ✍️ توضیحات 
الگوی طراحی Decorator یک الگوی ساختاری است که به شما این امکان را می‌دهد که به یک شیء اضافه‌کاری کنید بدون این که بخشی از کد شیء اصلی را ویرایش کنید. در این الگو، یک شیء اصلی و یک یا چند شیء دکوراتور وجود دارد که قابلیت اضافه کردن خصوصیات جدید به شیء اصلی را دارند. هر دکوراتور می‌تواند یک یا چند ویژگی را به شیء اصلی اضافه کند.

با استفاده از الگوی طراحی Decorator، می‌توانید به یک شیء به صورت پویا و در زمان اجرا، ویژگی‌های جدیدی را اضافه کنید. به عنوان مثال، در یک برنامه فروشگاهی، می‌توانید به یک محصول آنلاین امکان اضافه کردن گزینه‌های ارسال، بسته‌بندی و هدیه را به صورت پویا اضافه کنید و به راحتی نیازهای مشتریان را برآورده کنید.

به طور خلاصه، الگوی طراحی Decorator اجازه می‌دهد تا شیء‌های موجود را با قابلیت‌های جدید و به صورت پویا ترکیب کنید و از ویرایش کد اصلی آنها جلوگیری کنید.

## مثال در دنیای واقعی:
فرض کنید که یک کارگاه خدمات خودرو با چندین خدمات مختلف راه‌اندازی کرده‌اید. حال چگونه هزینه‌ی خدمات ارائه شده را محاسبه کنید؟ شما یکی از خدمات را انتخاب کرده و به آن پوشش خدمات دیگر را به صورت پویا اضافه می‌کنید تا در نهایت هزینه نهایی را به دست آورید. در اینجا هر نوع خدمات یک دکوراتور است.

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **★⭐⭐**

**الگوی طراحی Decorator به شما این امکان را می‌دهد که با قرار دادن یک شیء درون یک شیء از کلاس دکوراتور، به صورت پویا و در زمان اجرا، رفتار یک شیء را به صورت دینامیک تغییر دهید.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
from abc import ABC, abstractmethod

class Coffee(ABC):
    @abstractmethod
    def get_cost(self):
        pass
    
    @abstractmethod    
    def get_ingredients(self):
        pass

class SimpleCoffee(Coffee):
    def get_cost(self):
        return 1.0
    
    def get_ingredients(self):
        return 'Coffee'

class CoffeeDecorator(Coffee):
    def __init__(self, decorated_coffee):
        self.decorated_coffee = decorated_coffee

    def get_cost(self):
        return self.decorated_coffee.get_cost()

    def get_ingredients(self):
        return self.decorated_coffee.get_ingredients()

class WithMilk(CoffeeDecorator):
    def __init__(self, decorated_coffee):
        CoffeeDecorator.__init__(self, decorated_coffee)

    def get_cost(self):
        return self.decorated_coffee.get_cost() + 0.5
    
    def get_ingredients(self):
        return self.decorated_coffee.get_ingredients() + ', Milk'

simple_coffee = SimpleCoffee()
print(simple_coffee.get_cost())
print(simple_coffee.get_ingredients())

coffee_with_milk = WithMilk(simple_coffee)
print(coffee_with_milk.get_cost())
print(coffee_with_milk.get_ingredients())
```

