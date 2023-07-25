<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/bridge-mini.png" height="150px" />
</p>

# الگو طراحی :  Bridge 🚡
 
# ✍️ توضیحات 
الگوی طراحی Bridge یک الگوی ساختاری است که برای جداسازی واسط (Interface) از پیاده‌سازی آن استفاده می‌شود. این الگو به شما اجازه می‌دهد تا اجزای سیستم را به صورت مستقل از یکدیگر طراحی کنید و از ارتباطات مستقیم بین آنها جلوگیری کنید.

در این الگو، یک کلاس (یا گروهی از کلاس‌ها) وظیفه ایجاد ارتباط با کلاس دیگری را دارد که به عنوان پل (Bridge) شناخته می‌شود. این پل می‌تواند بین چندین کلاس و چندین ارتباط گوناگون ایجاد کند. پل واسطی بین این کلاس ها بوجود می آورد که با استفاده از آن می توانند با هم ارتباط برقرار کنند.

با استفاده از الگوی طراحی Bridge، می‌توانید تغییراتی را در یک کلاس اعمال کنید بدون این که برای تغییر کلاس‌های دیگر در سیستم تأثیری داشته باشید. علاوه بر این، این الگو به شما امکان می‌دهد تا کلاس‌های مختلفی را با هم ترکیب کنید و به راحتی گسترش دهید. به عبارت دیگر، این الگو از لحاظ انعطاف پذیری بسیار قوی است.

## مثال در دنیای واقعی:
وقتی یک وب سایت با صفحات مختلف دارید و باید به کاربر اجازه دهید تا تم را تغییر دهد، آیا برای هر تم چندین نسخه از هر صفحه را ایجاد می‌کنید یا فقط تم‌های مختلف را ایجاد کرده و بر اساس ترجیحات کاربر آن را بارگیری می‌کنید؟ الگوی Bridge به شما اجازه می‌دهد که روش دوم را انجام دهید، به عبارت دیگر، تم‌های مختلف را ایجاد کرده و بر اساس ترجیحات کاربر آن را بارگیری کنید.

 # 📝 خلاصه :
**پیچیدیگی** : **⭐⭐⭐** 

م**حبوبیت** : **★★⭐**

**الگوی طراحی Bridge در واقع به این معناست که بهتر است از ترکیب شیء‌ها به جای وراثت استفاده کنیم. در این الگو، جزئیات پیاده‌سازی از یک سلسله مراتب به یک شیء دیگر با یک سلسله مراتب جداگانه منتقل می‌شود.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
# The implementation interface 
class DrawingAPI:
   def draw_circle(self, x, y, radius):
       pass

# Concrete implementation 1
class DrawingAPI1(DrawingAPI):
   def draw_circle(self, x, y, radius):
       print("API1.draw_circle(), x:", x, "y:", y, "radius:", radius)

# Concrete implementation 2  
class DrawingAPI2(DrawingAPI):
   def draw_circle(self, x, y, radius):
       print("API2.draw_circle(), x:", x, "y:", y, "radius:", radius)
       
# The abstraction 
class Shape:
   def __init__(self, drawing_api):
       self._drawing_api = drawing_api

   def draw(self):            
       pass
       
# Refined abstraction
class CircleShape(Shape):
   def __init__(self, x, y, radius, drawing_api):
       super().__init__(drawing_api)
       self._x = x
       self._y = y  
       self._radius = radius

   def draw(self):
       self._drawing_api.draw_circle(self._x, self._y, self._radius)
       
# Usage:
circle1 = CircleShape(1, 2, 3, DrawingAPI1())
circle1.draw()

circle2 = CircleShape(5, 7, 11, DrawingAPI2()) 
circle2.draw()
```
