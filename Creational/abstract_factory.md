<p align="center">
  <img src="https://github.com/mojtabapaso/Design-Pattern-Persian/blob/main/img/Creational/abstract-factory-mini.png" height="150px" />
</p>

# الگو طراحی :  Abstract Factory 🔨

# ✍️ توضیحات 

الگو Abstract Factory یک الگوی طراحی (Design Pattern) در برنامه‌نویسی شی‌گرا است که به توسعه دهندگان اجازه می‌دهد یک مجموعه از اشیاء مرتبط را به صورت مستقل از سایر اشیاء ساختاردهی کنند.

این الگو به صورت یک ابزار برای ایجاد محصولات با خصوصیات مشترک استفاده می‌شود. در واقع، Abstract Factory مجموعه‌ای از Factory Methodها است که به صورت یکجا گروه‌بندی می‌شوند و همه آن‌ها یک مجموعه استانداردی از متد‌ها را پیاده‌سازی می‌کنند.

مزیت استفاده از Abstract Factory این است که به توسعه دهندگان اجازه می‌دهد که از ساختاری مستقل از اشیاء استفاده کنند و این امکان را برای آن‌ها فراهم می‌کند که به راحتی محصولاتی با خصوصیات مشابه و با کیفیت بالا ایجاد کنند. به علاوه، با استفاده از این الگو، می‌توانید محصولاتی را با کیفیت بالا ایجاد کنید که با استفاده از آن‌ها برنامه‌هایی با خصوصیات مشابه را ایجاد کنید.

بنابراین  Abstract Factory یک الگوی طراحی است که به توسعه دهندگان اجازه می‌دهد که محصولاتی با خصوصیات مشابه را به صورت مستقل از سایر اشیاء ساختاردهی کنند. این الگو به برنامه‌نویسان اجازه می‌دهد تا از ساختاری مستقل از اشیاء استفاده کنند و به راحتی محصولاتی را با کیفیت بالا برای برنامه‌های خود ایجاد کنند.
## مثال در دنیای واقعی:
در اینجا مثال درب از کارخانه ساده تراوش مورد ادامه قرار میدهیم. بهترین در را برای نیازهای خودتان می‌توانید از فروشگاه درب چوبی، فروشگاه درب آهنی یا فروشگاه درب پی وی سی بخرید. همچنین ممکن است نیاز به یک شخص با تخصص مختلف برای نصب درب داشته باشید، به عنوان مثال برای درب چوبی نیاز به یک نجار دارید، برای درب آهنی به یک جوشکار و غیره. همانطور که مشاهده می‌کنید، حالا وابستگی بین درها وجود دارد، درب چوبی به نجار نیاز دارد، درب آهنی به یک جوشکار نیاز دارد و غیره.

 # 📝 خلاصه :
**پیچیدیگی** : **★⭐⭐** 

م**حبوبیت** : **⭐⭐⭐**

**به زبان ساده، این به یک (Factory) کارخانه تولیدی اشاره دارد که کارخانه‌های جداگانه ولی وابسته به یکدیگر را با هم گروه بندی می‌کند، بدون این که نوع خاص و مشخص آن‌ها را مشخص کند.**

# 👨🏻‍💻 مثال  :
Python 🐍 


```python
from abc import ABC, abstractmethod

class AbstractFactory(ABC):
    """
    The Abstract Factory interface declares a set of methods that return
    different abstract products. These products are called a family and are
    related by a high-level theme or concept. Products of one family are usually
    able to collaborate among themselves. The Abstract Factory pattern separates
    product construction code from the code that actually uses the products.
    """
    
    @abstractmethod
    def create_product_a(self):
        pass

    @abstractmethod    
    def create_product_b(self):
        pass
    
class ConcreteFactory1(AbstractFactory):
    """
    Concrete Factories produce a family of products that belong to a single
    variant. The factory guarantees that resulting products are compatible. Note
    that signatures of the Concrete Factory's methods return an abstract product.
    """

    def create_product_a(self):
        return ConcreteProductA1()

    def create_product_b(self):
        return ConcreteProductB1()
        
class ConcreteFactory2(AbstractFactory):
    """
    Each Concrete Factory has a corresponding product variant.
    """

    def create_product_a(self):
        return ConcreteProductA2()

    def create_product_b(self):
        return ConcreteProductB2()

class AbstractProductA(ABC):
    """
    Each distinct product of a product family should have a base interface. All
    variants of the product must implement this interface.
    """

    @abstractmethod
    def useful_function_a(self):
        pass

"""
Concrete Products are created by corresponding Concrete Factories.
"""
class ConcreteProductA1(AbstractProductA):
    def useful_function_a(self):
        return "The result of the product A1."

class ConcreteProductA2(AbstractProductA):
    def useful_function_a(self):
        return "The result of the product A2."
        
class AbstractProductB(ABC):
    """
    Here's the the base interface of another product. All products can interact
    with each other, but proper interaction is possible only between products of
    the same concrete variant.
    """
    @abstractmethod
    def useful_function_b(self):
        pass
    
"""
Concrete Products are created by corresponding Concrete Factories.
"""
class ConcreteProductB1(AbstractProductB):
    def useful_function_b(self):
        return "The result of the product B1."
    
class ConcreteProductB2(AbstractProductB):
    def useful_function_b(self):
        return "The result of the product B2."

def client_code(factory):
    """
    The client code works with factories and products only through abstract
    types: AbstractFactory and AbstractProduct. This lets you pass any factory or
    product subclass to the client code without breaking it.
    """
    product_a = factory.create_product_a()
    product_b = factory.create_product_b()

    print(f"{product_b.useful_function_b()}")
    print(f"{product_a.useful_function_a()}")


if __name__ == "__main__":
    """
    The client code can work with any concrete factory class.
    """
    print("Client: Testing client code with first factory type:")
    client_code(ConcreteFactory1())

    print("\n")

    print("Client: Testing same client code with second factory type:")
    client_code(ConcreteFactory2())
```
