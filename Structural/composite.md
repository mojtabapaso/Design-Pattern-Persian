<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/composite-mini.png" height="150px" />
</p>

# الگو طراحی :  Composite 🌿

# ✍️ توضیحات 
الگوی طراحی Composite یک الگوی ساختاری است که به شما اجازه می‌دهد چندین شیء را در یک ساختار درختی ترکیب کنید. این الگو به شما این امکان را می‌دهد که با استفاده از یک روش یکنواخت، با همه‌ی این شیء‌ها به یک شیء مشابه برخورد کنید. این الگو به شما امکان می‌دهد تا با استفاده از یک شیء پیچیده، شیء‌های ساده را به صورت سلسله مراتبی ترکیب کنید و با یک روش یکنواخت با همه‌ی این شیء‌ها به صورت یک شیء مشابه برخورد کنید.

## مثال در دنیای واقعی:
هر سازمانی از کارکنان تشکیل شده است. هر یک از کارکنان ویژگی‌های مشابهی دارند، به عنوان مثال حقوق دارند، مسئولیت‌هایی دارند، ممکن است به شخصی گزارش دهند یا ندهند و ممکن است زیردست‌هایی داشته باشند یا نداشته باشند.

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **★⭐⭐**

**الگوی طراحی Composite به مشتریان اجازه می‌دهد تا با اشیاء فردی به یک شیء یکنواخت برخورد کنند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class Component:
    def operation(self):
        pass

class Leaf(Component):
    def operation(self):
        print("Leaf")

class Composite(Component):
    def __init__(self):
        self.children = []

    def add(self, child):
        self.children.append(child) 

    def remove(self, child):
        self.children.remove(child)

    def operation(self):
        for child in self.children:
            child.operation()

leaf1 = Leaf()
leaf2 = Leaf()

composite = Composite()
composite.add(leaf1)
composite.add(leaf2)

composite.operation()
```
