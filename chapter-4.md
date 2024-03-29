---
title: Шарттар
isFree: True
---

## 4 Шарттар / Conditionals

Шарттарды тексеріп, нәтижесіне байланысты бағдарлама әрекетін өзгерте алатын болсақ, бағдарламалар шынымен қызықты болады. Бұл тарау осы туралы.

## 4.1 Логикалық мәндер мен өрнектер / Boolean values and expressions

Питон бағдарламалау тілінде **bool** деп аталатын дерек түрі бар.

Және оның екі ғана мәні болады: ```True``` не ```False``` (шын және жалған). Оларды **Boolean value** деп атайды.

Бұл Ұлыбританиялық математик Джордж Бульдің құрметіне аталған, ол логикалық алгебраны (_Boolean algebra_) алғаш тұжырымдаған - boolean мәндер туралы ой қорытындылау және біріктіру үшін кейбір ережелер. Бұл барлық заманауи компьютерлік логиканың негізі.

```True``` және ```False``` дәл көрсетілгендей бас әріппен жазылуы керек.

```python
>>> type(True)
<class 'bool'>
>>> type(true)
Traceback (most recent call last):
  File "<interactive input>", line 1, in <module>
NameError: name 'true' is not defined
```

Логикалық өрнек / **Boolean expression** - логикалық мән болып табылатын нәтиже шығару үшін бағаланатын өрнек. Мысалы, ```==``` операторы екі мәннің тең екендігін тексереді. Ол логикалық мәнді шығарады (yields):

```python
>>> 5 == (3 + 2)   # 5 мәні 3 + 2 нәтижесіне тең бе?
True
>>> 5 == 6
False
>>> j = "hel"
>>> j + "lo" == "hello"
True
```

Бірінші амалда екі операнд тең мәндерге бағаланады, сондықтан өрнек ```True``` мәнін береді; екінші амалда 5 6-ға тең емес, сондықтан біз ```False``` аламыз.

```bool``` мәнін беретін салыстыру операторларының (**comparision operators**) жалпы саны алтау.
Салыстыру операторлары:

```python
x == y                     # ```True``` мәнін бер ... егер x y-ке тең болса
x != y                     #                      ... егер x y-ке тең болмаса
x > y                      #                      ... егер x y-ктен үлкен болса
x < y                      #                      ... егер x y-ктен кіші болса
x >= y                     #                      ... егер x y-ктен үлкен не тең болса
x <= y                     #                      ... егер x y-ктен кіші не тең болса
```

Мұнда көрсетілген операциялар таныс болса да, Python таңбалары математикалық таңбалардан ерекшеленеді. Көп кездесетін қателік екі теңдік белгісінің (==) орнына бір теңдік белгісін (=) қолдану жағдайлары. = бұл тағайындау таңбасы екенін есте сақтаңыз, ал == салыстыру таңбасы. Және Python тілінде мынандай => не мынандай =< белгілер жоқ. 

Біз көрген басқа типтер (дерек түрлері) сияқты, Boolean мәндер айнымалыларға тағайындала алады, басып шығарылады т.б.

```python
>>> age = 18
>>> old_enough_to_get_driving_licence = age >= 17
>>> print(old_enough_to_get_driving_licence)
True
>>> type(old_enough_to_get_driving_licence)
<class 'bool'>
```

## 4.2 Логикалық операторлар

Қарапайым логикалық өрнектерден күрделі логикалық өрнектерді құруға мүмкіндік беретін үш логикалық оператор бар (**logical operators**) - ```and```, ```or```, ```not``` (және, не, жоқ). Бұл операторлардың семантикасы (мағынасы) ағылшын тіліндегі мағынасына ұқсас. Мысалы, ```x > 0 and x < 10```, егер ```x``` 0-ден үлкен болса _және_ сонымен бірге ```x``` 10-нан кіші болса ғана ```True``` мәнін береді.

```n % 2 == 0  or n % 3 == 0``` ```True``` мәнін береді егер кез-келген біреуі ```True``` болса, яғни, n саны 2-ге немесе 3-ке қалдықсыз бөлінуі керек. (Егер n саны 2-ге де, 3-ке де бөлінетін болса не болады деп ойлайсыз? Өрнек ```True``` не ```False``` бола ма? Python интерпретаторында байқап көріңдер)

```not``` опеарторы Boolean мәнін теріске шығарады. Басқаша айтқанда, ```not True``` -> ```False``` болады, ал ```not False``` -> ```True``` болады.

Бірінші кезекте ```or``` операторының сол жағындағы өрнек бағаланады: егер натиже ```True``` болса, Python оң жақтағы өрнекті бағаламайды (және қажет те емес) — бұл қысқа тұйықты бағалау (_short-circut evaluation_) деп аталады. Сол сияқты ```and``` операторы үшін сол жақтағы өрнек ```False``` мәнін берсе, Python оң жақтағы өрнекті бағаламайды.

Демек қажетсіз есептеулер орын алмайды.

## 4.3 Ақиқат кестелері /  Truth Tables

Ақиқат кестесі - төменде келтірілген кесте. Ол мүмкін мәндерге байланысты Boolean мән қандай болатынын көрсетеді. ```and``` және ```or``` операторларының әрқайсысында екі операнд болғандықтан, ақиқат кестесінде ```and``` семантикасын сипаттайтын тек төрт жол бар .

![aAndB](https://user-images.githubusercontent.com/84173441/178203167-81fced0d-7ab4-4c62-8408-b09d2706a123.JPG)

Ақиқат кестесінде біз кейде T және F әріптерін Boolean мәндерінің қысқартылған белгісі ретеінде қолданамыз: төменде, ```or```-ны сипаттайтын ақиқат кестесі 

![aOrB](https://user-images.githubusercontent.com/84173441/178203241-414091a3-2184-4466-baab-3169e1b5182c.JPG)

Үшінші логикалық оператор ```not```, тек бір операндты қабылдайды, сондықтан оның ақиқат кестесінде тек екі жол бар:

![aB](https://user-images.githubusercontent.com/84173441/178203341-c30c5922-fa06-4568-832a-de89be165cff.JPG)


## 4.4 Логикалық өрнектерді жеңілдету 

Өрнектерді оңайлатуға және қайта реттеуге арналған ережелер жиынтығы ```алгебра``` деп аталады . Біз бәріміз мектептегі алгебра ережелерімен таныспыз, мысалы:

```python
n * 0 == 0
```

Төменде келтірілген өзге алгебра - Boolean алгебрасы - ол Boolean мәндермен жұмыс істеу ережелереін көрсетеді. 

Біріншіден, ```and``` операторы: 

```python
x and False == False
False and x == False
y and x == x and y
x and True == x
True and x == x
x and x == x
```

Ал мұнда ```or``` операторы үшін кейбір сәйкес ережелер берілген:

```python
x or False == x
False or x == x
y or x == x or y
x or True == True
True or x == True
x or x == x
```

Екі ```not``` оператор бірін-бірі жоққа шығарады:
```python
not (not x) == x
```

## 4.5 Шартты орындау

Пайдалы бағдарламаларды жазу үшін бізге шарттарды тексеру және сәйкесінше бағдарламаның әрекетін өзгерту мүмкіндігі әрқашан дерлік қажет. **Шартты амалдар / Conditional statements** бізге бұл қабілетті береді. Ең қарапайым форма ```if``` операторы болып табылады:

```python
x = int(input("Enter any number: "))

if x % 2 == 0:
    print(x, "is even")
    print("Did you know that 2 is the only even number that is prime?")
else:
    print(x, "is odd")
    print("Did you know that multiplying two odd numbers always gives an odd result?")
```

```if``` операторынан кейінгі логикалық өрнек **шарт** деп аталады. Егер бұл шын болса, онда барлық шегінісі бар амалдар орындалады. Oлай болмаса, ```else``` тармағының астындағы шегіністердің барлығы орындалады..

![elseIf](https://user-images.githubusercontent.com/84173441/172294686-7ad62c0e-c5cb-48da-a830-2e2be2befb75.JPG)

```if``` операторының синтаксисі келесідей:

```python
if BOOLEAN EXPRESSION:
    STATEMENTS_1        # егер шарт True болса орындалады
else:
    STATEMENTS_2        # егер шарт False болса орындалады
```

Келесі бөлімдерде қарастырылатын функция анықтамасындағыдай және құрама ```for``` амалы сияқты, ```if``` операторы да бастапқы жолдан және денеден тұрады. Бастапқы жол ```if``` кілт сөзден басталады, логикалық өрнектпен (_Boolean expression_) жалғасады және қос нүктемен (:) аяқталады.

Oдан кейінгі шегініскен амалдар **блок** деп аталады. Бірінші шегініссіз амал блоктың аяқталуын білдіреді.

Логикалық өрнек ```True``` мәніне бағаланса амалдардың бірінші блогындағы әрбір амал ретімен орындалады. Логикалық өрнек ```False``` мәніне бағаланса, амалдардың бүкіл бірінші блогы өткізіліп жіберіледі және оның орнына ```else``` тармағының астындағы шегіністердің барлығы орындалады.

```if``` операторының екі тармағының астында пайда болатын амалдар санында шектеу жоқ, бірақ әрбір блокта кемінде бір амал болуы керек. Кейде амалдары жоқ бөлімнің болуы пайдалы (әдетте біз әлі жазбаған код үшін орын сақтаушы немесе тірек ретінде). Бұл жағдайда біз толтырғыш ретінде әрекет етуден басқа ештеңе жасамайтын ```pass```/өту операторын пайдалана аламыз.

```python
if True:          # әрқашан True,
    pass          #   сондықтан барлық жағдайда орындалады, бірақ pass болғандықтан код ештеңе жасамайды
else:
    pass
```


## 4.6 else тармағын алып тастау

```else``` тармағы жоқ ```if``` операторының блок-схемасы
![noElse](https://user-images.githubusercontent.com/84173441/172297480-52d19600-4d63-495b-94b6-3296c5a63790.JPG)

```if``` опереторының басқа түрі - ```else``` тармағы толығымен алып тасталған. Бұл жағдайда шарт ```True``` мәніне бағаланған кезде операторлар орындалады, әйтпесе орындау ағыны ```if```-тен кейінгі амалда жалғасады.

```python
import math
x = int(input("Enter any number: "))

if x < 0:
    print("Бұл жерде теріс мән ",  x, " қабылданбайды.")
    x = 144
    print("Орнына мен 144 санын қолдандым")

print( x, "санының түбірі мынаған тең: ", math.sqrt(x))
```

Бұл жағдайда квадрат түбірді шығаратын ```print``` функциясы ```if```-тен кейінгі орналасқаны — бұл бос жол қалдырғандықтан емес, код шегінісіне байланысты. Сондай-ақ, егер скриптің жоғарғы жағында орналасқан ```import math``` амалы болмаса, ```math.sqrt(x)``` функциясының шақыруы қате беретін еді. 

## 4.7 Тізбектелген шарт (Chained conditionals)

Кейде екіден көп мүмкіндіктер бар және бізге екіден көп тармақ қажет. Oсындай есептеуді жазудың бір жолы - **тізбектелген шарт**:

```python
if x < y:
    STATEMENTS_A
elif x > y:
    STATEMENTS_B
else:
    STATEMENTS_C
```

![chained](https://user-images.githubusercontent.com/84173441/172300218-0fd0a515-adc0-4458-9ccb-cce17056a1b6.JPG)

```elif``` — else if сөзінің аббревиатурасы. Тағы да бір ғана код тармағы орындалады. ```elif``` амалының санында шектеу жоқ, бірақ ```else``` амалы соңғы және жалғыз болуы керек немесе ```else``` мүлдем болмаса да болады:

```python
if choice == "a":
    function_one()
elif choice == "b":
    function_two()
elif choice == "c":
    function_three()
else:
    print("Invalid choice.")
```

Әрбір шарт ретімен тексеріледі. Біріншісі жалған болса, келесісі тексеріледі және т.б. Егер олардың біреуі ақиқат болса, сәйкес тармақ орындалады және оператор аяқталады. Бірнеше шарт ақиқат болса да, тек бірінші ```True``` болған тармақ орындалады.

## 4.8 Кірістірілген шарттар (Nested conditionals)

Бір шартты басқасының ішіне де кірістіруге болады. (Бұл тағы да сол құрама тақырыбы!) Алдыңғы мысалды былай жазуға болар еді:

![kırıstırılgen_Shart](https://user-images.githubusercontent.com/84173441/172301441-716f0e9d-b3e4-436c-9cb1-c024b0694ee6.JPG)


```python
if x < y:
    STATEMENTS_A
else:
    if x > y:
        STATEMENTS_B
    else:
        STATEMENTS_C
```

Сыртқы шарт екі тармақты қамтиды. Екінші тармақта өзінің екі тармағы бар басқа ```if``` операторы бар. Бұл екі тармақта тағы да ішкі шартты амалдар болуы мүмкін.

Амалдардың шегінісі құрылымды айқын еткенімен, кірістірілген шартты амалдарды оқу өте қиындай түседі. Жалпы, мүмкіндігінше олардан аулақ болған дұрыс.

Логикалық операторлар көбінесе кірістірілген шартты амалдарды жеңілдету жолын ұсынады. Мысалы, біз бір шартты қолданып келесі кодты қайта жаза аламыз:

```python
if 0 < x:            # Мұндағы x int деп есептейік
    if x < 10:
        print("x бір цифрлы оң сан")
```

Басып шығару ```print``` функциясы екі шарттың екеуінен де өтсек ғана шақырылады, сондықтан әрқайсысы қарапайым шарты бар екі ```if``` операторын пайдаланатын жоғарыда көрсетілгеннің орнына ```and``` операторын пайдаланып күрделірек шарт жасай аламыз. Енді бізге тек бір ```if``` операторы қажет:

```python
if 0 < x and x < 10:
    print("x оң бір цифрлы сан")
``` 

## 4.9 return. Қайтару амалы

```return``` амалы, _fruitfull_ не _void_ екеніне байланысты мәнмен не мәнсіз болатын функцияны соңына жетпей ақ (не жеткенде) аяқтап тастауға мүмкіндік беретін амал. _Ерте қайтаруды_ пайдаланудың бір себебі, егер қате жағдайды анықтасақ:

```python
def print_sqrt(x):
    if x <= 0:
        print("Өтініш, тек оң сандар енгізіңіз.")
        return

    result = x**0.5
    print(x, "санының түбірі ", result, "-ке тең")
```

```print_sqrt``` функциясының ```x``` деп аталатын параметрі бар. Oл жасайтын бірінші нәрсе - ```x``` мәні 0-ден кіші немесе тең екенін тексеру, солай болған жағдайда ол қате туралы хабарды көрсетеді, содан кейін функциядан шығу үшін ```return``` функциясын пайдаланады. Oрындау ағыны дереу шақырушыға оралады, ал функцияның қалған жолдары орындалмайды.

## 4.10 Логикалық қарама-қарсы операторлар

Алты реляциялық оператордың әрқайсысының логикалық қарама-қарсылығы бар: мысалы, жасымыз 18-ге толғанда жүргізуші куәлігін ала аламыз делік, ал 18-ге толмаған кезде жүргізуші куәлігін ала алмаймыз .

\>= қарама-қарсысы < екеніне назар аударыңыз

| оператор  | логикалық қарама-қарсы |
| ------------- | ------------- |
| ==  | !=  |
| !=  |	==  |
| <   |	>=  |
| <=  |	>   |
| >	  | <=  |
|  >= |	<   |

Oсы логикалық қарама-қарсыларды түсіну кейде ```not``` операторынан арылуға мүмкіндік береді. ```not``` операторларды компьютерлік кодта оқу әдетте өте қиын, және егер біз оларды жоя алсақ, біздің мақсат әдетте анық болады.

Мысалы, егер біз бұл Python кодын жазсақ:

```python
if not (age >= 18):
    print("Хей, сен жүргізуші куәлігін алуға әлі жассың!")
```
оның орнына жеңілдету заңдылығын қолданып, былайша жазсақ ше:

```python
if age < 18:
    print("Хей, сен жүргізуші куәлігін алуға әлі жассың!")
```

Күрделі логикалық өрнектермен жұмыс істегенде жиі пайдалы болатын екі керемет жеңілдету заңдары (де Морган заңдары деп аталады) мыналар:

```python
not (x and y)  ==  (not x) or (not y)
not (x or y)   ==  (not x) and (not y)
```

Мысалы, сиқырлы шам семсеріміз 90% немесе одан жоғары зарядталған болса және қорғаныс қалқанымызда 100 немесе одан да көп қуат бірліктері болса ғана айдаһарды өлтіре аламыз делік. Біз ойында Python кодының бұл фрагментін былай көретін едік:

```python
if not ((sword_charge >= 0.90) and (shield_energy >= 100)):
    print("Сіздің шабуылыңыз әсер етпейді, айдаһар сізді қытырлақ етіп қуырады!")
else:
    print("Айдаһар үйіндіде мыжылады. Сіз Керемет ханшайымды құтқардыңыз!")
```

Де Морган заңдары логикалық қарама-қарысылармен бірге шартты келесідей түсінуге оңай түрде қайта өңдеуге мүмкіндік береді:

```python
if (sword_charge < 0.90) or (shield_energy < 100):
    print("Сіздің шабуылыңыз әсер етпейді, айдаһар сізді қытырлақ етіп қуырады!")
else:
    print("Айдаһар үйіндіде мыжылады. Сіз Керемет ханшайымды құтқардыңыз!")
```

Шартты мағынаның ```if``` және ```else``` бөліктерін ауыстыру арқылы да біз ```not```-тан құтыла аламыз. Міне, үшінші нұсқа, сонымен қатар баламасы:

```python
if (sword_charge >= 0.90) and (shield_energy >= 100):
    print("Айдаһар үйіндіде мыжылады. Сіз керемет ханшайымды құтқардыңыз!")
else:
    print("Сіздің шабуылыңыз әсер етпейді, айдаһар сізді қытырлақ етіп қуырады!")
```

Бұл нұсқа үшеуінің ішіндегі ең жақсысы болуы мүмкін, себебі ол ағылшын тіліндегі бастапқы амалға өте сәйкес келеді. Біздің кодтың анықтығы (басқа адамдар үшін) және кодтың күткенді орындайтынын түсінуді жеңілдету әрқашан жоғары басымдық болуы керек.

Бағдарламалау дағдылары дамыған сайын бізде кез келген мәселені шешудің бірнеше жолы бар екенін көреміз. Сондықтан жақсы бағдарламалар _жоспарланады, дизаиндалады_. Біз айқындықты, қарапайымдылықты және талғампаздықты қолдайтын кодты таңдау жасаймыз. Бағдарламалық жасақтамасының сәулетшісі лауазымы не істейтініміз туралы көп айтады — біз өз туындыларымызда сұлулықты, функционалдылықты, қарапайымдылық пен айқындықты теңестіру үшін өнімдерімізді құрастыратын сәулетшілерміз.

> Кеңес:
> Бағдарламамыз жұмыс істегеннен кейін, біз оны жақсартуға тырысуымыз керек. Жақсы түсініктемелер жазыңыз. Әр түрлі айнымалы атаулармен кодтың анық болуы туралы ойланыңыз. Біз мұны бұдан да талғампаз етіп жасай алар ма едік? Функцияны пайдалану керек пе? Шарттылықты жеңілдете аламыз ба?
> 
> Біз кодты өз туындымыз, өнер туындымыз деп санаймыз! Біз оны керемет жасаймыз.

## 4.11 Типті түрлендіру

Біз мұны алдыңғы тарауда бірінші рет қарастырдық. Қайтадан шолу жасап өтейік!

Көптеген Python [мән түрлері](https://www.w3schools.com/python/python_datatypes.asp) басқа түрдегі мәндерді өз түріне түрлендіруге әрекеттенетін кірістірілген функциясымен келеді. Мысалы , ```int``` функциясы кез келген мәнді қабылдайды және оны мүмкін болса бүтін санға түрлендіреді, басқа жағдайда қате шығарады:

```python
>>> int("32")
32
>>> int("Hello")
ValueError: invalid literal for int() with base 10: 'Hello'
```

```int``` сонымен қатар жылжымалы нүкте мәндерін (floating-point values) бүтін сандарға түрлендіре алады, бірақ оның бөлшек бөлігін қысқартатынын есте сақтаңыз:

```python
>>> int(-2.3)
-2
>>> int(3.99999)
3
>>> int("42")
42
>>> int(1.0)
1
```

```float``` функциясы бүтін сандар мен тіркестерді өзгермелі нүктелі сандарға түрлендіреді:

```python
>>> float(32)
32.0
>>> float("3.14159")
3.14159
>>> float(1)
1.0
```

Python, 1 бүтін мәнін өзгермелі нүкте мәні 1.0-ден ажырататыны біртүрлі көрінуі мүмкін. Олар бірдей санды білдіруі мүмкін, бірақ олар әртүрлі типке (type) жатады. Себебі, олар компьютер ішінде әртүрлі түрде көрсетіледі.

```str``` функциясы оған берілген кез келген аргументті ```string``` түріне түрлендіреді:

```python
>>> str(32)
'32'
>>> str(3.14149)
'3.14149'
>>> str(True)
'True'
>>> str(true)
Traceback (most recent call last):
  File "<interactive input>", line 1, in <module>
NameError: name 'true' is not defined
```

```str``` кез келген мәнмен жұмыс істейді және оны тіркеске түрлендіреді. Бұрын айтылғандай, ```True``` – Boolean мән; ```true``` жай айнымалының аты және бұл жерде анықталмаған, сондықтан біз қате аламыз.

## 4.12 Тасбақа бағаналы диаграммасы

Тасбақа біз осы уақытқа дейін көргеннен әлдеқайда көп күшке ие. Толық құжаттаманы http://docs.python.org/py3k/library/turtle.html сайтынан немесе PyScripter ішінен табуға болады, _Help_ пайдаланыңыз және тасбақа модулін іздеңіз.

Міне, біздің тасбақалар үшін бірнеше жаңа трюктер:

- Тасбақа өзі турған жерде мәтінді басып шығара алады. Мұны істеу әдісі - ```alex.write(«Сәлеметсіз бе»)```.
- Біз пішінді (шеңбер, жарты шеңбер, үшбұрыш, т.б.) түспен толтыра аламыз. Бұл екі сатылы процесс. Алдымен ```alex.begin_fill()``` әдісін шақырамыз, содан кейін пішінді саламыз, содан кейін ```alex.end_fill()``` әдісін шақырамыз.
- Біз тасбақаның түсін алдында орнатқан болатынбыз — енді оның толтыру түсін де орнатуға болады, ол тасбақа мен қаламның түсімен бірдей болмаса да болады. Тасбақа көк түспен сызу үшін, ал қызылмен толтыру үшін ```alex.color («blue», «red»)``` пайдаланамыз.

Олай болса, ```tess``` тасбақамызға бағана диаграмасын салдыра аламыз ба? Диаграммаланатын кейбір деректерден бастайық,

```xs = [48, 117, 200, 240, 160, 260, 220]```

Төмендегі кодты жақсылап зерттеп қарасаңыз, біз салатын төртбұрышты бағандардың қалай сызылғанын түсінесіз. Олай болса кірісіңіз.

```python
import turtle

wn = turtle.Screen()        # Терезені және оның атрибуттарын жазу
wn.bgcolor("lightgreen")
xs = [48, 117, 200, 240, 160, 260, 220]

tess = turtle.Turtle()      # tess-ті жасау және оған атрибуттар беру
tess.pensize(3)

size = 20                   # Ең кішкентай шаршының үлкендігі

def draw_bar(t, height):
    """Мына биіктіктегі тіктөртбұрышты салу үшін t тасбақасын ал"""
    t.left(90)
    t.forward(height)     # Сол жағын сызу
    t.right(90)
    t.forward(40)         # Жолақ ені, үстіңгі жағы 
    t.right(90)
    t.forward(height)     # Және қайтадан төмен! 
    t.left(90)            # Тасбақаны алғашқы бастағандағы бағытына қаратып қою
    t.forward(10)         # Әрбір жолақтан кейін кішкене бос орын қалдырыңыз

for v in xs:              #  xs және tess дайын деп есептейік!
    draw_bar(tess, v)
    
wn.mainloop()
```

![graph](https://user-images.githubusercontent.com/84173441/172327221-df0c2996-89fa-4ec6-9614-c9bb4aa1a588.JPG)

Жарайды, фантастикалық әсерлі емес, бірақ бұл жақсы бастама! Бұл жерде маңызды нәрсе программаны ойша бөлу немесе мәселені кішірек бөліктерге бөлу болды. Біздің программалық бөлік бір жолақты сызу болып табылады және біз мұны істеу үшін функция жаздық. Содан кейін бүкіл диаграмма үшін біз функциямызды қайта-қайта шақырдық.

Әрі қарай, әрбір жолақтың жоғарғы жағында деректердің мәнін басып шығарамыз. Біз мұны ```draw_bar``` денесіне негізгі жаңа үшінші жол ретінде ```t.write('   ' + str(height))``` қосу арқылы орындаймыз. Санның алдына кішкене бос орын қойып, санды жолға (тіркеске) айналдырдық. Бұл қосымша берілген бос орынсыз біз мәтінді сол жақтағы жолаққа ыңғайсыз қысып аламыз. Нәтиже қазір әлдеқайда жақсы көрінеді:

![withNumbers](https://user-images.githubusercontent.com/84173441/172328838-3cdf5db7-2ad8-4f56-a2dd-fccf7c90fba2.JPG)

Ал енді әр бағананы толтыру үшін екі жолды қосамыз. Біздің соңғы бағдарламамыз келесідей көрінеді:

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
    t.forward(10)

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

Ол келесілерді шығарады, бұл қанағаттанарлық:

![withColor](https://user-images.githubusercontent.com/84173441/172329597-99d37b7b-ab36-4ac3-b177-d6842d694174.JPG)

Хммм мүмкін, бағаналарды төменгі жағында бір-бірімен біріктіруге болмайды. Жолақтардың арасын жасау кезінде қаламды алуымыз керек. Мұны сізге жаттығу ретінде қалдырамыз!

## 4.13. Глоссарий 

**блок / block** 
Бірдей шегіністе жазылған тізбектелген амалдар тобы

**дене / body** 
Бас жолдан кейінгі _құрама амалдағы_ амалдар блогы.

**Буль алгебра / Boolean algebra** 
Логикалық өрнектерді қайта реттеу және пайымдаудың кейбір ережелері.

**Boolean амалы / Boolean expression**
Шын немесе жалған өрнек. (True or False expression)

**Boolean мән / Boolean value**
Дәл екі Boolean мән бар: True және False. Логикалық мәндер логикалық өрнек Python интерпретаторы арқылы бағаланғанда пайда болады. Oлар ```bool``` дерек түрі болып табылады.

**тармақ / branch**
Шартты есептеу арқылы анықталатын орындау ағынының мүмкін жолдарының бірі.

**тізбектелген шартты / chained conditional**
Орындау ағынының екіден көп ықтимал ағыны бар шартты тармақ. Python тілінде тізбектелген шарттар ```if ... elif ... else``` операторларымен жазылады.

**салыстыру операторы / comparison operator**
Екі мәнді салыстыратын алты оператордың бірі: == , != , > , < , >= және <= .

**жағдай / condition**
Қай тармақ орындалатынын анықтайтын шартты оператордағы логикалық өрнек.

**шартты амал / conditional statement**
Кейбір шартқа байланысты орындалу ағынын басқаратын амал. Python тілінде ```if , elif``` және ```else``` кілт сөздері шартты амал үшін пайдаланылады.

**логикалық оператор / logical operator**
Логикалық өрнектерді біріктіретін операторлардың бірі: ```and``` , ```or``` , ```not``` .

**nesting**
Бір бағдарлама құрылымы екіншісінің ішінде. Мысалы, шартты оператордың тармағының ішіндегі басқа бір шартты оператор

**шақыру / prompt**
Пайдаланушыға жүйе енгізілген деректерді қабылдауға дайын екенін көрсететін көрнекі сигнал.

**ақиқат кестесі / truth table**
Oператордың семантикасын сипаттай алатын логикалық мәндердің қысқаша кестесі.

**тип түрлендіру / type conversion**
Бір түрдің мәнін алатын және басқа түрдің сәйкес мәнін есептейтін арнайы функция шақыруы.

**функциядағы кодты орау / wrapping code in a function**
Функция тақырыбы мен параметрлерді бағдарлама амалының тізбегіне қосу процесі көбінесе «кодты функцияға орау» деп аталады. Бұл процесс қарастырылып отырған бағдарлама амалдары бірнеше рет пайдаланылатын кезде өте пайдалы. Бұл бағдарламашыға өздерінің ақыл-ой түйіндерін және күрделі мәселені бөліктерге қалай бөлгенін көрсетуге мүмкіндік берсе, одан да пайдалы.


## 4.14 Жаттығулар

1. Аптаның күндері Дүйсенбіден Жексенбіге дейін 0,1,2,3,4,5,6 деп есептелсін. Күн нөмірі берілген кезде ол күн атын (тіркес/сөз) қайтаратын функцияны жазыңыз.

2. Сіз керемет мерекеге барасыз, ол жаққа номер 3-ші (Бейсенбі) күні кетесіз. 137 рет ұйықтағаннан кейін үйге қайтасыз. Бастапқы күннің нөмірін және болу ұзақтығын сұрайтын бағдарламаның жалпы нұсқасын жазыңыз, сонда ол сізге қайтатын апта күнінің атын айтады.

3. Oсы шарттардың логикалық қарама-қарсы операторларын көрсетіңіз

```python
1. a > b
2. a >= b
3. a >= 18  and  day == 3
4. a >= 18  and  day != 3
```

4. Мына өрнектердің мәні не болады?

```python
1. 3 == 3
2. 3 != 3
3. 3 >= 4
4. not (3 < 4)
```

5. Мына ақиқат кестесін толтырыңыз:

![turth_Table](https://user-images.githubusercontent.com/84173441/172352474-a50e8cfa-7a9e-4bf0-84c1-0108ddb6491b.JPG)

6. Төмендегі кестеге сайкес емтихан белгісін сурайтын (санды) және енгізілген мәнге байланысты бағаны тіркеспен (str) қайтаратын бағдарлама жазыңыз.

![grade](https://user-images.githubusercontent.com/84173441/172354094-583d24ad-337e-4669-b497-d26c4a841478.JPG)

Шаршы және дөңгелек жақшалар жабық және ашық аралықтарды білдіреді. Жабық интервал санды қамтиды, ал ашық интервал оны жоққа шығарады. Сонымен 39,99999 F3 бағасын алады, бірақ 40 F2 бағасын алады. Болжам

```python
xs = [83, 75, 74.9, 70, 69.9, 65, 60, 59.9, 55, 50,
                     49.9, 45, 44.9, 40, 39.9, 2, 0]
```

Oсы тізімдегі барлық елементтердің белгісі мен бағасын басып шығару арқылы функсяңызды тексеріңіз.

7. Тасбақа бағаналы диаграмма бағдарламасын қалам әр бағана арасындағы шағын бос орындарға келгенде көтеріліп туратындай етіп өзгертіңіз.

8. Тасбақа бағаналы диаграмма бағдарламасын 200 немесе одан жоғары кез келген мәнге арналған жолақ қызыл түспен, \[100 және 200) арасындағы мәндер сары түспен және 100-ден аз мәндерді білдіретін бағана жасыл түспен толтырылатындай етіп өзгертіңіз.

9. Тасбақа бағаналы диаграмма бағдарламасында тізімдегі деректер мәндерінің біреуі немесе бірнешеуі теріс болса, не болады деп күтесіз? Байқап көріңіз. Бағдарламаны теріс жолақтар үшін мәтін мәнін басып шығарғанда, мәтінді жолақтың төменгі жағына қоятындай етіп өзгертіңіз.

10. Тік бұрышты үшбұрыштың екі қабырғасының ұзындығы берілгенде гипотенузаның ұзындығын беретін ```find_hypot``` функциясын жазыңыз. (Кеңес: ```x ** 0,5``` квадрат түбірді қайтарады.)

11. Үшбұрыштың үш қабырғасының ұзындығын ескере отырып, үшбұрыштың тік бұрышты екенін анықтайтын ```is_rightangled``` функциясын жазыңыз. Функцияның үшінші аргументі әрқашан ең ұзын жағы деп есептейік. Егер үшбұрыш тік бұрышты болса, ол ```True``` мәнін қайтарады , ал болмаса ```False``` мәнін қайтарады .

Нұсқау: Жылжымалы нүкте арифметикасы әрқашан дәл бола бермейді, сондықтан өзгермелі нүкте сандарын теңдік үшін тексеру қауіпсіз емес. Егер жақсы бағдарламашы ```x``` -тің ```y```-ке тең немесе жеткілікті жақын екенін білгісі келсе, оны келесідей кодтауы мүмкін:

```python
if  abs(x-y) < 0.000001:    # If x is approximately equal to y / Егер x шамамен у-ға тең болса
    ...
```

12. Жоғарыдағы бағдарламада, қабырғаларын функцияға кез-келген ретпен беруге болатындай етіп кеңейтіңіз.

13. Егер сізді неліктен өзгермелі нүкте арифметикасының кейде дұрыс емес екендігі қызықтырса, қағазда 10-ды 3-ке бөліп, ондық нәтижені жазыңыз. Сіз оның аяқталмайтынын көресіз, сондықтан сізге шексіз ұзын қағаз парағы қажет болады. Компьютер жадындағы немесе калькулятордағы сандарды көрсетуде ұқсас мәселелер бар: жад шектеулі және кейбір сандарды алып тастау қажет болуы мүмкін . Кішкентай дәлсіздіктер орын алады. Мына сценарийді қолданып көріңіз:

```python
import math

a = math.sqrt(2.0)

print(a, a*a)
print(a*a == 2.0)
```

