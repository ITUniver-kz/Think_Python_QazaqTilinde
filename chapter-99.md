---
title: extra parts
isFree: true
---

## 5.12. Инкапсуляция және жалпылау 

Инкапсуляция - бұл функциялар үшін қолайлы барлық нәрселердің артықшылығын пайдалануға мүмкіндік беретін функциядағы код бөлігін орау процесі. Сіз алдыңғы тарауда is_divisible қоса алғанда, инкапсуляцияның кейбір мысалдарын көрдіңіз.

Жалпылау дегеніміз 2-нің еселіктерін басып шығару сияқты нақты нәрсені алу және оны жалпылау, мысалы, кез келген бүтін санның еселіктерін басып шығару.

Бұл функция алдыңғы циклды инкапсуляциялайды және оны n еселіктерін басып шығару үшін жалпылайды :

```python
def print_multiples(n):
    for i in range(1, 7):
        print(n * i, end="   ")
    print()
```

Инкапсуляциялау үшін бізге функцияның атын және параметрлер тізімін жариялайтын бірінші жолды қосу ғана қалды. Жалпылау үшін бізге тек 2 мәнін n параметрімен ауыстыру қажет болды .

Бұл функцияны 2 аргументі арқылы шақырсақ, бұрынғыдай нәтиже аламыз. 3 аргументі арқылы нәтиже:


```python
3 6 9 12 15 18
```

4 аргументі арқылы нәтиже:

```python
4 8 12 16 20 24
```

Қазірге дейін көбейту кестесін басып шығару жолын болжауға болады — print_multiples деп әртүрлі аргументтермен қайта-қайта шақыру арқылы. Шын мәнінде, біз басқа циклды пайдалана аламыз:

```python
for i in range(1, 7):
    print_multiples(i)
```

Бұл цикл print_multiples ішіндегі циклге қаншалықты ұқсас екенін байқаңыз . Бар болғаны басып шығару функциясын функция шақыруымен ауыстыру болды.

Бұл бағдарламаның нәтижесі көбейту кестесі болып табылады:

```python
1      2      3      4      5      6
2      4      6      8      10     12
3      6      9      12     15     18
4      8      12     16     20     24
5      10     15     20     25     30
6      12     18     24     30     36
```

## 5.13. Қосымша инкапсуляция 

Инкапсуляцияны қайтадан көрсету үшін соңғы бөлімнен кодты алып, оны функцияға орап көрейік:

```python
def print_mult_table():
    for i in range(1, 7):
        print_multiples(i)
```

Бұл процесс жалпы даму жоспары болып табылады . Біз кодты кез келген функциядан тыс код жолдарын жазу немесе интерпретаторға енгізу арқылы әзірлейміз. Кодты іске қосқан кезде біз оны шығарып, оны функцияға орап аламыз.

Бұл әзірлеу жоспары әсіресе жазуды бастаған кезде бағдарламаны функцияларға бөлуді білмесеңіз пайдалы. Бұл тәсіл сіз жүріп жатқанда дизайн жасауға мүмкіндік береді.

## 5.14. Жергілікті айнымалылар 

Сіз print_multiples және print_mult_table екеуінде де бірдей айнымалыны, i қалай қолдануға болатынын сұрайтын боларсыз . Функциялардың бірі айнымалының мәнін өзгерткенде, бұл қиындықтар туғызбайды ма?

Жауап жоқ, себебі print_multiples ішіндегі i және print_mult_table ішіндегі i бірдей айнымалы емес .

Функция анықтамасының ішінде жасалған айнымалылар жергілікті болып табылады; жергілікті айнымалыға оның үй функциясынан тыс қол жеткізе алмайсыз. Бұл бір функцияда болмаса, бірдей атпен бірнеше айнымалыларға ие бола аласыз дегенді білдіреді.

Python функциядағы барлық мәлімдемелерді зерттейді — егер олардың кез келгені айнымалыға мән тағайындаса, бұл Python айнымалыны жергілікті айнымалыға айналдыру үшін пайдаланатын анықтама.

Бұл бағдарламаның стек диаграммасы i деп аталатын екі айнымалының бірдей айнымалы емес екенін көрсетеді. Олар әртүрлі мәндерге сілтеме жасай алады және біреуін өзгерту екіншісіне әсер етпейді.

Стек 2 диаграммасы


print_mult_table ішіндегі i мәні 1-ден 6-ға дейін барады. Диаграммада ол 3 болады. Цикл арқылы келесі жолы 4 болады. Цикл арқылы өткен сайын print_mult_table аргумент ретінде i ағымдағы мәнімен print_multiples шақырады . . Бұл мән n параметріне тағайындалады .

print_multiples ішінде i мәні 1-ден 6-ға дейін барады. Диаграммада ол 2 болады. Бұл айнымалы мәнді өзгерту print_mult_table ішіндегі i мәніне әсер етпейді .

Бір атаумен әртүрлі жергілікті айнымалылардың болуы әдеттегі және толық заңды. Атап айтқанда, i және j сияқты атаулар циклдік айнымалылар ретінде жиі пайдаланылады. Егер сіз оларды басқа жерде пайдаланғаныңыз үшін бір функцияда пайдаланудан аулақ болсаңыз, бағдарламаны оқуды қиындатуыңыз мүмкін.

http://netserv.ict.ru.ac.za/python3_viz/ сайтындағы визуализатор екі айнымалы i қалай бір-бірінен бөлек айнымалылар екенін және олардың тәуелсіз мәндері бар екенін өте анық көрсетеді.

## 5.15. үзіліс мәлімдемесі  _
break операторы өз циклінің денесінен бірден шығу үшін қолданылады . Орындалатын келесі мәлімдеме денеден кейінгі бірінші болып табылады:

```python
for i in [12, 16, 17, 24, 29]:
    if i % 2 == 1:  # If the number is odd
       break        #  ... immediately exit the loop
    print(i)
print("done")
```

Бұл басып шығарады:

```python
12
16
done
```

Сынақ алдындағы цикл — стандартты цикл әрекеті

for және while циклдері дененің кез келген бөлігін орындамас бұрын бастапқыда сынақтарын жасайды. Олар сынаққа дейінгі циклдар деп аталады, өйткені сынақ денеден бұрын (алдын ала) болады. үзіліс және қайтару - бұл стандартты мінез-құлықты бейімдеуге арналған құрал.


## 5.19. Толығырақ жалпылау 

Жалпылаудың тағы бір мысалы ретінде сізге тек алтыдан алтыға дейінгі кестені емес, кез келген өлшемдегі көбейту кестесін басып шығаратын бағдарлама қажет деп елестетіңіз. print_mult_table параметріне параметр қосуға болады :

```python
def print_mult_table(high):
    for i in range(1, high+1):
        print_multiples(i)
```

7 мәнін high+1 өрнегімен ауыстырдық . 7 аргументі арқылы print_mult_table деп атасақ , ол мынаны көрсетеді:

```python
1      2      3      4      5      6
2      4      6      8      10     12
3      6      9      12     15     18
4      8      12     16     20     24
5      10     15     20     25     30
6      12     18     24     30     36
7      14     21     28     35     42
```

Бұл жақсы, тек біз кестенің төртбұрышты болуын қалауымыз мүмкін - жолдар мен бағандардың саны бірдей. Ол үшін кестеде қанша баған болуы керектігін көрсету үшін print_multiples параметріне басқа параметрді қосамыз.

Тек тітіркендіргіш болу үшін, біз бұл параметрді high деп атаймыз , бұл әртүрлі функциялардың бірдей атпен параметрлері болуы мүмкін екенін көрсетеді (жергілікті айнымалылар сияқты). Міне, бүкіл бағдарлама:

```python
def print_multiples(n, high):
    for i in range(1, high+1):
        print(n * i, end="   ")
    print()

def print_mult_table(high):
    for i in range(1, high+1):
        print_multiples(i, high)
```

Назар аударыңыз, біз жаңа параметрді қосқанда, функцияның бірінші жолын (функция тақырыбы) өзгертуге тура келді, сонымен қатар print_mult_table ішінде функция шақырылатын орынды өзгертуге тура келді .

Енді print_mult_table(7) деп атаған кезде :

```python
1      2      3      4      5      6      7
2      4      6      8      10     12     14
3      6      9      12     15     18     21
4      8      12     16     20     24     28
5      10     15     20     25     30     35
6      12     18     24     30     36     42
7      14     21     28     35     42     49
```

Функцияны дұрыс жалпылағанда, сіз жоспарламаған мүмкіндіктері бар бағдарламаны жиі аласыз. Мысалы, ab = ba болғандықтан, кестедегі барлық жазбалар екі рет пайда болатынын байқай аласыз. Кестенің жартысын ғана басып шығару арқылы сияны үнемдеуге болады. Ол үшін print_mult_table бір жолын ғана өзгерту керек . Өзгерту

```python
print_multiples(i, high+1)
```

дейін

```python
print_multiples(i, i+1)
```

және сіз аласыз:

```python
1
2 4
3 6 9
4 8 12 16
5 10 15 20 25
6 12 18 24 30 36
7 14 21 28 35 42 49
```



## 5.20 Функциялар 

Функциялардың жақсы болатынын бірнеше рет айттық. Осы уақытқа дейін сіз бұл нәрселердің не екенін сұрайтын шығарсыз. Міне, олардың кейбіреулері:

Психикалық бұзылыстарыңызды түсіру. Күрделі тапсырмаларды қосалқы тапсырмаларға бөлу және қосалқы тапсырмаларға мағыналы атау беру - күшті ақыл-ой әдісі. Тесттен кейінгі циклды суреттейтін мысалды қайта қараңыз: бізде play_the_game_once деп аталатын функция бар деп ойладық . Бұл топтастыру бізге белгілі бір ойынның егжей-тегжейлерін - бұл карта ойыны ма, жоқ па, кресттер ме, әлде рөлдік ойын ма - - және жай ғана бағдарлама логикасының бір оқшауланған бөлігіне назар аударуға мүмкіндік берді - ойыншыға қалағанын таңдауға мүмкіндік берді. қайта ойнауға.
Ұзын бағдарламаны функцияларға бөлу бағдарламаның бөліктерін бөлуге, оларды оқшаулап жөндеуге, содан кейін оларды бүтінге құруға мүмкіндік береді.
Функциялар итерацияны пайдалануды жеңілдетеді.
Жақсы жобаланған функциялар көбінесе көптеген бағдарламалар үшін пайдалы. Біреуін жазып, жөндеуден кейін оны қайта пайдалануға болады.

## 5.21. 


Енді Эйлер жолдары туралы Уикипедия мақаласын ( http://en.wikipedia.org/wiki/Eulerian_path ) оқыңыз. Шешім табуға болатын-болмайтынын тексеру арқылы бірден анықтауды үйреніңіз. Егер жол мүмкін болса, сіз сурет салуды бастау үшін қаламды қайда қою керектігін және қайда аяқтау керектігін білесіз!

num_digits(0) нені қайтарады? Осы жағдай үшін 1 қайтару үшін оны өзгертіңіз . Неліктен num_digits(-24) санына шақыру шексіз циклге әкеледі? ( кеңес: -1//10 мәні -1 деп есептеледі ) Сан_сандарын кез келген бүтін мәнмен дұрыс жұмыс істейтіндей өзгертіңіз. Мына сынақтарды қосыңыз:

```python
test(num_digits(0) == 1)
test(num_digits(-12345) == 5)
```

n санындағы жұп сандар санын есептейтін сан_жұп_цифр(n) функциясын жазыңыз . Бұл сынақтардан өту керек:

```python
test(num_even_digits(123456) == 3)
test(num_even_digits(2468) == 4)
test(num_even_digits(1357) == 0)
test(num_even_digits(0) == 1)
```

xs тізіміндегі сандардың квадраттарының қосындысын есептейтін sum_of_squares(xs) функциясын жазыңыз . Мысалы, шаршылардың_қосындысы([2, 3, 4]) 29 болатын 4+9+16 мәнін қайтаруы керек:

```python
test(sum_of_squares([2, 3, 4]) == 29)
test(sum_of_squares([ ]) == 0)
test(sum_of_squares([2, -3, 4]) == 29)
```

Сіз және сіздің досыңыз Tic-Tac-Toe / Noughts және Crosses сияқты компьютерге қарсы адам ойынын жазу үшін командадасыз. Сіздің досыңыз ойынның бір раундында ойнау логикасын жазады, ал сіз ойынның көптеген раундтарына мүмкіндік беретін логиканы жазасыз, ұпайларды сақтайсыз, кім ойнайтынын шешесіз, бірінші және т.б. бағдарлама бір-біріне сәйкес келеді және сіз мына қарапайым тіректерді ойлап табасыз (досыңыз оны кейінірек жақсартады):

```python
# Your friend will complete this function
def play_once(human_plays_first):
    """
       Must play one round of the game. If the parameter
       is True, the human gets to play first, else the
       computer gets to play first.  When the round ends,
       the return value of the function is one of
       -1 (human wins),  0 (game drawn),   1 (computer wins).
    """
    # This is all dummy scaffolding code right at the moment...
    import random                  # See Modules chapter ...
    rng = random.Random()
    # Pick a random result between -1 and 1.
    result = rng.randrange(-1,2)
    print("Human plays first={0},  winner={1} "
                       .format(human_plays_first, result))
    return result
```

Ойынды ойнау үшін осы функцияны қайта-қайта шақыратын негізгі бағдарламаны жазыңыз және әр раундтан кейін ол нәтижені «Мен жеңдім!», «Сен жеңдің!» немесе «Ойын ойнатылды!» деп хабарлайды. Содан кейін ол ойыншыдан «Қайта ойнағың келе ме?» деп сұрайды. және қайта ойнайды немесе «Қош бол» деп айтады және тоқтайды.
Әр ойыншының қанша жеңіске жеткенін және қанша тең түскенін есептеңіз. Ойынның әр турынан кейін ұпайларды да жариялаңыз.
Ойыншылар бірінші кезекте ойнау үшін логиканы қосыңыз.
Ойналған барлық ойындардың ішінен адам ұтысының пайызын есептеңіз. Әр раундтың соңында бұл туралы хабарлаңыз.
Логикаңыздың блок-схемасын сызыңыз.
