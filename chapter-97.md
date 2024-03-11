---
title: Жаттығулар жауабы. 2
isFree: True
---

## 7.16 Жаттығулар жауабы

1. Төрт компас нүктесін «N», «E», «S» және «W» ретінде бір әріпті жолдармен қысқартуға болады. Осы төрт компас нүктесінің біреуін параметр ретінде қабылдайтын және келесі компас нүктесін сағат тілінің бағытымен қайтаратын turn_clockwiseу функциясын жазыңыз. Мұнда өту керек кейбір сынақтар:

![compass](https://user-images.githubusercontent.com/84173441/182080962-0cd3566c-656c-45e4-98f3-3e49ebb903ca.JPG)

```python
def turn_clockwiseу (side):
    if side == "N":
        return "E"
    elif side == "E":
        return "S"
    elif side == "S":
        return "W"
    elif side == "W":
        return "N"
    else:
        return None

print(turn_clockwiseу("E"))
```

2. 0-ден 6-ға дейінгі бүтін санды күннің атына түрлендіретін day_name функциясын жазыңыз . 0-күнді «жексенбі» деп есептейік. Функцияның аргументтері жарамсыз болса, тағы бір рет Ешбір қайтарыңыз. Мұнда өту керек кейбір сынақтар:

```python
def day_name(n):
    if n == 0:
        return "Jeksenbi"
    elif n == 1:
        return "Duisenbi"
    elif n == 2:
        return "Seisenbi"
    elif n == 3:
        return "Sarsenbi"
    elif n == 4:
        return "Beisenbi"
    elif n == 5:
        return "Juma"
    elif n == 6:
        return "Senbi"


print(day_name(4))
```

3. Күн атауы берілген және оның нөмірін қайтаратын ```day_num``` кері функциясын жазыңыз:

```python
def day_num(dayName):
    if dayName == "Jeksenbi":
        return 0
    elif dayName == "Duisenbi":
        return 1
    elif dayName == "Seisenbi":
        return 2
    elif dayName == "Sarsenbi":
        return 3
    elif dayName == "Beisenbi":
        return 4
    elif dayName == "Juma":
        return 5
    elif dayName == "Senbi":
        return 6
    else:
        return None


print(day_num("Juma"))
```

4. «Бүгін сәрсенбі. Мен демалысқа 19 күннен кейін шығамын. Бұл аптаның қай күні болады?» деген сияқты сұрақтарға жауап беруге көмектесетін функцияны жазыңыз. Сондықтан функция күн атауын және ```delta``` аргументін — қосылатын күндер санын — алуы керек және нәтиже ретінде апта күнінің атауын қайтаруы керек:

```python
def day_name(n):
    if n == 0:
        return "Jeksenbi"
    elif n == 1:
        return "Duisenbi"
    elif n == 2:
        return "Seisenbi"
    elif n == 3:
        return "Sarsenbi"
    elif n == 4:
        return "Beisenbi"
    elif n == 5:
        return "Juma"
    elif n == 6:
        return "Senbi"

def day_num(dayName):
    if dayName == "Jeksenbi":
        return 0
    elif dayName == "Duisenbi":
        return 1
    elif dayName == "Seisenbi":
        return 2
    elif dayName == "Sarsenbi":
        return 3
    elif dayName == "Beisenbi":
        return 4
    elif dayName == "Juma":
        return 5
    elif dayName == "Senbi":
        return 6
    else:
        return None

def day_add(dayName, delta):
    theDayNum = day_num(dayName)
    theDay = abs((7 + theDayNum + delta) % 7)
    return day_name(theDay)

print(day_add("Juma", 19))
```

7. Сағаттарды, минуттарды және секундтарды жалпы секунд санына түрлендіретін ```to_secs``` функциясын жазыңыз. Мұнда өту керек кейбір сынақтар:

```python
def to_secs(sagat, minut, sekund):
    sagatSec = sagat * 60 * 60
    minutSec = minut * 60
    sekundSec = sagatSec + minutSec + sekund
    return sekundSec


#test(to_secs(2, 30, 10) == 9010)
#test(to_secs(2, 0, 0) == 7200)
#test(to_secs(0, 2, 0) == 120)
#test(to_secs(0, 0, 42) == 42)
#test(to_secs(0, -10, 10) == -590)

print(to_secs(2, 30, 10))
print(to_secs(2, 0, 0))
print(to_secs(0, 2, 0))
print(to_secs(0, 0, 42))
print(to_secs(0, -10, 10))
```

8. ```to_secs``` функциясын кіріс ретінде нақты мәндерді алатындай етіп жетілдіріңіз. Ол әрқашан секундтардың бүтін санын қайтаруы керек (нөлге дейін қысқартылған):

```python
test(to_secs(2.5, 0, 10.71) == 9010)
test(to_secs(2.433,0,0) == 8758)
```

9. ```to_secs```-қа "кері" болатын мына үш функцияны жазыңыз :

- ```hours_in``` жалпы секунд санымен көрсетілген сағаттардың бүкіл бүтін санын қайтарады.
- ```minutes_in``` сағаттар алынып тасталғаннан кейін жалпы секундтардағы қалған минуттардың бүтін бүтін санын қайтарады.
- ```seconds_in``` жалпы секунд санымен ұсынылған секундтардың қалғанын қайтарады.



10. Осы сынақтардың қайсысы сәтсіз? Себебін түсіндіріңіз.

Python интерпретаторда енгізіп көріңіз. Қандай қате шыққанын не дұрыс өткенін бақылап көріңіз. Себептерін түсініңіз.

11. a > b болса 1 , а == b болса 0 және а < b болса -1 мәнін беретін салыстыру ```compare``` функциясын жазыңыз.

```python
def compare (a, b):
    if a > b:
        return 1
    elif a == b:
        return 0
    elif a < b:
        return -1


print(compare(5, 4) == 1)
print(compare(7, 7) == 0)
print(compare(2, 3) == -1)
print(compare(42, 1) == 1)

>>> True
>>> True
>>> True
>>> True
```

12. Тік бұрышты үшбұрыштың екі катетінің ұзындықтары берілген гипотенузаның ұзындығын параметр ретінде қайтаратын гипотенуза ```hypotenuse``` деп аталатын функцияны жазыңыз:

```python
def hypotenuse(a, b):
    c = ((a * a) + (b * b)) ** 0.5
    return c

#hypotenuse(3, 4) == 5.0
#hypotenuse(12, 5) == 13.0
#hypotenuse(24, 7) == 25.0
#hypotenuse(9, 12) == 15.0

print(hypotenuse(3, 4))
print(hypotenuse(12, 5))
print(hypotenuse(24, 7))
```

13. (x1, y1) және (x2, y2) нүктелері арқылы өтетін [түзудің көлбеуін](https://www.khanacademy.org/math/cc-eighth-grade-math/cc-8th-linear-equations-functions/8th-slope/a/slope-formula) қайтаратын ```slope(x1, y1, x2, y2)``` функциясын жазыңыз. ```slope``` функциясын мына мәндермен шақыру келесі сынақтардан өте алатынына көз жеткізіңіз:

```python
def slope(x1, y1, x2, y2):
    result = (y2 - y1) / (x2 - x1)
    return result


#slope(5, 3, 4, 2) == 1.0
#slope(1, 2, 3, 2) == 0.0
#slope(1, 2, 3, 3) == 0.5
#slope(2, 4, 1, 2) == 2.0

print(slope(5, 3, 4, 2))
print(slope(1, 2, 3, 2))
print(slope(1, 2, 3, 3))
print(slope(2, 4, 1, 2))

>>> 1.0
>>> 0.0
>>> 0.5
>>> 2.0
```
Содан кейін (x1, y1) және (x2, y2) нүктелері арқылы түзудің y-[кесіндісін](https://www.khanacademy.org/math/algebra/x2f8bb11595b61c86:forms-of-linear-equations/x2f8bb11595b61c86:intro-to-slope-intercept-form/a/introduction-to-slope-intercept-form) қайтаратын ```intercept(x1, y1, x2, y2)``` деп аталатын жаңа функцияда ```slope``` функциясын қолданып жазыңыз.

[Көлбеу-кесу формасы](https://www.khanacademy.org/math/algebra/x2f8bb11595b61c86:forms-of-linear-equations/x2f8bb11595b61c86:intro-to-slope-intercept-form/a/introduction-to-slope-intercept-form) дегеніміз не?

```python
y = mx + b
```

```python
def slope(x1, y1, x2, y2):
    result = (y2 - y1) / (x2 - x1)
    return result


def intercept(x1, y1, x2, y2):
    m = slope(x1, y1, x2, y2)
    x = x1
    y = y1
    b = y -(m * x)
    return b

#intercept(1, 6, 3, 12) == 3.0
#intercept(6, 1, 1, 6) == 7.0
#intercept(4, 6, 12, 8) == 5.0

print(intercept(1, 6, 3, 12))
print(intercept(6, 1, 1, 6))
print(intercept(4, 6, 12, 8))

>>> 3.0
>>> 7.0
>>> 5.0
```

Бұл жаттығудың жауабын табу үшін [WikiHow](https://www-wikihow-com.translate.goog/Find-the-Y-Intercept?_x_tr_sl=en&_x_tr_tl=kk&_x_tr_hl=en&_x_tr_pto=wapp) сайтындағы мақаланы оқып түсініп алсаңыз көп көмегі болады. [En](https://www.wikihow.com/Find-the-Y-Intercept) WikiHow
2-ші тәсіл біздің жағдайға арналған.

14. Аргумент ретінде бүтін санды қабылдайтын және аргумент жұп сан болса, True және тақ болса, False мәнін қайтаратын is_even(n) деп аталатын функцияны жазыңыз.

Сынақ жиынтығына өз сынақтарыңызды қосыңыз.

```python
def is_even(n):
    num = int(n)
    if num % 2 == 0:
        return True
    else:
        return False


print(is_even(9))
print(is_even(12))
print(is_even(-12))

>>> False
>>> True
>>> True
```

15. Енді ```n``` тақ болғанда ```True``` мәнін, ал кері жағдайда ```False``` мәнін қайтаратын ```is_odd(n)``` функциясын жазыңыз. Бұл функция үшін бірлік сынақтарын да қосыңыз.

Соңында, оның аргументі тақ бүтін сан екенін анықтау үшін ```is_even``` шақыруын пайдаланатындай етіп өзгертіңіз және оның сынағы әлі де өткеніне көз жеткізіңіз.

```python
def is_odd(n):
    num = int(n)
    if num % 2 == 0:
        return False
    else:
        return True


print(is_odd(9))
print(is_odd(12))
print(is_odd(-12))
```

16. Мына сынақтардан өтетін ```is_factor(f, n)``` функциясын жазыңыз:

```python
def is_factor(f, n):
    if n % f == 0:
        return True
    else:
        return False
        

>>> is_factor(3, 12)
True
>>> is_factor(5, 12)
False
>>> is_factor(7, 14)
True
>>> is_factor(2, 14)
True
>>> is_factor(7, 15)
False
```

Бірлік сынақтарының маңызды рөлі олар күтілетін нәрсенің бір мәнді «спецификациясы» ретінде әрекет ете алады. Бұл сынақ жағдайлары 1 және 15-ті 15-тің көбейткіштері ретінде қарастырамыз ба деген сұраққа жауап береді .

17. Мына бірлік сынақтарын қанағаттандыру үшін ```is_multiple``` деп жазыңыз:

```python
def is_multiple(x, y):
    if x % y == 0:
        return True
    else:
        return False

print(is_multiple(12, 3))
print(is_multiple(12, 4))
print(not is_multiple(12, 5))
print(is_multiple(12, 6))
print(not is_multiple(12, 7))

>>> True
>>> True
>>> True
>>> True
>>> True
```

```is_multiple``` анықтамасында ```is_factor``` пайдалану жолын таба аласыз ба?

18. Фаренгейттегі берілген температура үшін ең жақын Цельсий градусының бүтін мәнін қайтаруға арналған ```f2c(t)``` функциясын жазыңыз. ( кеңес: кірістірілген ```round``` функциясын пайдаланғыңыз келуі мүмкін. ```round.__doc__``` Python анықтамасын интернеттен не IDE-ден іздеп қарап алыңыз немесе ```round``` функция үшін анықтаманы іздеңіз және оның жұмыс істеу әдісі жайлы таныс болғанша онымен тәжірибе жасаңыз.)

Фарангейт. [Wikipedia](https://en.wikipedia.org/wiki/Fahrenheit)

Python built-in function ```round``` [doc](https://docs.python.org/3/library/functions.html#round).

```python

def f2c(t):
    c = round((t - 32) * (5/9))
    return c

print(f2c(36))

test(f2c(212) == 100)     # Boiling point of water
test(f2c(32) == 0)        # Freezing point of water
test(f2c(-40) == -40)     # Wow, what an interesting case!
test(f2c(36) == 2)
test(f2c(37) == 3)
test(f2c(38) == 3)
test(f2c(39) == 4)
```

19. Енді керісінше орындаңыз: Цельсийді Фаренгейтке түрлендіретін ```c2f``` функциясын жазыңыз:

```python
def c2f(t):
    f = round(t * (9/5) + 32)
    return f

print(c2f(18))

test(c2f(0) == 32)
test(c2f(100) == 212)
test(c2f(-40) == -40)
test(c2f(12) == 54)
test(c2f(18) == 64)
test(c2f(-48) == -54)
```

## 8.20 Жаттығулар

2. Кодты өзгерту. Қатені түзету

```python
prefixes = "JKLMNOPQ"
suffix = "ack"

for letter in prefixes:
    if letter == "O" or letter == "Q":
        print(letter + "u" + suffix)
        continue
    print(letter + suffix)
```

3. Инкапсуляциялау

```python
def count_letter(phrase, word):
    counter = 0
    for letter in phrase:
        if letter == word:
            counter += 1
    return counter

print(count_letter("Something beatuiful. Here is a sample world", "e"))
```

```
>>> 5
```

4. Енді ```count_letter``` функциясын өзгертіп жазыңыз...

```python
Now rewrite the count_letters  function so that instead of traversing the string, it repeatedly calls find (the version from Optional parameters), with the optional third parameter to locate new occurences of the letter being counted.

def find(strng, ch, start=0):
    index = start
    while index < len(strng):
        if strng[index] == ch:
            return index
        index += 1
    return -1

#for example strng = "banana"
#letter = "a"
#x = find(strng, letter, start) will return 1
#we need to modify count_letters so it returns 3
#the start variable can thus be used to our advantage
#the loop will end at the last letter of the string by returning -1

def count_letters(strng, letter, start=0):
    count = 0
    x = find(strng, letter, start)
    while x != -1:
        count += 1
        x = find(strng, letter, x + 1)
    return count
    
    
print(count_letters("Something beatuiful. Here is a sample world", "e"))
```

```python
>>> 5
```

5. Тіркестегі тыныс белгілерінің барлығын алып тастайтын, тіркесті сөздер тізіміне бөлетін және мәтініңізде «e» әрпі бар сөздердің санын есептейтін функцияны жазыңыз.

Қадам-қадаммен қарастырайық. 
Бірінші тыныс белгілерін алып тастайтын код

```python
import string

bbc_news = """In a recent study, the team looked into how many of the photos being submitted 
feature pandemic-related personal protective equipment (PPE). 
They found that it featured in almost a quarter of the photographs submitted.

"It's almost all masks," said Dr Bond. 
"And if you think of the different materials a surgical mask is made from - there's 
the elastic that we see tangled around birds' legs or we might see birds injured by 
trying to ingest the fabric or the hard piece of plastic that secures it over your nose.
"So we use this catch-all term of 'plastic' but it's a whole range of 
different polymers, and masks are a good example of that."

The researchers say they want to highlight the "systemic problem" 
that leads to so much debris ending up in the environment."""

def remove_punc(phrase):
    new_phrase = ""
    for letter in phrase:
        if letter.lower() not in string.punctuation:
            new_phrase = new_phrase + letter
    return new_phrase

print(remove_punc(bbc_news))
```
Тіркесті сөздер тізіміне бөлу:

```python
def list_words(phrase):
    words = phrase.split()
    return list(words)

print(list_words(remove_punc(bbc_news)))
```

Берілген мәтіндегі әріпті санау коды:

```python
def count_letter(phrase, ch):
    count = 0
    for letter in phrase:
        if letter == ch:
            count += 1
    return count

print(count_letter(bbc_news, "e"))
```

6. Мынадай ұқыпты көрінетін көбейту кестесін басып шығарыңыз:

\* Толық аяқталмаған 

```python
for x in range(1, 13):
    for y in range(1, 13):
        print(x * y, end="\t")
    print("\n")
```

7. Тіркес аргументін керісінше жазатын және мына сынақтарды қанағаттандыратын функцияны жазыңыз:

```python
def reverse(phrase):
    counter = 0
    new_phrase = ""
    for i in range(len(phrase)):
        new_phrase = new_phrase + phrase[len(phrase) - (counter+1):len(phrase) - counter]
        counter += 1
    return new_phrase

print(reverse("FC Manchester City"))
```

\* Түсіну үшін 
```python
fruit = "apple"

print(fruit[len(fruit)-1:len(fruit)-0])

print(fruit[len(fruit)-2:len(fruit)-1])

print(fruit[len(fruit)-3:len(fruit)-2])
```

Өзге шешім нұсқасы. Жақсылап оқып, зерттеңіз

```python
def reverse(s):
    x = 1
    while x <= len(s):
        length = len(s)
        lastoutput = s[length - x]
        print(lastoutput, end="")
        x += 1

reverse("FC Manchester City")

#explanation
#we need to use len(s) to make it output letters
#length = len(happy) = 6
#print last = happy[length - 1] will return y
#we need to make it such that [length - 2] and so on
#we need the while loop to stop when length - x = 0
#if len(s) is 6
```

8. Берілген аргументтің "айна кескінін" шығаратын функцияны жазыңыз:

```python
def reverse(phrase):
    counter = 0
    new_phrase = ""
    for i in range(len(phrase)):
        new_phrase = new_phrase + phrase[len(phrase) - (counter+1):len(phrase) - counter]
        counter += 1
    return new_phrase

def mirror(strng):
    new_strng = strng + reverse(strng)
    return new_strng

print(mirror("FC Bayern Munich"))
```

9. Тіркестен берілген әріптің барлық кездесулерін алып тастайтын функцияны жазыңыз:

```python
def remove_letter(x, phrase):
    new_phrase = ""
    for letter in phrase:
        if letter == x:
            continue
        else:
            new_phrase = new_phrase + letter
    return new_phrase


print(remove_letter("i", "Mississippi"))
```

10. Палиндромды танитын функцияны жазыңыз. (Кеңес: мұны жеңілдету үшін өзіңіз жазған reverse функциясын пайдаланыңыз!):

```python

```

11. Substring (ішкі тіркестің) тіркесте қанша рет кездесетінін есептейтін функцияны жазыңыз:

```python

```

12. Тіркестің бірінші кездесетін жағдайын басқа басқа алып тастайтын функцияны жазыңыз:

```python

```

13. Басқа тіркесте осы тіркес кездессе алып тастайтын функцияны жазыңыз:

## 9.5 Tuples. Жаттығулар жауабы 

1. Біз осы тарауда кортеждерді функцияға аргумент ретінде беруге болатын-болмайтыны туралы ештеңе айтқан жоқпыз. Бұл мүмкін екенін тексеру үшін шағын Python мысалын жасаңыз және нәтижелеріңізді жазыңыз.

```python
FCBarcelona = ("FC Barcelona", 1902, "Camp Nou Spotify", "Joan Laporta", "Leo Messi")

#(name, year, stadium, president, bestPlayer) = FCBarcelona

def UCL_Team(club):
    return club[0], club[1], club[2], club[3], club[4]

print(UCL_Team(FCBarcelona))
```

2. Жұп кортежді жалпылау ма, әлде кортеж жұпты жалпылау ма? (Is a pair a generalization of a tuple, or is a tuple a generalization of a pair?)

Жауап: Кортеж жұптың жалпыламасы. Жұп кортеждің мысалы. Бірақ кортеж жұптың кеңейтілген әрі нақты сипатталмаған түрі.

3. Жұп кортеждің бір түрі ме, әлде кортеж жұптың бір түрі ме?

Жауап: Жұп кортеждің бір түрі. Кортеж кеңірек, жұпқа қарағанда жоғарғы деңгейдегі түсінік. Сондықтан жұп кортеждің бір түрі


## 10. Тізімдер. Жаттығу жауаптары

1. Төмендегіге Python интерпретаторының жауабы қандай?

```python
>>> list(range(10, 0, -2))
[10, 8, 6, 4, 2]
```

2. Бұл код фрагментін қарастырыңыз:

```python
import turtle

tess = turtle.Turtle()
alex = tess
alex.color("hotpink")
```

Бұл код фрагменті бір тасбақа инстанциясын жасайды. Оны тексеру үшін былай жаза аламыз:

```python
>>> print(alex is tess)
True
```

Ия, ```alex```-тің түсін өзгерту ```tess```-тің де түсін өзгертеді.
Себебі бұл екі айнымалы бір объектіге сілтеме жасайды. Яғни олар бір-біріне alias - бүркеншік ат.

3. ```b``` ```a```-ның клоны болады. Олар екі түрлі объектіге сілтеме жасап тұр. ```b```-дің 0-ші индексіндегі 1 мәні 5 мәніне ауыстырылады. Оны ```print``` функциясы арқылы тексере аламыз.

4. Келесі бағдарламаның нәтижесі қандай болады?


```python
this = ["I", "am", "not", "a", "crook"]
that = ["I", "am", "not", "a", "crook"]
print("Test 1: {0}".format(this is that))
that = this
print("Test 2: {0}".format(this is that))
```

```python
Test 1: False
Test 2: True
```

```Test 1: False``` болған себебі ```this``` және ```that``` екеуі екі түрлі объектіге сілтеме жасап тұр. Олардың мәндері бірдей, бірақ екі түрлі, бөлек объекті. 
Одан кейін ```that``` айнымалысына ```this``` айнымалысы сілтеме жасап тұрған объекті тағайындалды. Және ```Test 2: True``` мәнін берді, яғни енді ```this``` және ```that``` бір объектіге сілтеме жасап тұр. 

5. Сандардан тұратын, ұзындығы бірдей екі тізімді алатын және әрқайсысының сәйкес элементтерінің қосындыларын қамтитын жаңа тізімді қайтаратын ```add_vectors(vector1,vector2)``` функциясын жазыңыз:

```python
def add_vectors(vector1, vector2):
    new_vector = []
    for ind, val in enumerate(vector1):
        new_vector.append(val)
    for ind2, val2 in enumerate(vector2):
        new_vector[ind2] += val2
    return new_vector


# test(add_vectors([1, 1], [1, 1]) == [2, 2])
# test(add_vectors([1, 2], [1, 4]) == [2, 6])
# test(add_vectors([1, 2, 1], [1, 4, 3]) == [2, 6, 4])

print(add_vectors([1, 1], [1, 1]))
print(add_vectors([1, 2], [1, 4]))
print(add_vectors([1, 2, 1], [1, 4, 3]))
```

6. Санды ```scalar``` және тізімді ```vector``` аргумент ретінде қабылдайтын ```scalar_mult(scalar, vector)``` функциясын жазыңыз, ол [Скалярлық көбейту](https://en-m-wikipedia-org.translate.goog/wiki/Scalar_multiplication?_x_tr_sl=en&_x_tr_tl=kk&_x_tr_hl=en&_x_tr_pto=wapp) вектордың скалярлық еселігін қайтаруы керек. [Wikipedia_en](https://en.wikipedia.org/wiki/Scalar_multiplication)

```python
def scalar_mult(scalar, vector):
    for ind, val in enumerate(vector):
        vector[ind] = val * scalar
    return vector

#test(scalar_mult(5, [1, 2]) == [5, 10])
#test(scalar_mult(3, [1, 0, -1]) == [3, 0, -3])
#test(scalar_mult(7, [3, 0, 5, 11, 2]) == [21, 0, 35, 77, 14])

print(scalar_mult(5, [1, 2]))
print(scalar_mult(3, [1, 0, -1]))
print(scalar_mult(7, [3, 0, 5, 11, 2]))
```

7. Мәндері сан болатын ұзындығы бірдей екі тізімді аргумент ретінде алатын және әрқайсысының сәйкес элементтерінің көбейтінділерінің қосындысын қайтаратын ```dot_product(vec1,vec2)``` функциясын жазыңыз. \* қосымша: ([dot_product](https://en.wikipedia.org/wiki/Dot_product))

```python
def dot_product(vec1, vec2):
    total = 0
    new_list = []
    for ind, val in enumerate(vec1):
        new_list.append(val)
    for ind2, val2 in enumerate(vec2):
        new_list[ind2] = new_list[ind2] * val2
    for ind3, val3 in enumerate(new_list):
        total += val3
    return total

#test(dot_product([1, 1], [1, 1]) ==  2)
#test(dot_product([1, 2], [1, 4]) ==  9)
#test(dot_product([1, 2, 1], [1, 4, 3]) == 12)

print(dot_product([1, 1], [1, 1]))
print(dot_product([1, 2], [1, 4]))
print(dot_product([1, 2, 1], [1, 4, 3]))
```

9. Төмендегі код фрагментіндегі ```song``` пен " ".```join(song.split())``` мен арасындағы байланысты сипаттаңыз. Олар ```song```-қа тағайындалған барлық тіркестер үшін бірдей ме? Олар қашан басқаша болады?

Ойланып, жауабын іздеп көріңіз.

10. ```s``` тіркесіндегі ```old```-тың барлық кездесулерін ```new```-мен ауыстыратын ```replace(s, old, new)``` функциясын жазыңыз:

```python
def replace(s, old, new):
    old_string = s.split(old)
    new_string = new.join(old_string)
    return new_string

#test(replace("Mississippi", "i", "I") == "MIssIssIppI")

#s = "I love spom! Spom is my favorite food. Spom, spom, yum!"
#test(replace(s, "om", "am") ==
    #"I love spam! Spam is my favorite food. Spam, spam, yum!")

#test(replace(s, "o", "a") ==
    #"I lave spam! Spam is my favarite faad. Spam, spam, yum!")

print(replace("Mississippi", "i", "I"))
s = "I love spom! Spom is my favorite food. Spom, spom, yum!"
print(replace(s, "om", "am"))
print(replace(s, "o", "a"))
```

## 11.8 Сөздіктер. Жаттығу жауаптары

1. Тіркесті оқитын және тіркесте кездесетін алфавиттің әріптерінің кестесін әр әріптің неше рет кездесетінімен бірге қайтаратын программа жазыңыз.

```python
def letter_counts (phrase):
    letter_counts = {}
    for letter in phrase:
        letter_counts[letter.lower()] = letter_counts.get(letter, 0) + 1
        letter_items = list(letter_counts.items())
        letter_items.sort()
    return letter_items


print(letter_counts("ThiS is String with Upper and lower case Letters"))
```

2. Үздіксіз интерпретация сеансынан төмендегілердің әрқайсысына Python интерпретаторының жауабын беріңіз:

```
a. 35
b. 4
c. True
e. Key Error: 'pears'
f. ['apples', 'bananas', 'grapes', 'oranges']
g. False
```

Содан кейін төмендегі функцияның негізгі бөлігін толтыру үшін үйренгендеріңізді қолданыңыз:

```python
def add_fruit(inventory, fruit, quantity=0):
    new_inventory = inventory
    new_inventory[fruit] = quantity
    return new_inventory

new_inventory = {}
add_fruit(new_inventory, "strawberries", 10)

# Make these tests work...

#test("strawberries" in new_inventory)
#test(new_inventory["strawberries"] == 10)
#add_fruit(new_inventory, "strawberries", 25)
#test(new_inventory["strawberries"] == 35)

print("strawberries" in new_inventory)
print(new_inventory["strawberries"])
add_fruit(new_inventory, "strawberries", 25)
print(new_inventory["strawberries"])
print(new_inventory)
```

3. Алисаның ғажайыптар еліндегі шытырман оқиғаларының  ...

```python

```

```python

```

```python

```

```python

```

```python

```




