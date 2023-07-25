<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Behavioral/chain-of-responsibility-mini.png" height="150px" />
</p>

# الگو طراحی :  Chain Of Responsibility 🔗

# ✍️ توضیحات 
الگوی طراحی Chain of Responsibility یک الگوی ساختاری است که برای پردازش درخواست‌هایی با ماهیت یکسان و بر اساس یک الگوی پردازش مشابه، به کار می‌رود. در این الگو، یک زنجیره از شیء (object) ها در نظر گرفته می‌شود که هر کدام می‌توانند درخواست را پردازش کنند و در صورتی که نتوانستند، درخواست را به شیء بعدی در زنجیره انتقال می‌دهند. این الگو از ساختار درختی (hierarchical) پیروی می‌کند.

در الگوی Chain of Responsibility، هر شیء در زنجیره می‌تواند درخواست را پردازش کند و در صورتی که نتواند، درخواست را به شیء بعدی در زنجیره ارسال می‌کند. این رویه ادامه می‌یابد تا زمانی که شیءی در زنجیره پردازش درخواست را به درستی انجام دهد و یا هیچ شیءی در زنجیره باقی نماند. به عبارت دیگر، درخواست به صورت پویا بین شیء‌های مختلف جابجا می‌شود تا شیء مناسب برای پردازش درخواست پیدا شود.

استفاده از الگوی Chain of Responsibility در برنامه‌نویسی می‌تواند به بهبود انعطاف‌پذیری و قابلیت توسعه برنامه کمک کند. به عنوان مثال، در حوزه‌هایی مانند برنامه‌های حسابداری و پرداخت، الگوی Chain of Responsibility برای پردازش درخواست‌های پرداختی با مبالغ مختلف و به ترتیب اولویت مورد استفاده قرار می‌گیرد.
## مثال در دنیای واقعی:

به عنوان مثال، در حساب کاربری شما سه روش پرداخت (A، B و C) تنظیم شده است، هر کدام دارای مقدار متفاوتی هستند. A دارای 100 دلار، B دارای 300 دلار و C دارای 1000 دلار است و الگوی پرداخت به صورت A، B، C تنظیم شده است. شما سعی می‌کنید چیزی به ارزش 210 دلار بخرید. با استفاده از الگوی Chain of Responsibility، ابتدا حساب A بررسی می‌شود که آیا می‌تواند خرید را انجام دهد؛ اگر بله، خرید انجام شده و زنجیره شکسته می‌شود. اگر خیر، درخواست به حساب B منتقل می‌شود و می‌تواند خرید را انجام دهد، زنجیره شکسته می‌شود. در غیر این صورت، درخواست به حساب C منتقل می‌شود و اگر این حساب نیز نتواند خرید را انجام دهد، درخواست از قله زنجیره به سمت پایین پیش می‌رود تا یک مدیر مناسب پیدا شود. در اینجا A، B و C لینک‌های زنجیره هستند و کل فرایند به عنوان Chain of Responsibility شناخته می‌شود.

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **★⭐⭐**

**این الگو به ساخت یک زنجیره از شیء کمک می‌کند. درخواست از یکی از سرها وارد می‌شود و از شیء به شیء پیش می‌رود تا کنترل کننده مناسب را پیدا کند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
class Handler:
    def __init__(self, successor):
        self._successor = successor

    def handle(self, request):
        handled = self._handle(request)

        if not handled:
            self._successor.handle(request)

    def _handle(self, request):
        raise NotImplementedError()
        
class ConcreteHandler1(Handler):
    def _handle(self, request):
        if 0 < request <= 10:
            print("Request {} handled in handler 1".format(request))
            return True
        
class ConcreteHandler2(Handler):
    def _handle(self, request):
        if 10 < request <= 20:
            print("Request {} handled in handler 2".format(request))
            return True
        
class DefaultHandler(Handler):
    def _handle(self, request):
        print("Default handler")
        return True

handler1 = ConcreteHandler1(ConcreteHandler2(DefaultHandler(None)))

requests = [2, 5, 14, 22]

for request in requests:
    handler1.handle(request)```

