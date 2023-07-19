<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/singleton-mini.png" height="150px" />
</p>

# الگو طراحی : Singleton 💍
# ✍️ توضیحات 

الگوی طراحی Singleton یکی از الگوهای طراحی رایج در برنامه‌نویسی است که برای اطمینان از اینکه یک کلاس تنها یک نمونه از خود دارد، استفاده می‌شود. با استفاده از این الگو، امکان ایجاد چند نمونه از یک کلاس را به صورت تصادفی یا ناخواسته کاهش می‌دهیم و تضمین می‌شود که همیشه تنها یک نمونه از کلاس مورد نظر وجود دارد.
 # 📝 خلاصه :
**پیچیدیگی** : **آسان** 

م**حبوبیت** : **متوسط**

# 👨🏻‍💻 مثال  :
کلاس Singleton می‌تواند به روش‌های مختلفی در پایتون پیاده‌سازی شود. برخی از روش‌های ممکن شامل: کلاس پایه، دکوراتور و متاکلاس هستند. ما از متاکلاس استفاده خواهیم کرد زیرا برای این منظور مناسب‌تر است.
Python 🐍
```python
class MySingleton:
    _instance = None
  
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance


class Singleton(metaclass=SingletonMeta):
    def some_business_logic(self):
     ...



```
