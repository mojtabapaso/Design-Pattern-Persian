<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/adapter-mini.png" height="150px" />
</p>

# الگو طراحی :  Adapter 🔌

# ✍️ توضیحات 
الگوی طراحی آداپتور، یک الگوی کاربردی است که به شما این امکان را می‌دهد که یک شیء را به یک شیء دیگر تبدیل کنید و آن را با کلاس‌های دیگر سازگار کنید. 

## مثال در دنیای واقعی:
فرض کنید شما چند عکس در کارت حافظه خود دارید و نیاز دارید آن‌ها را به کامپیوتر خود منتقل کنید. برای انتقال آن‌ها، نیاز به یک نوع آداپتور دارید که با پورت‌های کامپیوتر شما سازگار باشد تا بتوانید کارت حافظه را به کامپیوتر متصل کنید. در این مورد، خواننده کارت حافظه یک آداپتور است مثال دیگری هم ممکن است مترجم باشد که کلمات گفته شده توسط یک فرد را برای دیگری ترجمه می‌کند.

 # 📝 خلاصه :
**پیچیدیگی** : **★★⭐** 

م**حبوبیت** : **⭐⭐⭐**

**الگوی آداپتور به شما این امکان را می‌دهد که اشیاءی که ساختار و رابطه‌ی متفاوتی دارند را با یکدیگر ارتباط دهید و سازگار کنید.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
# The old interface
class Old Calculator:
    def operations(self, txt):
        return "Here is the result: " + str(eval(txt))

# The new interface  
class NewCalculator:
    def execute(self, expression):
        return expression.calculate()

# The adapter class
class CalculatorAdapter(NewCalculator):
    def __init__(self, old_calculator):
        self.old_calculator = old_calculator

    def execute(self, expression):
        result = self.old_calculator.operations(expression)
        return result

# Usage
old_calculator = OldCalculator()
new_calculator = CalculatorAdapter(old_calculator)

print(new_calculator.execute("1 + 2"))
# Prints "Here is the result: 3"
```
