---
title: Жаттығу жауаптары
isFree: True
---


## 3.1 Біздің алғашқы тасбақа бағдарламамыз

Oсы бағдарламаны ары қарай жетілдіріңіз...
Жауап:

```python
import turtle

window = turtle.Screen()
bg_color = input("What you want a background color look like?")
window.bgcolor(bg_color)  # Терезе фонының түсін орнатыңыз
window.title("Hello, Tess!")  # Терезе тақырыбын орнатыңыз

tess = turtle.Turtle()
turtle_color = input("What is the color of turtle: ")
tess.color(turtle_color)  # tess-ке түсін өзгертуін айт
tess.pensize(3)  # tess-ке қаламның енін орнатуды айтыңыз

tess.forward(50)
tess.left(120)
tess.forward(50)

window.mainloop()
```

## 3.8 Жаттығулар

5. Жауап:

```python
xc = [12, 10, 32, 3, 66, 17, 42, 99, 20]
total = 0

for nums in xc:
    total = total + nums
print(total) 
```

6. Жауап:

- Тең қабырғалы үшбұрыш (equilateral triangle)

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(3):
    alex.forward(100)
    alex.left(120)

turtle.mainloop()
```

- Шаршы (square)

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(4):
    alex.forward(100)
    alex.left(90)

turtle.mainloop()
```

- Алтыбұрыш (hexagon)

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(6):
    alex.forward(100)
    alex.left(60)

turtle.mainloop()
```

- Сегізбұрыш (octagon)

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(8):
    alex.forward(100)
    alex.left(45)

turtle.mainloop()
```

7. Мас пират жүріп өткен жол:

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

pirat_joly = [160, -43, 270, -97, -43, 200, -940, 17, -86]

for i in pirat_joly:
    alex.forward(100)
    alex.left(i)

turtle.mainloop()
```

8. Пираттың "қарап қалған" бағыты

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

pirat_joly = [160, -43, 270, -97, -43, 200, -940, 17, -86]
all_turn = 0

for i in pirat_joly:
    alex.forward(100)
    alex.left(i)
    all_turn = all_turn + int(i)

turtle.mainloop()
print(360 % all_turn)
```

9. Егер сіз 18 қабырғасы бар дұрыс көпбұрышты салғыңыз келсе, тасбақаны әр бұрышта қандай бұрышқа бұру керек еді?

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(18):
    alex.forward(100)
    alex.left(20)

turtle.mainloop()
```

11. Мынадай фигураны салу программасын жазыңыз:

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("deepskyblue")

alex = turtle.Turtle()
alex.color("white")

for i in range(5):
    alex.forward(100)
    alex.left(-144)


turtle.mainloop()
```

12. Мынадай көрінетін сағаттың бетін салу программасын жазыңыз:

```python
import turtle

window = turtle.Screen()
alex = turtle.Turtle()
alex.shape("turtle")
alex.color("indigo")
window.bgcolor("deepskyblue")

for i in range(12):
    alex.penup()
    alex.forward(80)
    alex.pendown()
    alex.forward(10)
    alex.penup()
    alex.forward(10)
    alex.stamp()
    alex.forward(-100)
    alex.left(30)

window.mainloop()
```

13. Тасбақа жасаңыз және оны айнымалыға тағайындаңыз. Оның түрін сұрағанда, не аласыз?

```python
import turtle

alex = turtle.Turtle()
print(type(alex))
```

```python
>>> <class 'turtle.Turtle'>
```

## 4.14 Жаттығулар 

1. Апта күндері 

```python
n = int(input("Please, enter weeek number: "))

if n == 0:
    print("Duisenbi")
elif n == 1:
    print("Seisenbi")
elif n == 2:
    print("Sarsenbi")
elif n == 3:
    print("Beisenbi")
elif n == 4:
    print("Juma")
elif n == 5:
    print("Senbi")
elif n == 6:
    print("Jeksenbi")
```

2. Сіз керемет мерекеге барасыз ...

```python
qonaqqa_baratyn_kun = int(input("Qonnaqqa qai kuni barasyz: "))
bolu_uzaqtyqy = int(input("Qansa uaqyt bolasyz?: "))
qaityp_keletin_kun = (bolu_uzaqtyqy + qonaqqa_baratyn_kun) % 7

if qaityp_keletin_kun == 0:
    print("Siz qaityp keletin kun: Duisenbi")
elif qaityp_keletin_kun == 1:
    print("Siz qaityp keletin kun: Seisenbi")
elif qaityp_keletin_kun == 2:
    print("Siz qaityp keletin kun: Sarsenbi")
elif qaityp_keletin_kun == 3:
    print("Siz qaityp keletin kun: Beisenbi")
elif qaityp_keletin_kun == 4:
    print("Siz qaityp keletin kun: Juma")
elif qaityp_keletin_kun == 5:
    print("Siz qaityp keletin kun: Senbi")
elif qaityp_keletin_kun == 6:
    print("Siz qaityp keletin kun: Jeksenbi")
```

3. Oсы шарттардың логикалық қарама-қарсы операторларын көрсетіңіз

```python
1. a > b
2. a >= b
3. a >= 18  and  day == 3
4. a >= 18  and  day != 3
```

қарама-қарсы операторлары
```python
1. a < b
2. a < b
3. a < 18  and  day != 3
4. a < 18  and  day == 3
```

4. Мына өрнектердің мәні не болады?

```python
1. 3 == 3  True
2. 3 != 3  False
3. 3 >= 4  False
4. not (3 < 4) False
```

6. Емтихан бағасы:

```python
Emtihan_bagasy = int(input("Emtihan bagasy qandai: "))

eb = Emtihan_bagasy

if eb >= 75:
    print("Birinshi")
elif eb < 75 and eb >= 70:
    print("Jogary ekinshi")
elif eb < 70 and eb >= 60:
    print("Ekinshi")
elif eb < 60 and eb >= 50:
    print("Usinsi")
elif eb < 50 and eb >= 45:
    print("F1 Qosymsa")
elif eb < 45 and eb >= 40:
    print("F2")
elif eb < 40:
    print("F3")
```

тексеру:

```python
xs = [83, 75, 74.9, 70, 69.9, 65, 60, 59.9, 55, 50, 49.9, 45, 44.9, 40, 39.9, 2, 0, 56]

for eb in xs:
    if eb >= 75:
        print("Birinshi")
    elif eb < 75 and eb >= 70:
        print("Jogary ekinshi")
    elif eb < 70 and eb >= 60:
        print("Ekinshi")
    elif eb < 60 and eb >= 50:
        print("Usinsi")
    elif eb < 50 and eb >= 45:
        print("F1 Qosymsa")
    elif eb < 45 and eb >= 40:
        print("F2")
    elif eb < 40:
        print("F3")
```

7. Тасбақа бағаналы диаграмма бағдарламасын қалам әр бағана арасындағы шағын бос орындарға келгенде көтеріліп туратындай етіп өзгертіңіз.

```python
import turtle

wn = turtle.Screen()        # Set up the window and its attributes
wn.bgcolor("lightgreen")
xs = [48, 117, 200, 240, 160, 260, 220]

tess = turtle.Turtle()      # Create tess and set some attributes
tess.pensize(3)

size = 20                   # Size of the smallest square

def draw_bar(t, height):
    """ Бір бағананы салу үшін тасбақа t-ны алыңыз, биіктігі """
    t.begin_fill()           # Осы жолды қосты
    t.left(90)
    t.forward(height)
    t.write("  "+ str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)
    t.end_fill()             # Осы жолды қосты
    t.penup()
    t.forward(10)
    t.pendown()

wn = turtle.Screen()         # Терезені және оның атрибуттарын орнату
wn.bgcolor("lightgreen")

tess = turtle.Turtle()       # tess-ті жасаңыз және кейбір атрибуттарды орнатыңыз
tess.color("blue", "red")
tess.pensize(3)

xs = [48,117,200,240,160,260,220]

for a in xs:
    draw_bar(tess, a)

wn.mainloop()
```

8. Тасбақа бағаналы диаграмма бағдарламасын 200 немесе одан жоғары кез келген мәнге арналған жолақ қызыл түспен, \[100 және 200) арасындағы мәндер сары түспен және 100-ден аз мәндерді білдіретін бағана жасыл түспен толтырылатындай етіп өзгертіңіз.

```python
import turtle

wn = turtle.Screen()        # Set up the window and its attributes
wn.bgcolor("lightgreen")
xs = [48, 117, 200, 240, 160, 260, 220]

tess = turtle.Turtle()      # Create tess and set some attributes
tess.pensize(3)

size = 20                   # Size of the smallest square

def draw_bar(t, height):
    """ Бір бағананы салу үшін тасбақа t-ны алыңыз, биіктігі """
    t.begin_fill()           # Осы жолды қосты
    t.left(90)
    t.forward(height)
    t.write("  "+ str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)
    t.end_fill()             # Осы жолды қосты
    t.penup()
    t.forward(10)
    t.pendown()

wn = turtle.Screen()         # Терезені және оның атрибуттарын орнату
wn.bgcolor("lightgreen")

tess = turtle.Turtle()       # tess-ті жасаңыз және кейбір атрибуттарды орнатыңыз

tess.pensize(3)

xs = [48,117,200,240,160,260,220]

for a in xs:
    if a >= 200:
        tess.color("blue", "red")
    elif a < 200 and a >= 100:
        tess.color("blue", "yellow")
    elif a < 100:
        tess.color("blue", "green")
    draw_bar(tess, a)

wn.mainloop()
```

9. Тасбақа бағаналы диаграмма бағдарламасында тізімдегі деректер мәндерінің біреуі немесе бірнешеуі теріс болса, не болады деп күтесіз? Байқап көріңіз. Бағдарламаны теріс жолақтар үшін мәтін мәнін басып шығарғанда, мәтінді жолақтың төменгі жағына қоятындай етіп өзгертіңіз.

```python
import turtle

wn = turtle.Screen()        # Set up the window and its attributes
wn.bgcolor("lightgreen")
xs = [48, 117, 200, 240, 160, 260, 220]

tess = turtle.Turtle()      # Create tess and set some attributes
tess.pensize(3)

size = 20                   # Size of the smallest square

def draw_bar(t, height):
    """ Бір бағананы салу үшін тасбақа t-ны алыңыз, биіктігі """
    t.begin_fill()           # Осы жолды қосты
    t.left(90)
    t.forward(height)
    t.write("  "+ str(height))
    t.right(90)
    t.forward(40)
    t.right(90)
    t.forward(height)
    t.left(90)
    t.end_fill()             # Осы жолды қосты
    t.penup()
    t.forward(10)
    t.pendown()

wn = turtle.Screen()         # Терезені және оның атрибуттарын орнату
wn.bgcolor("lightgreen")

tess = turtle.Turtle()       # tess-ті жасаңыз және кейбір атрибуттарды орнатыңыз

tess.pensize(3)

xs = [48,-117,200,-240,-160,260,220]

for a in xs:
    if a >= 200:
        tess.color("blue", "red")
    elif a < 200 and a >= 100:
        tess.color("blue", "yellow")
    elif a < 100:
        tess.color("blue", "green")
    draw_bar(tess, a)

wn.mainloop()
```

10. Тік бұрышты үшбұрыштың екі қабырғасының ұзындығы берілгенде [гипотенузаның ұзындығын](https://kk.wikipedia.org/wiki) беретін find\_hypot функциясын жазыңыз. (Кеңес: x ** 0,5 квадрат түбірді қайтарады

```python
a = int(input("Тікбұрышты үшбұрыш а қабырғасы: "))
b = int(input("Тікбұрышты үшбұрыш b қабырғасы: "))

c = (a * a + b * b) ** 0.5

print("Гипотенузаның ұзынды: " + c)
```

11. Үшбұрыштың үш қабырғасының ұзындығын ескере отырып, үшбұрыштың тік бұрышты екенін анықтайтын ```is_rightangled``` функциясын жазыңыз.

```python
def is_rightangled(a, b, c):
    if abs(c - ((a * a + b * b)**0.5)) < 0.001:
        print("Тікбұрышты үшбұрыш")
    else:
        print("Тікбұрышты үшбұрыш емес")

is_rightangled(6, 3, 6.708)
is_rightangled(3, 4, 5)
is_rightangled(8, 5, 9.4)
```

12. Жоғарыдағы бағдарламаны қабырғаларын функцияға кез келген ретпен беруге болатындай етіп кеңейтіңіз.

```python
def is_rightangled(a, b, c):
    if abs(c - ((a * a + b * b)**0.5)) < 0.001 or abs(a - ((c * c + b * b)**0.5)) <  0.001 or abs(b - ((a * a + c * c)**0.5)) < 0.001:
        print("Тікбұрышты үшбұрыш")
    else:
        print("Тікбұрышты үшбұрыш емес")

is_rightangled(6.708, 6, 3)
is_rightangled(5, 4, 3)
is_rightangled(8, 5, 9.4339)
```

13. Егер сізді неліктен өзгермелі нүкте арифметикасының кейде дұрыс емес екендігі қызықтырса, қағазда 10-ды 3-ке бөліп, ондық нәтижені жазыңыз. Сіз оның аяқталмайтынын көресіз, сондықтан сізге шексіз ұзын қағаз парағы қажет болады. Компьютер жадындағы немесе калькулятордағы сандарды көрсетуде ұқсас мәселелер бар: жад шектеулі және кейбір сандарды алып тастау қажет болуы мүмкін . Кішкентай дәлсіздіктер орын алады. Мына сценарийді қолданып көріңіз:

```python
import math

a = math.sqrt(2.0)

print(a, a*a)
print(a*a == 2.0)
```

```python
1.4142135623730951 2.0000000000000004
False
```


## 5.26 Жаттығулар

1. Тізімде қанша тақ сан бар екенін санайтын функцияны жазыңыз.

```python
xs = [34, 9, 15, 115, 37]


def odd_nums (theList):
    counter = 0
    for i in theList:
        if i % 2 != 0:
            counter += 1
    print(counter)

odd_nums(xs)
```

2. Тізімдегі барлық жұп сандарды қорытындылаңыз. 

```python
sandar_tizimi = [34, 9, 15, 115, 37, 2]


def jup_san_qosu (tizim):
    qosyndy = 0
    for i in tizim:
        if i % 2 == 0:
            qosyndy += i
    print(qosyndy)

jup_san_qosu(sandar_tizimi)
```

3. Тізімдегі барлық теріс сандарды қорытындылаңыз.

```python
sandar_tizimi = [34, -9, 15, 115, 37, -2]


def teris_san_qosu (tizim):
    qosyndy = 0
    for i in tizim:
        if i < 0:
            qosyndy += i
    print(qosyndy)

teris_san_qosu(sandar_tizimi)
```

4. Тізімдегі қанша сөздің ұзындығы 5 болатынын санаңыз.

```python
UCL = ["Milan", "Inter", "Juventus", "Atalanta", "Real M", "Barca", "Liverpool", "MC"]


def besArip (tizim):
    sanau = 0
    for i in tizim:
        if len(i) == 5:
            sanau += 1
    print(sanau)

besArip(UCL)
```

5. Тізімдегі бірінші жұп санға дейінгі барлық элементтердің қосындысын шығарыңыз, жұп санның өзін қоспаңыз.

```python
sandar_tizimi = [3, 7, 5, 3, 34, 9, 15, 115, 37, 2]


def till_even (tizim):
    odd_sum = 0
    for i in tizim:
        if i % 2 == 0:
            break
        odd_sum += i
    print(odd_sum)

till_even(sandar_tizimi)
```

6. «Sam» сөзінің бірінші рет кездесетінін қосқанда тізімде қанша сөз саны кездесетінін санаңыз.

```python
UCL = ["Milan", "Inter", "Juventus", "Rome", "Sam", "Real M", "Barca", "Liverpool", "MC"]


def sam_sozi (tizim):
    sanau = 0
    for i in tizim:
        sanau += 1
        if i == "Sam":
            break
    print(sanau)

sam_sozi(UCL)
```

7. Ньютонның sqrt функциясына есептелген сайын better мәнін басып шығаратын print функциясын қосыңыз. Өзгертілген функцияңызды аргумент ретінде 25 арқылы шақырыңыз және нәтижелерді жазыңыз.

```python
arasy = 0.00001

def tubir (san):
    jobalau = 10
    while True:
        odan_jaqsy = (jobalau + san / jobalau) / 2
        print(odan_jaqsy)
        if abs(jobalau - odan_jaqsy) < arasy:
            break
        jobalau = odan_jaqsy
    print(odan_jaqsy)

tubir(25)
```

9. Жалғыз бүтін аргументті қабылдайтын және аргумент жай сан болғанда True мәнін, ал кері жағдайда False мәнін қайтаратын ```is_prime``` функциясын жазыңыз.

```python
num = 9

if num > 1:

    # Iterate from 2 to num 
    for i in range(2, num):

        # If num is divisible by any number between
        # 2 and n , it is not prime
        if (num % i) == 0:
            print(num, "is not a prime number")
            break
    else:
        print(num, "is a prime number")

else:
    print(num, "is not a prime number")
```

```python
def is_prime(n):
    if n > 1:
        for i in range(2, n):
            if n % i == 0:
                print("NOT PRIME NUMBER")
                break
        else:
            print("PRIME NUMBER")


is_prime(5743)
```

10. 3-тараудағы жаттығулардағы мас қарақшы мәселесін қайта қарап шығыңыз.

```python
import turtle

wn = turtle.Screen()        # Set up the window and its attributes
wn.bgcolor("lightgreen")

tizim = [(160, 50), (-43, 120), (270, 90), (-43, 245)]

tess = turtle.Turtle()      # Create tess and set some attributes

def pirat_joly (tizim):
    for burysh, qadam in tizim:
        tess.left(burysh)
        tess.forward(qadam)

pirat_joly(tizim)

wn.mainloop()
```

11. Тасбақа көптеген қызықты фигураларды біз жоғарыда көрсеткендей жұптардың тізімін беру арқылы салуы мүмкін, мұнда жұптың бірінші тармағы - бұрылу бұрышы, ал екінші элемент - алға жылжу қашықтығы. Мұнда көрсетілгендей тасбақа ортасында крест бар үйді сызатындай жұптар тізімін орнатыңыз. Бұл сызықтарды/жиектерді бір реттен артық өтпей және қаламды көтермей-ақ жасау керек.

```python
import turtle

wn = turtle.Screen()        # Set up the window and its attributes
wn.bgcolor("lightgreen")

tizim = [(0, 160), (90, 120), (90, 160), (90, 120), (127, 200), (98, 119), (94, 114), (94, 200)]

tess = turtle.Turtle()      # Create tess and set some attributes

def pirat_joly (tizim):
    for burysh, qadam in tizim:
        tess.left(burysh)
        tess.forward(qadam)

pirat_joly(tizim)

wn.mainloop()
```

\* Тасбақаның бұрылу градусы және жүру қадам ұзақтығы геометрия, математика амалдарымен шешілуі керек. Мұндағы мәндер сызбаға қарай таңдала салған жоба мәндер. Уақытыңыз болса дәл есептеп, тура сызба жасайтын тасбақа мәндерін шығарыңыз.


13. Цифрлар санын санау бағдарламасын есіңізге түсіріңіз. n = 0 жағдайында не басып шығарады?

```python
n = 25666
count = 0

if n == 0:
    count = count + 1
else:
    while n != 0:
        count = count + 1
        n = n // 10

print(count)
```
\* Теріс сан және 0 ушін цифр санын есептейтін код

```python
n = 345345
count = 0

if n == 0:
    count = count + 1
else:
    if n < 0:
        n = -(n)
    while n != 0:
        count = count + 1
        n = n // 10

print(count)
```

14. n-дегі жұп цифрлардың санын санайтын бағдарлама жазыңыз

```python
n = 12345678
even_count = 0
odd_count = 0

while n > 0:
    rem = n % 10
    if (rem % 2 == 0):
        even_count += 1
    else:
        odd_count += 1

    n = int(n / 10)

print(even_count)
```

15. numbers тізіміндегі сандардың квадраттарының қосындысын есептейтін программа жазыңыз. Мысалы мынандай шаыру, numbers = \[2, 3, 4] 4+9+16 деп басып шығару керек, ал оның нәтижесі 29.

```python
sandar = [2, 3, 4]
sum = 0

for i in sandar:
    i = i * i
    print(i, end="+")
    sum += i
print(sum)
```

\* соңына дейін шешілмеген.


## 6.9 Жаттығулар

1. Шаршы салу үшін void (бос, жеміссіз) функцияны жазыңыз. Жоғарыда көрсетілген 1-ші суретті салу үшін оны бағдарламада пайдаланыңыз.

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")

def draw_square(tasbaqa, qadam):
    for i in range(5):
        for i in range(4):
            tasbaqa.forward(qadam)
            tasbaqa.left(90)
        tasbaqa.penup()
        tasbaqa.forward(30)
        tasbaqa.pendown()
    tasbaqa.penup()
    tasbaqa.forward(10)

draw_square(alex, 20)

window.mainloop()
```

2. #2 суретті салу салу үшін програма жазыңыз.

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def multi_square(tasbaqa, qadam):
    for i in range(5):
        qadam += 20
        for y in range(4):
            tasbaqa.forward(qadam)
            tasbaqa.left(90)
        tasbaqa.penup()
        tasbaqa.right(45)
        tasbaqa.forward(10)
        tasbaqa.left(45)
        tasbaqa.forward(-15)
        tasbaqa.pendown()


multi_square(alex, 0)

window.mainloop()
```

3. Тасбақа дұрыс көпбұрышты сызуға мүмкіндік беретін draw_poly(t, n, sz) бос функциясын жазыңыз.

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def draw_poly (tasbaqa, n, qadam):
    for i in range(n):
        tasbaqa.forward(qadam)
        tasbaqa.left(360/n)

draw_poly(alex, 8, 50)

window.mainloop()
```

4. #4-ші суретті салыңыз.

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def draw_rectangle(tasbaqa, qadam, sany):
    for i in range(sany):
        for i in range(4):
            tasbaqa.forward(qadam)
            tasbaqa.left(90)
        tasbaqa.left(15)

draw_rectangle(alex, 50, 24)

window.mainloop()
```

5. #5. Бұл суреттегі екі спираль тек бұрылыс бұрышымен ерекшеленеді. Екеуін де сызыңыз.

* өзгеше сурет коды. Байқап көріңіз

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def draw_spiral(tasbaqa, back, up, top, down, sany):
    for i in range(sany):
        back = back + 5
        up = up + 5
        top = top + 5
        down = down + 5
        for i in range(4):
            tasbaqa.forward(-back)
            tasbaqa.left(90)
            tasbaqa.forward(up)
            tasbaqa.right(90)
            tasbaqa.forward(top)
            tasbaqa.right(90)
            tasbaqa.forward(down)


draw_spiral(alex, 0, 0, 0, 0, 20)
```
\* қателікпен орындалған спираль. Өзіңіз нұрыс нұсқасын тауып көріңіз. 


```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def draw_spiral(tasbaqa, back, up, top, down, sany, size):
    for i in range(sany):
        back = back + size
        up = up + size
        top = top + size
        down = down + size
        size = size + 5
        for i in range(1):
            tasbaqa.forward(-back)
            tasbaqa.left(90)
            tasbaqa.forward(up)
            tasbaqa.right(90)
            tasbaqa.forward(top)
            tasbaqa.right(90)
            tasbaqa.forward(down)
            tasbaqa.left(90)


draw_spiral(alex, 5, 5, 10, 10, 10, 5)

window.mainloop()
```

6. Тасбақа тең бүйірлі үшбұрыш салу үшін алдыңғы сұрақтағы draw_poly функциясын шақыратын draw_equitriangle(t, sz) void функциясын жазыңыз.

```python
import turtle

window = turtle.Screen()
window.bgcolor("light green")

alex = turtle.Turtle()
alex.pensize(2)
alex.color("deeppink")


def draw_poly (tasbaqa, n, qadam):
    for i in range(n):
        tasbaqa.forward(qadam)
        tasbaqa.left(360/n)

def draw_equitriangle(t, sz):
    draw_poly(t, 3, sz)


draw_equitriangle(alex, 100)

window.mainloop()
```

7. n-ге дейінгі барлық бүтін сандардың қосындысын (n-де кіреді) қайтаратын sum_to(n) нәтижелі функциясын жазыңыз. Осылайша, sum_to(10) 1+2+3...+10 болады, ол 55 мәнін қайтарады.

```python
def sum_to(n):
    sum = 0
    for i in range(n+1):
        sum = sum + i
    return sum

print(sum_to(10))
```

8. Радиусы r шеңберінің ауданын қайтаратын area_of_circle(r) функциясын жазыңыз.

```python
def area_of_circle(r):
    return  3.14159 * (r * r)

print(area_of_circle(4))
```

9. sfdas

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("light green")

alex = turtle.Turtle()
alex.color("blue")
alex.pensize(3)

for i in range(5):
    alex.forward(100)
    alex.left(-144)


turtle.mainloop()
```

10. Жоғарыдағы бағдарламаңызды кеңейтіңіз. Бес жұлдызды салыңыз, бірақ әрқайсысының арасында қаламды алыңыз, 350 бірлікке алға жылжыңыз, 144-ке оңға бұрылыңыз, қаламды қойыңыз және келесі жұлдызды салыңыз. Сіз келесідей нәрсені аласыз:

```python
import turtle

window = turtle.Screen()
window = turtle.Turtle()
window = turtle.bgcolor("light green")

alex = turtle.Turtle()
alex.color("blue")
alex.pensize(3)

def draw_star(t, size):
    for i in range(5):
        for i in range(5):
            alex.forward(size)
            alex.left(-144)
        alex.penup()
        alex.forward(300)
        alex.right(144)
        alex.pendown()

draw_star(alex, 100)

turtle.mainloop()
```
