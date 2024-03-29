---
title: Объектілердің жинақтары
isFree: true
---

# Объектілердің жинақтары / Collections of objects

## 20.1. Объектілердің құрамы, композициясы

Осы уақытқа дейін біз композицияның бірнеше мысалдарын көрдік. Алғашқы мысалдардың бірі өрнек бөлігі ретінде әдісті шақыруды пайдалану болды. Басқа мысал - операторлардың кірістірілген (nested) құрылымы; ```if``` операторын ```while``` цикл ішінде, басқа ```if``` амалының ішіне және т.б. қоюға болады.

Бұл үлгіні көріп, тізімдер мен объектілер туралы біліп, біз объектілер тізімдерін жасай алатынымызды білуге таң қалмауымыз керек. Біз сондай-ақ тізімдерді (атрибуттар ретінде) қамтитын объекттерді жасай аламыз; біз тізімдерді қамтитын тізімдерді жасай аламыз; біз объектілерді қамтитын объектілерді жасай аламыз; және тағы сол сияқты.

Осы және келесі тарауда біз мысал ретінде ```Card``` объектілерін пайдалана отырып, осы комбинациялардың кейбір мысалдарын қарастырамыз.

## 20.2. Card объектілері

Егер сіз қарапайым ойын карталарымен таныс болмасаңыз, қазір бір қорап ойын картасын алудың жақсы уақыты болар еді, әйтпесе бұл тараудың мағынасы болмауы мүмкін. Ойын картасында елу екі карта бар, олардың әрқайсысы төрт мастьтың (suit - оқылуы _сиуут_) біріне және он үш дәреженің (rank) біріне жатады. Масть - қарға, жүрек, қиық және шыбын ([Bridge](https://en.wikipedia.org/wiki/Contract_bridge) карта ойынындағы ретпен). Дәрежелер: Тұз, 2, 3, 4, 5, 6, 7, 8, 9, 10, Валет, Дама және Король. Біз ойнап жатқан ойынға байланысты Тұз дәрежесі Корольден жоғары немесе 2-ден төмен болуы мүмкін. Ранг/дәреже кейде картаның номиналды құны деп аталады.

![Cards_Kaz](https://user-images.githubusercontent.com/84173441/177247651-62f4b478-da72-459f-b157-39bdcfb1861a.JPG)

\* _Ағылшынша - қазақша атаулары. Осы бөлімдегі сабақ үшін маңызды. Жаттап алғандарыңыз жөн_
![Suit](https://user-images.githubusercontent.com/84173441/177249457-c74ecd4f-bb71-4411-a9d5-0236130f13d9.JPG)

Ойын картасын көрсету үшін жаңа обътектіні анықтағымыз келсе, атрибуттардың қандай болуы керектігі анық: ```rank``` және ```suit```. Атрибуттардың қандай type болуы керек екені анық емес. Мүмкіндіктердің бірі - масть үшін «Spade» және дәрежелер үшін «Queen» сияқты сөздерді қамтитын тіркестерді пайдалану. Бағдарламаны бұлай жазып бастаудың бір проблемасы карталардың қайсысының мастьі немесе дәрежесі үлкен екенін анықтау қиын болады.

Өзге тәсілі - дәрежелер мен мастьтарды **кодтау** үшін бүтін сандарды пайдалану. Бұл жерде біздің кодтау деп отырғанымыз шифрлау немесе құпия кодқа айналдыру емес. Кодтау сөзін қолданып компьютер ғалымының айтқысы келетіні мен көрсеткім келетін элементтерді сандар тізбегіне сәйкестендіру. Мысалға:

```python
Spades / Қарға  --> 3
Hearts / Жүрек  --> 2
Diamonds / Қиық --> 1
Clubs / Шыбын   --> 0
```

Бұлай сәйкестендірудің айқын артықшылығы біз бүтін сандарды салыстыру арқылы мастьтарды салыстыра аламыз. Дәрежелер үшін сәйкестендіру өте айқын; сандық дәрежелердің әрқайсысы сәйкес бүтін санға сәйкестендіріледі, 2-2, 3-3 ... 10-10, ары қарай Валет - 11, Дама - 12, Кароль - 13 және Тұз 1 болады:

```python
Ace / Тұз  --> 1
Jack / Валет --> 11
Queen / Дама --> 12
King / Король --> 13
```

Бұл сәйкестендірулер үшін математикалық белгілерді пайдалануымыздың себебі, олар біздің Python бағдарламамыздың бөлігі емес. Олар бағдарлама дизайнының бөлігі болып табылады, бірақ олар ешқашан кодта анық жазылмайды. ```Card``` type/түріне класс анықтамасы келесідей:

```python
class Card:
    def __init__(self, suit=0, rank=0):
        self.suit = suit
        self.rank = rank
```

Әдеттегідей, біз әрбір атрибут үшін қосымша параметрді қабылдайтын инициализация әдісін береміз.

Енді, мысалы 3 Шыбынды және Валет Қиықты білдіретін объектіні жасау үшін біз мынандай код жазар едік:

```python
three_of_clubs = Card(0, 3)
card1 = Card(1, 11)
```

Жоғарыдағы алғашқы кодта бірінші аргумент, 0, Шыбын мастьін білдіреді.

---

**Бұл кодты кейінірек пайдалану үшін сақтаңыз** ...

```Cards.py``` деп аталатын файлда ```Cards``` классын және ```Deck``` (алда қарастырылады) классын сақтап қойыңыз. Алдағы тарауларда қолданамыз.

---

## 20.3. Класс атрибуттары және str әдісі

```Cards``` объектілерін адамдар оңай оқи алатындай етіп басып шығару үшін біз бүтін сандар кодын сөздермен сәйкестендіргіміз келеді. Мұны істеудің әдеттегі табиғи жолы - тіркестер тізімдері. Бұл тізімдерді класс анықтамасының жоғарғы жағындағы **класс атрибуттарына** тағайындаймыз:

```python
class Card:
    suits = ["Clubs", "Diamonds", "Hearts", "Spades"]
    ranks = ["narf", "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"]
    
    def __init__(self, suit=0, rank=0):
        self.suit = suit
        self.rank = rank
        
    def __str__(self):
        return (self.ranks[self.rank] + " of " + self.suits[self.suit])
```

Класс атрибуты кез келген әдістен тыс анықталады және оған класстағы кез келген әдістерден қол жеткізуге болады.

```__str__``` ішінде біз масть пен дәреженің сандық мәндерін тіркестерге сәйкестендіру үшін пайдалана аламыз. Мысалы, ```self.suits[self.suit]``` өрнегі ```self``` объектісіндегі ```suit``` атрибутын ```suits``` деп аталатын класс атрибутына индекс ретінде пайдалан, және сәйкес тіркесті таңда дегенді білдіреді.

```ranks```-тағы бірінші элементтің ```narf``` болу себебі ешқашан пайдаланылмайтын тізімнің нөлдік элементі үшін орын сақтаушы ретінде әрекет ету. Жалғыз жарамды дәрежелер ```ranks``` 1-ден 13-ке дейін. Біз әдеттегідей 0-ден бастай алар едік, бірақ 2-дәрежені бүтін 2, 3-ті 3 және т.с.с. ретінде кодтау ыңғайлы әрі түсінікті екені анық.

Бізде бар әдістердің көмегімен біз карталарды жасай аламыз және басып шығара аламыз:

```python
>>> card1 = Card(1, 11)
>>> print(card1)
Jack of Diamonds
```

```python
class Card:
    suits = ["Шыбын", "Қиық", "Жүрек", "Қарға"]
    ranks = ["narf", "Тұз", "2", "3", "4", "5", "6", "7",
             "8", "9", "10", "Валет", "Дама", "Король"]

    def __init__(self, suit=0, rank=0):
        self.suit = suit
        self.rank = rank

    def __str__(self):
        return (self.ranks[self.rank] + " " + self.suits[self.suit])

card1 = Card(1, 13)

print(card1)
```

```suits``` сияқты класс атрибуттары барлық ```Card``` объектілеріне ортақ. Мұның артықшылығы мынада, біз класс атрибуттарына қол жеткізу үшін кез келген ```Card``` объектісін пайдалана аламыз:

```python
>>> card2 = Card(1, 3)
>>> print(card2)
3 of Diamonds
>>> print(card2.suits[1])
Diamonds
```

Әрбір ```Card``` данасы бірдей класс атрибутына сілтеме жасайтындықтан, бізде бүркеншік аттар мәселесі бар. Кемшілігі класс атрибутын өзгертетін болсақ, ол осы класстың әрбір данасына әсер етеді. Мысалы, егер біз Валет қиық негізінде Валет кірпіш деп аталуы керек екен десек, біз мұны істей аламыз:

```python
>>> card1.suits[1] = "Кірпіш"
>>> print(card1)
Валет кірпіш
```

Мәселе мынада, барлық қиықтар бірден кірпішке айналды:

```python
>>> print(card2)
3 Кірпіш
```

Әдетте класс атрибуттарын өзгерту жақсы идея емес.


## 20.4. Карталарды салыстыру

Қарапайым типтер үшін мәндерді салыстыратын және біреуі екіншісінен үлкен, кіші немесе тең екенін анықтайтын алты реляциялық оператор (<, >, ==, т.б.) бар. Егер біз осы реляциялық операторлардың синтаксисін пайдалана отырып, өз типтерімізді салыстыруға болатынын қаласақ, біздің класста сәйкес алты арнайы әдісті анықтауымыз керек.

Біз тапсырыс логикасын қамтитын ```cmp``` деп аталатын жалғыз әдіспен бастағымыз келеді. Салыстыру әдісі шарт бойынша, ```self``` және ```other``` екі параметрді қабылдайды және бірінші объект үлкен болса 1 мәнін, екінші объект үлкен болса -1 мәнін және олар бір-біріне тең болса 0 мәнін қайтарады.

Кейбір түрлер толығымен реттелген, яғни біз кез келген екі элементті салыстырып, қайсысы үлкен екенін айта аламыз. Мысалы, бүтін сандар мен өзгермелі нүктелі сандар толығымен реттелген. Кейбір түрлер ретсіз, яғни бір элемент екіншісінен үлкен деп айтудың мағыналы жолы жоқ. Мысалы, жемістер ретсіз, сондықтан алма мен апельсинді салыстыра алмаймыз, сол сияқты суреттер жинағын немесе ұялы телефондар жинағын мәнді түрде реттей алмаймыз.

Ойын карталары ішінара реттелген, яғни біз кейде карталарды салыстыра аламыз, ал кейде жоқ. Мысалы, біз 3 Шыбын 2 Шыбыннан жоғары, ал 3 Қиық 3 Шыбыннан жоғары. Бірақ қайсысы жақсы: 3 Қиық немесе 2 жүрек? Біреуінің дәрежесі жоғары, ал екіншісінің мастьі жоғары.

Карталарды бір-бірімен салыстыра алатындай ету үшін біз қайсысы маңыздырақ екенін шешуіміз керек: дәреже немесе масть. Шынын айтқанда, таңдау ерікті. Жәй мысал таңдау үшін біз масть маңыздырақ деп алайық, өйткені карталардың жаңа қорабы бірінші барлық Шыбындар бірге сұрыпталған, одан кейін барлық Қиықтар және т.б.

Осылай шешіп алған соң, ```cmp``` былай жаза аламыз:

```python
def cmp(self, other):
    # Check the suits / Мастьтарды салыстыр
    if self.suit > other.suit: return 1
    if self.suit < other.suit: return -1
    # Suits are the same... check ranks / мастьтар бірдей ... дәрежелерді тексер
    if self.rank > other.rank: return 1
    if self.rank < other.rank: return -1
    # Ranks are the same... it's a tie / Дәрежелері де бірдей ... бұл тең
    return 0
```

Бұл ретте Тұздар 2-ден қарағанда төмен болып келеді.

Енді біз реляциялық операторлардың әрқайсысының шамадан тыс жүктелуін жүзеге асыратын алты арнайы әдісті анықтай аламыз:

```python
def __eq__(self, other):
    return self.cmp(other) == 0

def __le__(self, other):
    return self.cmp(other) <= 0

def __ge__(self, other):
    return self.cmp(other) >= 0

def __gt__(self, other):
    return self.cmp(other) > 0

def __lt__(self, other):
    return self.cmp(other) < 0

def __ne__(self, other):
    return self.cmp(other) != 0
```

Осы техниканың көмегімен реляциялық операторлар енді біз қалағандай жұмыс істейді:

```python
>>> card1 = Card(1, 11)
>>> card2 = Card(1, 3)
>>> card3 = Card(1, 11)
>>> card1 < card2
False
>>> card1 == card3
True
```

## 20.5. Карта бумасы - Deck

Енді бізде карталарды көрсететін ```Cards``` объекті бар, келесі логикалық қадам карта бумасын көрсететін классты анықтау болып табылады. Әрине, бума карталардан тұрады, сондықтан әрбір ```Deck``` объектісінде атрибут ретінде карталар тізімі болады. Көптеген карта ойындарына кем дегенде екі түрлі карта бумасы қажет болады - қызыл бума және көк бума.

Төменде Deck классының класс анықтамасы берілген. Инициализация әдісі ```cards``` атрибутын жасайды және елу екі картаның стандартты бумасын шығарады:

```python
class Deck:
    def __init__(self):
        self.cards = []
        for suit in range(4):
            for rank in range(1, 14):
                self.cards.append(Card(suit, rank))
```

Карта бумасын толтырудың ең оңай жолы - кірістірілген цикл. Сыртқы цикл мастьтарды 0-ден 3-ке дейін номерлейді. Ішкі цикл 1-ден 13-ке дейін дәрежелерді номерлейді. Сыртқы цикл төрт рет, ал ішкі цикл он үш рет қайталанатындықтан, дененің жалпы орындалу саны елу-екі (он үш көбейту төрт). Әрбір итерация ағымдағы масть пен дәрежесі бар ```Card```-тың жаңа данасын жасайды және сол картаны карталар тізіміне қосады.

Осыларды болған соң, біз қалаған карта бумасын жасай аламыз:

```python
red_deck = Deck()
blue_deck = Deck()
```

## 20.6 Карта бумасын басып шығару

Әдеттегідей, жаңа түрді анықтаған кезде біз дананың мазмұнын басып шығаратын әдісті қалаймыз. ```Deck```-ті басып шығару үшін біз
тізімді айналып өтіп, әрбір картаны ```Card``` басып шығарамыз:

```python
class Deck:
    ...
    def print_deck(self):
        for card in self.cards:
            print(card)
```

Мұнда және бұдан былай көп нүкте (...) класстағы басқа әдістерді өткізіп жібергенімізді көрсетеді.

```print_deck```-ке балама ретінде біз ```Deck``` классы үшін ```__str__``` әдісін жаза аламыз. ```__str__``` артықшылығы оның икемділігінде. Объекттің мазмұнын жай ғана басып шығарудың орнына, ол бағдарламаның басқа бөліктері басып шығару алдында басқара алатын немесе кейінірек пайдалану үшін сақтай алатын тіркес көрінісін жасайды.

Мұнда ```Deck```-тің тіркес көрінісін қайтаратын ```__str__``` нұсқасы берілген. Біраз "әдемілік" қосу үшін ол карталарды каскадқа орналастырады, онда әрбір карта алдыңғы картаға қарағанда бір бос орынға шегініс жасайды:

```python
class Deck:
    ...
    def __str__(self):
        s = ""
        for i in range(len(self.cards)):
            s = s + " " * i + str(self.cards[i]) + "\n"
        return s
```

![ordred_deck](https://user-images.githubusercontent.com/84173441/177281702-a81c002f-1f0f-4e0d-a657-311e7506548d.JPG)


Бұл мысал бірнеше мүмкіндіктерді көрсетеді. Біріншіден, ```self.cards``` арқылы өту (traverse) және әр картаны айнымалыға тағайындаудың орнына, біз циклдік айнымалы және карталар тізіміне индекс ретінде ```i```-ды пайдаланамыз.

Екіншіден, біз әрбір картаны соңғысынан бір бос орынға шегініс жасау үшін тіркесті көбейту операторын қолданамыз. ```" " * i``` өрнегі ағымдағы ```i``` мәніне тең бос орындар санын береді.

Үшіншіден, карталарды басып шығару үшін ```print``` командасын пайдаланудың орнына біз ```str``` функциясын қолданамыз. Объектті ```str```-ге аргумент ретінде беру объектте ```__str__``` әдісін шақыруға тең.

Соңында, біз ```s``` айнымалысын **аккумулятор** ретінде қолданамыз. Бастапқыда ```s``` бос тіркес болып табылады. Циклдің әрбір айналымында жаңа тіркес жасалады және ескі ```s``` мәнімен біріктіріліп жаңа мән алынады. Цикл аяқталған кезде, ```s``` карта бумасының, ```Deck```, толық тіркес көрінісін қамтиды, ол келесідей көрінеді:

```python
>>> red_deck = Deck()
>>> print(red_deck)
Ace of Clubs
  2 of Clubs
    3 of Clubs
      4 of Clubs
        5 of Clubs
         6 of Clubs
          7 of Clubs
            8 of Clubs
              9 of Clubs
                10 of Clubs
                  Jack of Clubs
                    Queen of Clubs
                      King of Clubs
                        Ace of Diamonds
                          2 of Diamonds
                            ...
```

_... және ары қарай_. Нәтиже 52 жолда пайда болса да, бұл жаңа жолдарды қамтитын бір ұзын тіркес.

## 20.7 Картаны араластыру

Егер карта бумасы жақсылап араластырылған болса, онда кез келген карта буманың кез келген жерінде пайда болуы және бумадағы кез келген жерде кез келген картаның болуы бірдей ықтимал.

Буманы араластыру үшін біз ```random``` модульден ```randrange``` функциясын қолданамыз. ```a``` және ```b``` екі бүтін аргументпен, ```randrange``` ```a <= x < b``` ауқымында кездейсоқ бүтін санды таңдайды. Жоғарғы шекара ```b```-дан қатаң түрде аз болғандықтан, біз екінші параметр ретінде тізімнің ұзындығын пайдалана аламыз және заңды индекс аламыз деп нақты айта аламыз. Мысалы, ```rng``` кездейсоқ сандар коды ретінде бұрыннан жазылып қойған болса, мына өрнек бумадағы кездейсоқ картаның индексін таңдайды:

```python
rng.randrange(0, len(self.cards))
```

Карта бумасын араластырудың оңай жолы - карталарды айналып өту және әрбір картаны кездейсоқ таңдалған картамен ауыстыру. Карта өзін өзі ауыстыруы мүмкін, бірақ бұл қабылданатын жағдай. Шынымен де, егер біз бұл жағдайды алып тастайтын болсақ, карталардың араласуы толығымен кездейсоқ болмай қалар еді:

```python
class Deck:
    ...
    def shuffle(self):
        import random
        rng = random.Random() # Create a random generator
        num_cards = len(self.cards)
        for i in range(num_cards):
            j = rng.randrange(i, num_cards)
            (self.cards[i], self.cards[j]) = (self.cards[j], self.cards[i])
```

Карта бумасында елу екі карта бар деп болжаудың орнына, біз тізімнің нақты ұзындығын аламыз және оны ```num_cards``` ішінде сақтаймыз.

Бумадағы әрбір карта үшін біз әлі араластырылмаған карталардың арасынан кездейсоқ картаны таңдаймыз. Содан кейін ағымдағы картаны (i) таңдалған картамен (j) ауыстырамыз. Карталарды ауыстыру үшін біз кортеж тағайындауын қолданамыз:

```python
(self.cards[i], self.cards[j]) = (self.cards[j], self.cards[i])
```

Бұл жақсы араластыру әдісі болғанымен, кездейсоқ сандар генераторы ```random``` объектісінде тізімдегі элементтерді орнында араластыра алатын ```shuffle``` әдісі де бар. Сондықтан біз бұл функцияны біз үшін берілген кірістірілген, дайын функциямен қайта жаза аламыз:

```python
class Deck:
    ...
    def shuffle(self):
        import random
        rng = random.Random() # Create a random generator
        rng.shuffle(self.cards) # uUse its shuffle method
```

## 20.8. Карталарды алып тастау және тарату

```Deck``` классы үшін пайдалы болатын тағы бір әдіс ```remove``` - ол картаны параметр ретінде қабылдайды және оны бумадан алып тастайды, карта бумада болса ```True``` мәнін, ал кері жағдайда ```False``` мәнін қайтаратын жою әдісі:

```python
class Deck:
    ...
    def remove(self, card):
        if card in self.cards:
            self.cards.remove(card)
            return True
        else:
            return False
```

Бірінші операнд екіншісінде болса ```in``` операторы ```True``` мәнін қайтарады. Бірінші операнд объект болса, Python тізімдегі элементтермен теңдікті анықтау үшін объекттің ```__eq__``` әдісін пайдаланады. Карта классында берілген ```__eq__``` терең теңдікті тексеретіндіктен, ```remove``` әдісі терең теңдікті тексереді.

Карталарды тарату үшін біз жоғарғы картаны жойып оны қайтарғымыз келеді. Тізім әдісі ```pop``` мұны істеудің ыңғайлы әдісін ұсынады:

```python
class Deck:
    ...
    def pop(self):
        return self.cards.pop()
```

Шын мәнінде, ```pop``` тізімдегі _соңғы_ картаны жояды, сондықтан біз карта бумасын төменгі жағынан таратып жатырмыз десек болады.

Біз қажет ететін тағы бір операция - бұл логикалық функция ```is_empty```, ол бумада карталар болмаса, ```True``` мәнін қайтарады:

```python
class Deck:
    ...
    def is_empty(self):
        return self.cards == []
```

## 20.9 Глоссарий

**кодтау** / **encode**
Бір-біріне сәйкестендіру арқылы мәннің бір түрін басқа түр арқылы көрсету.

**класс атрибуты** / **class attribute**
Класс анықтамасының ішінде, бірақ кез келген әдістен тыс анықталған айнымалы. Класс атрибуттарына класстағы кез келген әдіс арқылы қол жеткізуге болады және класстың барлық даналарына ортақ болады.

**аккумулятор** / **accumulator**
Циклдегі мәндр тізбегін біріктіріп жинайтын айнымылы, мысалы, оларды тіркестерге конкатенациялайды немесе ағымдағы санға қосып отырады.

## 20.10 Жаттығулар

1. ```cmp```-да Тұздар корольден жоғары болатындай етіп кодты қайта жазыңыз.

