# Python’da OOP (Obyektga yo‘naltirilgan dasturlash)

<div style="text-align: center;">
  <img src="https://miro.medium.com/v2/resize:fit:720/format:webp/1*Aepqo-jv2opyp0NzSaoa8w.jpeg" alt="pfSense Qoidasi" width="400"/>
</div>

Assalomu alaykum va xush kelibsiz! **Obyektga yo‘naltirilgan dasturlash** (**OOP — Object-Oriented Programming**) – bu keng qo‘llaniladigan dasturlash uslubi bo‘lib, 
u dasturchilarga **modulli (bo‘laklarga bo‘lingan)**, **qayta ishlatish mumkin bo‘lgan**, **oson boshqariladigan** va **kengaytirish mumkin bo‘lgan** kod yozishga yordam beradi.

Python — mashhur va ko‘p qirrali dasturlash tili bo‘lib, unda **OOP** g‘oyalarini amalga oshirish uchun kuchli vositalar mavjud. Ushbu maqolada biz Python’dagi **OOP asoslari** bilan tanishamiz, jumladan:

* **Encapsulation (inkapsulyatsiya)**
* **Inheritance (meros olish)**
* **Polymorphism (polimorfizm)**
* **Abstraction (abstraksiya)**
* **Best Practices (eng yaxshi amaliyotlar)**

Siz tajribali Python dasturchisi bo‘lasizmi yoki endi boshlayotgan bo‘lasizmi — bu **OOP tamoyillari**ni tushunish sizga yanada **tartibli**, **samarali** va **tushunarli** kod yozishga yordam beradi.

---

## Mundarija (Table of Contents)

1. OOP ga kirish
2. Encapsulation (inkapsulyatsiya)
3. Inheritance (meros olish)
4. Polymorphism (polimorfizm)
5. Abstraction (abstraksiya)
6. Best Practices (eng yaxshi amaliyotlar)

---


## 1. OOP ga kirish

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*K1qqTyj9AZsCbFufN7RGLg.jpeg)


**OOP (Object-Oriented Programming – obyektga yo‘naltirilgan dasturlash)** — dasturlashdagi muhim yondashuv bo‘lib, dasturiy ta’minot dizayni haqidagi qarashlarni tubdan o‘zgartirdi. OOP yordamida **obyektlar** yaratiladi. Obyekt ichida **ma’lumot (data)** ham, shu ma’lumot bilan ishlovchi **xatti-harakatlar (behavior)** ham jamlanadi. Bu yondashuv dasturchilarga murakkab tizimlarni yanada oson modellashtirish va **qayta foydalaniladigan (reusable)** kod yozish imkonini beradi.

O‘tkir afzalliklaridan biri shundaki, OOP yordamida dastur **modullarga bo‘linadi**. Ya’ni katta tizim obyektlarga bo‘linib, ular orqali kod kichikroq va boshqarilishi osonroq qismlarga ajratiladi. Bu esa vaqtni tejaydi va xatoliklar (bugs) ehtimolini kamaytiradi.

### Class (klass) tushunchasi

OOP ning markazida **klass** tushunchasi turadi. Klass — bu obyektlar yaratish uchun **chizma (blueprint)** hisoblanadi. Klass obyektning:

* **atributlari** (attributes – obyektning xususiyatlari, ya’ni o‘zgaruvchilar)
* **metodlari** (methods – obyektning xatti-harakatlarini ifodalovchi funksiyalar)

ni belgilaydi.

Klassdan obyekt yaratish jarayoni **instansiya qilish (instantiate)** deb ataladi. Buning uchun maxsus `__init__` metodi ishlatiladi. Bu metod obyekt yaratilgan zahoti avtomatik ishlaydi va atributlarni boshlang‘ich qiymatlar bilan to‘ldirishga imkon beradi.

### Oddiy misol:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def greet(self):
        print(f"Hello, my name is {self.name} and I am {self.age} years old.")
```

Bu yerda biz `Person` nomli **klass** yaratdik. Unda:

* `name` va `age` – atributlar,
* `greet` – metod.

`__init__` metodi esa yangi obyekt yaratilganda atributlarni boshlash uchun ishlatiladi.

### Obyekt yaratish:

```python
person1 = Person("Alice", 25)
```

Bu kod `person1` nomli yangi `Person` obyektini yaratadi. Unda `name` = `"Alice"`, `age` = `25`.

Metodni chaqirish:

```python
person1.greet()
```

Natija:

```
Hello, my name is Alice and I am 25 years old.
```

---

👉 Ko‘rib turganingizdek, klasslar yordamida kod tartibli bo‘ladi va obyektlar orqali ma’lumot ham, xatti-harakatlar ham bir joyda saqlanadi.


## 2. Encapsulation (Inkapsulyatsiya)

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*gmT0r_SYxVvt5SljKp_zWw.png)

**Encapsulation (inkapsulyatsiya)** — bu **OOP (Obyektga yo‘naltirilgan dasturlash)** ning to‘rt asosiy tamoyilidan biri (qolganlari: inheritance — meros olish, polymorphism — polimorfizm, abstraction — abstraksiya).

Inkapsulyatsiya deganda obyektning **ichki ishlash mexanizmlarini yashirish** va faqat tashqaridan kerakli qismlarigagina ruxsat berish tushuniladi. Bu obyekt ma’lumotlarini **xavfsiz saqlash** va **faqat kerakli yo‘lda foydalanish** imkonini beradi.

### Python’da encapsulation qanday ishlaydi?

Python’da inkapsulyatsiya **access modifiers (kirish darajalari)** orqali amalga oshiriladi:

* **public (ochiq)** — istalgan joydan murojaat qilish mumkin.
* **private (yopiq)** — faqat o‘sha klass ichida foydalanish mumkin (`__` bilan belgilanadi).

### Misol:

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.__age = age   # private (yopiq) o‘zgaruvchi

    def get_age(self):
        return self.__age

    def set_age(self, age):
        if age > 0:
            self.__age = age

person = Person("Alice", 30)
print(person.name)         # public
print(person.get_age())    # private qiymatni olish
person.set_age(-5)         # noto‘g‘ri qiymat
print(person.get_age())
```

### Tushuntirish:

* `name` — oddiy **public** atribut, tashqaridan bemalol chaqiriladi.
* `__age` — **private** atribut, faqat klass ichida ishlatilishi mumkin.
* `get_age()` va `set_age()` metodlari yordamida `__age` ni boshqarish mumkin.
* `set_age()` da qo‘shimcha shart (`age > 0`) qo‘yilgan — bu obyekt ma’lumotlari **to‘g‘ri ishlatilishini ta’minlaydi**.

👉 Demak, inkapsulyatsiya yordamida obyekt **o‘zini himoya qiladi** va faqat to‘g‘ri yo‘l bilan foydalanishga ruxsat beradi.

---

## 3. Inheritance (Meros olish)

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*iP78XqAbkntOuzbHCoiubg.png)

**Inheritance (meros olish)** — bu OOP’dagi kuchli tushuncha bo‘lib, yangi klassni mavjud klass asosida yaratishga imkon beradi.

* **Parent (superclass)** — mavjud, asosiy klass.
* **Child (subclass)** — yangi klass, parent’dan xususiyat va metodlarni meros qilib oladi.

Buning natijasida kod **qayta yozilmaydi**, balki **qayta foydalaniladi**.

### Python’da inheritance sintaksisi:

```python
class ChildClass(ParentClass):
    # yangi klassning tanasi
```

### Misol:

```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

    def speak(self):
        print(f"{self.name} says hi!")

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name, "Dog")   # parent klassni chaqirish
        self.breed = breed

    def speak(self):   # metodni override qilish
        print(f"{self.name} barks!")
```

### Tushuntirish:

* `Animal` — **parent klass**, unda `__init__` va `speak` mavjud.
* `Dog` — **child klass**, u `Animal` dan meros oladi.
* `super().__init__` orqali parent klassning konstruktorini chaqiramiz.
* `speak` metodi child klassda qayta yozildi (**override**).

### Obyektlar yaratish:

```python
animal = Animal("Bob", "Cat")
animal.speak()  
# Natija: Bob says hi!

dog = Dog("Max", "Labrador")
dog.speak()  
# Natija: Max barks!
```

👉 Ko‘rib turganingizdek, `Dog` klassi `Animal` dan meros oldi, lekin o‘ziga xos (`speak`) metodini qo‘shib qo‘ydi. Bu OOP’da **hierarxiya** yaratish va **kodni qayta ishlatish** imkonini beradi.

---

## 4. Polymorphism (Polimorfizm)
----------------
![Rasim](https://miro.medium.com/v2/resize:fit:640/format:webp/1*OGLbk0YoNHjr4NcKJKaxQw.jpeg)

**Polymorphism (polimorfizm)** — bu OOP’dagi muhim xususiyatlardan biri bo‘lib, obyektlarning **turli shakl** yoki **xatti-harakatlarga** ega bo‘lishini anglatadi.

Python’da polimorfizm obyektlarga **bir xil interfeys** (ya’ni metod nomi) orqali murojaat qilish imkonini beradi, ammo **har xil klasslarda u turlicha ishlashi** mumkin.

---

### 1️⃣ Method Overriding (metodni qayta yozish)

Polimorfizmni amalga oshirish yo‘llaridan biri — **method overriding**.

* Parent klassda mavjud bo‘lgan metodni **child klass** o‘z uslubida qayta yozadi.
* Subclass obyektida chaqirilsa — **child klassdagi versiyasi ishlaydi**, parent’dagi emas.

#### Misol:

```python
class Animal:
    def speak(self):
        print("Animal is speaking...")

class Dog(Animal):
    def speak(self):
        print("Dog is barking...")

class Cat(Animal):
    def speak(self):
        print("Cat is meowing...")

# Obyektlar yaratish
animal = Animal()
dog = Dog()
cat = Cat()

# Metodlarni chaqirish
animal.speak()  # Output: Animal is speaking...
dog.speak()     # Output: Dog is barking...
cat.speak()     # Output: Cat is meowing...
```

👉 Bu yerda:

* `Animal` — parent klass.
* `Dog` va `Cat` — child klasslar.
* Ularning `speak()` metodlari **turlicha bajariladi**.

---

### 2️⃣ Duck Typing (o‘rdak tipizatsiyasi)

Python dinamik dasturlash tili bo‘lgani uchun **duck typing** tushunchasi mavjud.

> “Agar biror obyekt o‘rdakdek yurib, o‘rdakdek ‘quack’ qilsa — u o‘rdakdir” 🦆

Ya’ni obyektning asl klassi muhim emas, **agar unda kerakli metod mavjud bo‘lsa, ishlaydi**.

#### Misol:

```python
class Duck:
    def quack(self):
        print("Quack!")

class Person:
    def quack(self):
        print("I'm quacking like a duck...")

def make_quack(obj):
    obj.quack()

# Obyektlar yaratish
duck = Duck()
person = Person()

# Funksiya chaqirish
make_quack(duck)    # Output: Quack!
make_quack(person)  # Output: I'm quacking like a duck...
```

👉 Bu misolda:

* `Duck` va `Person` klasslarida `quack()` metodlari bor.
* `make_quack()` funksiyasi obyekt klassiga qaramaydi, **faqat metod mavjudligiga qaraydi**.
* Shuning uchun ikkala obyekt ham bir xil interfeys bilan ishlatilishi mumkin.

---

✅ Xulosa:
Polimorfizm yordamida dasturda **bir xil metod nomi** turli klasslarda turlicha ishlaydi. Bu esa kodni **moslashuvchan** va **kengaytiriladigan** qiladi.

---


## 5. Abstraction (Abstraksiya)
---------------

![Rasim](https://miro.medium.com/v2/resize:fit:720/format:webp/1*-cJTFd3AosudzVr-QqrZ7A.jpeg)

**Abstraction (abstraksiya)** — bu OOP’dagi asosiy tushunchalardan biri bo‘lib, dasturchiga murakkab tizimlardan **faqat kerakli xususiyat va xatti-harakatlarni ajratib olish**, qolgan ichki detallarni esa yashirish imkonini beradi.

👉 Oddiy qilib aytganda, abstraksiya — bu **narsalarning umumiy modelini yaratish**.

### Hayotiy misol:

Mashina (Car) haqida o‘ylaylik:

* Har qanday mashinada **g‘ildirak**, **dvigatel**, **rul** mavjud.
* Lekin mashinalarning detallari turlicha: kimdadir 2 eshik, kimdadir 4 eshik, kimdadir elektr dvigatel, boshqasida benzinli.

Bizga dasturlashda mashinaning umumiy modeli kerak, lekin har bir detalni alohida ko‘rsatish shart emas. Shu yerda abstraksiya ishga tushadi.

---

### Python’da abstraksiya qanday ishlaydi?

Python’da abstraksiyani yaratish uchun:

* **abstract class (abstrakt klass)**
* **abstract method (abstrakt metod)**

ishlatiladi.

Buning uchun maxsus `abc` (Abstract Base Classes) moduli qo‘llaniladi:

```python
from abc import ABC, abstractmethod

class Vehicle(ABC):  # Abstract klass
    @abstractmethod
    def start(self):
        pass

    @abstractmethod
    def stop(self):
        pass
```

📌 Bu yerda:

* `Vehicle` — abstrakt klass.
* `start()` va `stop()` — abstrakt metodlar, ular **hech qanday tanaga ega emas** (faqat majburiy interfeys sifatida berilgan).
* Har qanday subclass bu metodlarni **majburiy** tarzda yozib chiqishi kerak.

---

### Misol: Car klassi

```python
class Car(Vehicle):
    def start(self):
        print("Starting the car...")

    def stop(self):
        print("Stopping the car...")
```

`Car` klassi `Vehicle` dan meros olib, `start` va `stop` metodlarini o‘ziga mos qilib yozdi.

---

### Yana bir nechta subclass qo‘shamiz

```python
class Bike(Vehicle):
    def start(self):
        print("Kick-starting the bike...")

    def stop(self):
        print("Stopping the bike...")

class Bus(Vehicle):
    def start(self):
        print("Bus engine is starting...")

    def stop(self):
        print("Bus is stopping...")
```

Endi bizda turli xil transport vositalari bor, lekin ularning **umumiy interfeysi bir xil** (`start()` va `stop()`).

---

### Obyektlar bilan ishlash:

```python
vehicles = [Car(), Bike(), Bus()]

for v in vehicles:
    v.start()
    v.stop()
```

👉 Natija:

```
Starting the car...
Stopping the car...
Kick-starting the bike...
Stopping the bike...
Bus engine is starting...
Bus is stopping...
```

---

### Afzalliklari:

1. **Umumiy interfeys**: barcha transport vositalari uchun `start()` va `stop()` metodlari bor. Bu dasturdagi kodni yagona uslubda ishlatishga imkon beradi.
2. **Moslashuvchanlik**: yangi transport qo‘shish uchun faqat `Vehicle` ni meros olib, metodlarni yozish kifoya.
3. **Murakkablikni yashirish**: biz foydalanuvchiga “boshlash” va “to‘xtatish” imkoniyatini ko‘rsatamiz, lekin ichkarida nima bo‘layotganini yashiramiz.

---

### Kengroq misol: To‘lov tizimi

Keling, yana bir **real hayotiy misol** — to‘lov tizimini ko‘raylik:

```python
from abc import ABC, abstractmethod

class Payment(ABC):
    @abstractmethod
    def pay(self, amount):
        pass

class CreditCardPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount}$ with Credit Card.")

class PayPalPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount}$ using PayPal.")

class BitcoinPayment(Payment):
    def pay(self, amount):
        print(f"Paid {amount}$ using Bitcoin.")
```

Foydalanish:

```python
payments = [
    CreditCardPayment(),
    PayPalPayment(),
    BitcoinPayment()
]

for p in payments:
    p.pay(100)
```

👉 Natija:

```
Paid 100$ with Credit Card.
Paid 100$ using PayPal.
Paid 100$ using Bitcoin.
```

---

### Xulosa:

**Abstraksiya** yordamida:

* Murakkab tizimlarni **soddalashtirilgan model** orqali ifodalaymiz.
* **Umumiy xatti-harakatlarni** ajratib olamiz (masalan, `start`, `stop`, `pay`).
* **Kodning moslashuvchanligi va kengaytirilishini** ta’minlaymiz.

---


Zo‘r, tarjimani kitob uslubida sof va tushunarli o‘zbek tilida qildim:

---

## 6. Eng yaxshi amaliyotlar

![Rasm](https://miro.medium.com/v2/resize\:fit:720/format\:webp/1*D-VHyiMoXsHGpYw-PkorNw.jpeg)

Obyektga yo‘naltirilgan dasturlash sizning kodingizni tartibga solish va tuzishda qudratli hamda moslashuvchan usulni taqdim etadi. Kodingiz **qo‘llab-quvvatlanadigan**, **masshtablanadigan** va **oson tushunarli** bo‘lishi uchun, dastur yaratishda eng yaxshi amaliyotlarga amal qilish juda muhim. Quyida Python’da obyektga yo‘naltirilgan dasturlash bilan ishlaganda yodda tutishingiz kerak bo‘lgan asosiy tamoyillar keltirilgan.

### 1. **Sinfni aniq vazifaga qaratish.**

Har bir sinf bitta aniq mas’uliyatga ega bo‘lishi kerak va faqat bitta vazifani bajarishi lozim. Bu qoida *Yagona mas’uliyat prinsipi (SRP)* deb ataladi. Bu kodingizni tartibli va qo‘llab-quvvatlash oson bo‘lishini ta’minlaydi. Shuningdek, kodni qayta ishlatish va sinashni yengillashtiradi.

Masalan, agar sizda ma’lumotlar bazasiga ulanishni boshqaruvchi sinf bo‘lsa, unga fayllar bilan ishlash metodlarini qo‘shmasligingiz kerak. Fayl I/O amallari uchun alohida sinf yaratish yaxshiroq bo‘ladi. Bu orqali kod yanada tartibli bo‘ladi va har bir sinfning aniq vazifasi belgilanadi.

**Misol:** ma’lumotlar bazasi bilan ishlash sinfi:

```python
class DatabaseConnection:
    def __init__(self, host, port, username, password):
        self.host = host
        self.port = port
        self.username = username
        self.password = password
        self.connection = None
    
    def connect(self):
        # Berilgan ma’lumotlar orqali bazaga ulanish
        pass
    
    def disconnect(self):
        # Bazadan uzilish
        pass
    
    def execute_query(self, query):
        # SQL so‘rovini bajarish va natijani qaytarish
        pass
```

---

### 2. **Ma’noli nomlardan foydalanish.**

Sinf, metod va o‘zgaruvchi nomlari aniq va tushunarli bo‘lishi kerak. Bu kodni o‘qishni va tushunishni yengillashtiradi, shuningdek, keyinchalik boshqa dasturchilar uchun ham qulay bo‘ladi.

Masalan, foydalanuvchini ifodalovchi sinfni `User` deb nomlash kerak, `Object` kabi umumiy nom emas. Xuddi shuningdek, o‘zgaruvchi va metodlarga ham mazmunli nom berilishi kerak. Masalan, foydalanuvchining yoshini saqlovchi o‘zgaruvchiga `user_age` deb nom berish `x` yoki `y` dan ancha tushunarli.

**Misol:** mazmunli nomlarga ega sinf:

```python
class User:
    def __init__(self, name, age, email):
        self.name = name
        self.age = age
        self.email = email
    
    def send_email(self, message):
        # Berilgan xabarni foydalanuvchiga yuborish
        pass
```

---

### 3. **Merosxo‘rlikdan ortiqcha foydalanmaslik.**

Merosxo‘rlik (inheritance) OOP’da kuchli vosita hisoblanadi, biroq undan ehtiyotkorlik bilan foydalanish lozim. Eng ko‘p uchraydigan xato — chuqur merosxo‘rlik iyerarxiyasini yaratishdir. Bunday iyerarxiya vaqt o‘tishi bilan murakkablashib, boshqarish qiyinlashadi.

Buning oqibatida sinflar o‘rtasida kuchli bog‘lanish, ortiqcha murakkablik va moslashuvchanlikning pasayishi kuzatiladi. Shuning uchun imkon qadar sathliroq (tekis) iyerarxiya yaratish, yoki kerak bo‘lganda *kompozitsiya*dan foydalanish maqsadga muvofiqdir.

**Misol:** merosxo‘rlikdan ortiqcha foydalanish:

```python
class Animal:
    def __init__(self, name, species):
        self.name = name
        self.species = species

class Mammal(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)

class Reptile(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)

class Fish(Animal):
    def __init__(self, name, species):
        super().__init__(name, species)

class Dog(Mammal):
    def __init__(self, name):
        super().__init__(name, "Canine")

class Cat(Mammal):
    def __init__(self, name):
        super().__init__(name, "Feline")

class Snake(Reptile):
    def __init__(self, name):
        super().__init__(name, "Serpent")

class Goldfish(Fish):
    def __init__(self, name):
        super().__init__(name, "Goldfish")
```

Bu yerda bir necha darajali chuqur iyerarxiya hosil qilingan, lekin har bir sinf ota sinfga deyarli yangi funksionallik qo‘shmayapti. Natijada kod tushunish va qo‘llab-quvvatlash qiyin bo‘lib qoladi. Bunday hollarda *kompozitsiya* yoki *interfeyslar*dan foydalanish yaxshiroq natija beradi.

---

## Xulosa

Python’da obyektga yo‘naltirilgan dasturlash prinsiplari — **inkapsulyatsiya**, **merosxo‘rlik**, **polimorfizm** va **abstraksiya** — samarali, masshtablanadigan va qo‘llab-quvvatlash oson dasturlar yaratishda muhim vositalardir. Ular yordamida kodni tartibga solish, takroriy kod yozishni kamaytirish va qayta foydalanish imkoniyatini oshirish mumkin.

Ammo bu prinsiplardan **ortiqcha foydalanish mumkin emas**. Eng muhim narsa — balansni saqlash, ya’ni OOP prinsiplari bilan kodni haddan tashqari murakkablashtirmaslik. Shuningdek, **toza va o‘qilishi oson kod yozish**, zarur joylarda **izoh (comment) qo‘yish**, va kodni muntazam **sinovdan o‘tkazish** samarali dasturlashning ajralmas qismidir.

Shu amaliyotlarga amal qilsangiz, yanada sifatli va masshtablanadigan, vaqt o‘tishi bilan qo‘llab-quvvatlash oson dasturlar yaratishingiz mumkin. Python’ning boy kutubxonalari va vositalari bu prinsiplardan foydalanishni yanada qulay va intuitiv qiladi. Python va OOP prinsiplari uyg‘unligi orqali siz **elegant**, **samarali** va **barqaror** kod yozishingiz mumkin.


