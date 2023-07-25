<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Structural/flyweight-mini.png" height="150px" />
</p>

# الگو طراحی :  Flyweight 🍃

# ✍️ توضیحات 
الگوی Flyweight در برنامه‌نویسی، یک الگوی ساختاری است که برای بهینه‌سازی استفاده از منابع حافظه و کاهش هزینه‌های محاسباتی طراحی شده است. این الگو به اشتراک گذاشتن یک شیء بین چندین قسمت مختلف سیستم اجازه می‌دهد تا از حافظه کمتری استفاده کنند. به عبارتی دیگر، هر شیء در این الگو به عنوان یک نمونه (instance) و یک مشخصه (intrinsic property) تعریف می‌شود. نمونه‌ها می‌توانند بین چندین محل استفاده شوند، در حالی که مشخصات آنها ثابت می‌ماند.
## مثال در دنیای واقعی:
حتما تا به حالا چای نوشیده اید معمولا ما بیشتر از نیاز همان لحظه مان چای دم میکنیم تا شاید دوباره نیاز داشتیم و یا کسی دیگری چای میخواست  و با این کار میتوانید در وقت و انرژی مان صرفه جویی کنیم در الگوی Flyweight همه چیز درباره این است:**به اشتراک گذاشتن**.


 # 📝 خلاصه :
**پیچیدیگی** : **⭐⭐⭐** 

م**حبوبیت** : **★★★**

**این الگو برای کاهش استفاده از حافظه یا هزینه‌های محاسباتی با به اشتراک گذاشتن حداکثر ممکن با شیء‌های مشابه استفاده می‌شود.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class Flyweight:
    def __init__(self, shared_state):
        self.shared_state = shared_state

    def operation(self, unique_state):
        s = self.shared_state
        u = unique_state
        print(f"Flyweight: Displaying shared ({s}) and unique ({u}) state.")

class FlyweightFactory:
    _flyweights = {}

    def __init__(self, initial_flyweights):
        for state in initial_flyweights:
            self._flyweights[self.get_key(state)] = Flyweight(state)

    def get_key(self, state):
        return "_".join(sorted(state))

    def get_flyweight(self, shared_state):
        key = self.get_key(shared_state)

        if not self._flyweights.get(key):
            print("FlyweightFactory: Can't find a flyweight, creating new one.")
            self._flyweights[key] = Flyweight(shared_state)
        else:
            print("FlyweightFactory: Reusing existing flyweight.")

        return self._flyweights[key]

factory = FlyweightFactory([
    ["Chevrolet", "Camaro2018", "pink"], 
    ["Mercedes Benz", "C300", "black"],
    ["Mercedes Benz", "C500", "red"]
    ])

flyweight1 = factory.get_flyweight(["Mercedes Benz", "C300"])
flyweight1.operation(["DINAMIC", "UNIQUE", "STATE"])

flyweight2 = factory.get_flyweight(["Chevrolet", "Camaro2018"]) 
flyweight2.operation(["OTHER", "UNIQUE", "STATE"])
```

