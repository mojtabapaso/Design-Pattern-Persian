<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/singleton-mini.png" height="150px" />
</p>

# الگو طراحی : Singleton 💍
# ✍️ توضیحات 

الگوی طراحی Singleton یکی از الگوهای طراحی رایج در برنامه‌نویسی است که برای اطمینان از اینکه یک کلاس تنها یک نمونه از خود دارد، استفاده می‌شود. با استفاده از این الگو، امکان ایجاد چند نمونه از یک کلاس را به صورت تصادفی یا ناخواسته کاهش می‌دهیم و تضمین می‌شود که همیشه تنها یک نمونه از کلاس مورد نظر وجود دارد.

## مثال در دنیای واقعی:
تنها یک رییس جمهور در یک کشور وجود دارد و همیشه همان رییس جمهور برای انجام وظایف دعوت می‌شود. در اینجا، رییس جمهور نمونه‌ی Singleton است.



 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **★⭐⭐**

**اطمینان حاصل می‌کند که تنها یک شیء از یک کلاس خاص ایجاد می‌شود.**

# 👨🏻‍💻 مثال  :
Python 🐍

کلاس Singleton می‌تواند به روش‌های مختلفی در پایتون پیاده‌سازی شود. برخی از روش‌های ممکن شامل: کلاس پایه، دکوراتور و متاکلاس هستند. ما از متاکلاس استفاده خواهیم کرد زیرا برای این منظور مناسب‌تر است.



```python
class Singleton:
    _instance = None

    def __new__(cls):
        if cls._instance is None:
            cls._instance = super(Singleton, cls).__new__(cls)
        return cls._instance

# Usage:

s1 = Singleton()
print(s1)

s2 = Singleton() 
print(s2)

# s1 and s2 point to the same instance
print(s1 is s2) # True

```
