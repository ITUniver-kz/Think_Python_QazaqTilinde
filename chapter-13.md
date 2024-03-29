---
title: Файлдар
isFree: true
---

# Файлдар. Files
 
## 13.1. Файлдар туралы

Бағдарлама жұмыс істеп тұрған кезде оның деректері жедел жадта (RAM) сақталады. RAM (ЖЖҚ) жылдам және қымбат емес, бірақ ол да өзгермелі (**volatile**), яғни бағдарлама аяқталғанда немесе компьютер өшірілгенде, ЖЖҚ-дағы деректер жоғалып кетеді. Компьютер келесі рет қосылғанда және бағдарлама іске қосылғанда деректерді қолжетімді ету үшін оны қатты дискіге, USB дискісіне немесе CD-RW сияқты өзгермейтін (**non-volatile**) жадқа жазу керек.

Өзгермейтін сақтау медиасындағы деректер файлдар (**files**) деген атауы бар орындарда сақталады. Бағдарламалар файлдарды оқу және жазу арқылы программаны орындау арасында ақпаратты сақтай алады.

Файлдармен жұмыс істеу жазу кітапшасымен (notebook) жұмыс істеу сияқты. Жазу кітапшасын пайдалану үшін оны ашу керек. Аяқтағаннан кейін оны жабу керек. Жазу кітапшасы ашық тұрғанда, оны оқуға немесе жазуға болады. Кез келген жағдайда, жазу кітапшасының иесі олардың қайда екенін біледі. Олар бүкіл жазу кітапшасын басынан соңына қарай оқи алады немесе кез-келген бөлігін ашып керек ақпаратты таба алады.

Мұның бәрі файлдарға да қатысты. Файлды ашу үшін оның атын көрсетеміз және оқуды немесе жазуды қалайтынымызды көрсетеміз.

## 13.2. Бірінші файлды жазу

Файлға мәтіннің үш жолын жазатын қарапайым бағдарламадан бастайық:

```python
with open("test.txt", "w") as myfile:
    myfile.write("My first file written from Python\n")
    myfile.write("---------------------------------\n")
    myfile.write("Hello, world!\n")
```

Файлды ашу, біз файл тұтқасы (**handle**) деп атайтын нәрсені жасайды. Бұл мысалда ```myfile``` айнымалысы жаңа тұтқа нысанына сілтеме жасайды. Біздің бағдарлама тұтқадағы әдістерді шақырады және бұл әдетте дискімізде орналасқан нақты файлға өзгерістер енгізеді.

1-ші жолдағы ```open``` функциясы екі аргумент қабылдайды. Біріншісі - файлдың аты, екіншісі - режимі (**mode**). «w» режимі файлды жазу үшін ашып жатқанымызды білдіреді.

«w» режимінде дискіде ```test.txt``` деп аталатын файл болмаса, ол жасалады. Ал егер ондай файл бұрыннан бар болса, ол біз жазып жатқан жаңа файлмен ауыстырылады.

Деректерді файлға қою үшін жоғарыдағы 2, 3 және 4-ші жолдарда көрсетілген ```write``` (жазу) әдісін тұтқада шақырамыз. Үлкенірек бағдарламаларда 2-4 жолдар әдетте файлға көп жолдарды жазатын циклмен ауыстырылады.

Файл 4-жолдан кейін, ```with``` блогының соңында жабылады. Блок ```with``` қате жағдай туындаса да файлдың жабылуын қамтамассыз етеді (электр қуаты өшіп қалғанын қоспағанда).

---

Тұтқа теледидардың қашықтан басқару пульті сияқты

Теледидарға арналған қашықтан басқару пульті бәрімізге таныс. Біз қашықтан басқару пультінде операцияларды орындаймыз — арналарды ауыстырамыз, дыбыс деңгейін өзгертеміз және т.б. Бірақ нақты әрекет теледидарда болады. Осылайша, қарапайым ұқсастық бойынша қашықтан басқару пультін негізгі теледидардың _тұтқасы_ деп айтсақ болады.

Кейде біз айырмашылықты атап өткіміз келеді — файл тұтқасы файлмен бірдей емес, ал қашықтан басқару пульті теледидармен бірдей емес. Бірақ басқа уақытта біз оларды ойша біртұтас бөлік немесе абстракция ретінде қарастыруды жөн көреміз және біз жай ғана «файлды жабыңыз» немесе «телеарнаны аударыңыз» деп айтамыз.

---

## 13.3. Файлдың бір жолын бір уақытта оқу

Енді файл біздің дискімізде болғандықтан, біз оны бұл жолы оқу үшін ашып, файлдағы барлық жолдарды бір-бірден оқи аламыз. Бұл жолы режим аргументі оқу үшін "r" болып табылады:

```python
with open("test.txt", "r") as my_new_handle:
    for the_line in my_new_handle:
        # Жаңа ғана оқыған жолмен бір нәрсе жасау
        # бұл жерде біз тек басып шығарамыз
        print(the_line, end="")
```

Бұл біздің жұмысымыз үшін ыңғайлы үлгі. Үлкенірек бағдарламаларда біз 5-ші жолдағы циклдің негізгі бөлігіне кеңірек логиканы енгізетін едік - мысалы, файлдың әрбір жолында достарымыздың бірінің аты мен электрондық пошта мекенжайы болса, біз тіркесті екіге бөлетін едік және досыңызға кешке шақыруды жіберу үшін функцияны жазатын едік.

5-ші жолда ```print``` басып шығару функциясының тіркес соңында әдетте жазылатын жаңа жол (\\n) таңбасын ```end = " "```-пен ауыстырдық. Неліктен? Себебі тіркестің өзінің жаңа жолы бар: 2-ші жолдағы ```for``` амалы тіркестің барлығын жаңа жолға дейін және жаңа жолды қамтып бірге оқиды. 

Егер жоқ файлды ашуға әрекеттенсек, қатені аламыз:

```python
>>> mynewhandle = open("wharrah.txt", "r")
FileNotFoundError: [Errno 2] No such file or directory: "wharrah.txt"
```

## 13.4. Файлды жолдар тізіміне айналдыру

Дискілік файлдан деректерді алу және оны жолдар тізіміне айналдыру жиі пайдалы. Бізде достарымыз бен олардың электрондық пошта мекенжайлары бар файл бар делік, файлдағы әр жолға біреуі жазылған. Бірақ біз жолдардың алфавиттік ретпен сұрыпталғанын қалаймыз. Жақсы жоспар - бәрін жолдар тізімінде оқып, содан кейін тізімді сұрыптау, содан кейін сұрыпталған тізімді басқа файлға қайта жазу:

```python
with open("friends.txt", "r") as input_file:
    all_lines = input_file.readlines()
    all_lines.sort()

with open("sortedfriends.txt", "w") as output_file:
    for line in all_lines:
        output_file.write(line)
```

2 - жолдағы ```readlines``` әдісі барлық жолдарды оқиды және тіркестердің тізімін қайтарады.

Біз алдыңғы бөлімдегі үлгіні әр жолды бір-бірден оқып, тізімді өзіміз жасау үшін пайдалана алар едік, бірақ Python жасақтаушылары берген әдісті пайдалану әлдеқайда оңай!

## 13.5. Бүкіл файлды бірден оқу

Мәтіндік файлдармен жұмыс істеудің тағы бір тәсілі - файлдың толық мазмұнын тіркеске оқу, содан кейін мазмұнмен жұмыс істеу үшін тіркестерді өңдеу дағдыларын пайдалану.

Егер файлдың жол құрылымы бізді қызықтырмаса, біз әдетте файлдарды өңдеудің осы әдісін қолданатын едік. Мысалы, тіркестерді сөздерге бөлуге болатын тіркестегі ```split``` (бөлу) әдісін көрдік. Сонымен, файлдағы сөздердің санын қалай санауға болатыны төменде:

```python
with open("somefile.txt") as f:
    content = f.read()
words = content.split()
print("There are {0} words in the file.".format(len(words)))
```

Мұнда 1-ші жолда "r" режимін қалдырғанымызға назар аударыңыз. Әдепкі бойынша, режимді бермесек, Python файлды оқу үшін ашады.

---

Файл жолдарының атауы нақты жазылуы талап етілуі мүмкін.

Жоғарыдағы мысалда ```somefile.txt``` файлы Python бастапқы кодымен бірдей папкада деп болжаймыз. Бұлай болмаса, файлға толық немесе салыстырмалы жолды беру қажет болуы мүмкін. Windows жүйесінде толық жол "```C:\\temp\\somefile.txt```" сияқты көрінуі мүмкін, ал Unix жүйесінде толық жол "```/home/jimmy/somefile.txt```" болуы мүмкін .

Біз бұған кейінірек осы тарауда қайта ораламыз.

---

## 13.6. Мысал

Көптеген пайдалы жолды-өңдеу бағдарламалары мәтіндік файлды бір уақытта бір жолдан оқиды және жолдарды шығыс файлына жазғанда аздаған өңдеулер жасайды. Мысалы, олар шығыс файлындағы жолдарды нөмірлей алады немесе қағаз парақтарында басып шығаруды ыңғайлы ету үшін әрбір 60 жолдан кейін қосымша бос жолдарды кірістіруі немесе бастапқы файлдағы әрбір жолдан ғана белгілі бір бағандарды шығаруы немесе тек басып шығару substring (ішкі тіркес) бар жолдарды шығаруы мүмкін. Мұндай бағдарламаны фильтр (**filter**) деп атаймыз.

Мұнда # деп басталатын жолдарды өткізіп жіберіп, бір файлды екіншісіне көшіретін фильтр берілген:

```python
def filter(oldfile, newfile):
     with open(oldfile, "r") as infile, open(newfile, "w") as outfile:
         for line in infile:
             # Put any processing logic here
             if not line.startswith('#'):
                 outfile.write(line)
```

2-ші жолда біз екі файлды ашамыз: оқитын файл, және жазатын файл. 3-жолдан бастап кіріс файлын бір-бір жол бойынша оқимыз. 5-жолдағы шарт ақиқат болған жағдайда ғана жолды шығыс файлына жазамыз.

## 13.7. Папкалар / Directories

Өзгермейтін сақтау медиасындағы файлдар файлдық жүйе (**file system**) деп аталатын ережелер жиынтығымен ұйымдастырылады. Файлдық жүйелер файлдар мен каталогтардан (**directories**) тұрады, олар файлдар мен басқа каталогтар үшін контейнерлер болып табылады.

Жаңа файлды ашу және жазу арқылы жасағанда, жаңа файл ағымдағы папкаға түседі (бағдарламаны іске қосқан кезде қай жерде болсақ та). Сол сияқты, оқу үшін файлды ашқанда, Python оны ағымдағы папкадан іздейді.

Егер басқа жерде орналасқан файлды ашқымыз келсе, файлға апаратын жолды (**path**) көрсетуіміз керек, ол файл орналасқан каталогтың (папканың) атауы:

```python
>>> wordsfile = open("/usr/share/dict/words", "r")
>>> wordlist = wordsfile.readlines()
>>> print(wordlist[:6])
['\n', 'A\n', "A's\n", 'AOL\n', "AOL's\n", 'Aachen\n']
```

Бұл (Unix) мысал ```dict``` деп аталатын папкада орналасқан ```words``` файлын ашады, ал ```dict``` папкасы ```share``` папкасында, ал ```share``` ```usr``` папкасында орналасқан, ал ```usr``` өз кезегінде жүйенің top-devel (жоғарға деңгей) **/** папкада орналасқан.

Windows жолы "c:/temp/words.txt" немесе "c:\\temp\\words.txt" болуы мүмкін . Кері қиғаш сызықтар жаңа жолдар мен қойындылар сияқты нәрселерден құтылу үшін пайдаланылғандықтан, біреуін алу үшін біз екі кері қиғаш сызық жазуымыз керек! Демек, бұл екі жолдың ұзындығы бірдей!

Біз файл атауының бөлігі ретінде **/** немесе **\\** пайдалана алмаймыз; олар папка пен файл атаулары арасындағы бөлгіш ретінде сақталған.

Каталогтардағы файлдармен жұмыс істегенде, Python-ға барлық қиғаш сызықтармен жұмыс істеуге және олардан құтылуға мүмкіндік берген дұрыс. ```os.path``` модулі мұны әртүрлі операциялық жүйелер үшін жасайды. ```os.path```.join("directory", "filename") автоматты түрде Unix/Linux жүйесінде "каталог/файл атын" және Windows жүйесінде "каталог\\ файл атауын" қайтарады. Бұл кодты бір жүйеден екінші жүйеге көшіруде ғана емес кодты әріптестермен бөлісу кезінде үлкен көмек бола алады. Бұл сондай-ақ оған өзіңіз қадағалаудың қажеті жоқ екенін білдіреді және ол сізге тіркесті өңдеуге қатысты кейбір қателерден құтқаруы мүмкін.

Сондай-ақ файлдарды өңдеуге көмектесетін басқа ыңғайлы мүмкіндіктер үшін ```os.path``` модулін ары қарай зерттеуге болады.

```/usr/share/dict/words``` файлы Unix негізіндегі жүйелерде болуы керек және алфавиттік тәртіпте сөздердің тізімін қамтиды.

## 13.8. Интернеттен бірдеңе алу туралы не деуге болады?

Python library (кітапханалары) кейбір жерлерде өте шимақ, түсініксіз. 

Бірақ мұнда кейбір веб-URL мекенжайындағы мазмұнды жергілікті файлға көшіретін өте қарапайым мысал бар.

```python
import urllib.request

url = "http://xml.resource.org/public/rfc/txt/rfc793.txt"
destination_filename = "rfc793.txt"

urllib.request.urlretrieve(url, destination_filename)
```

```urlretrieve``` функциясы — бір ғана шақыру — Интернеттен мазмұнның кез келген түрін жүктеп алу үшін пайдаланылуы мүмкін.

**Бұл жұмыс істуеі үшін бірнеше нәрсені алдын ала реттеп алуымыз керек:**

- Біз алуға тырысып жатқан ресурс бар болуы керек! Мұны браузер арқылы тексеріңіз.

- Файл жазылатын орында біз жаза алу құқығы болу керек және файл «ағымдағы каталогта» жасалады, яғни Python бағдарламасы сақталған папкада.

- Егер біз аутентификацияны қажет ететін прокси-сервердің артында тұрсақ (кейбір студенттер сияқты), бұл біздің проксиді айналып өту үшін арнайы өңдеуді қажет етуі мүмкін. Сондықтан осы демонстрация үшін жергілікті ресурсты пайдаланыңыз!

- Біз интернеттен кез келген деректерді пайдаланатын болсақ, мазмұнның біз күткендей болуын тексеретінімізге көз жеткізуіміз керек. Веб-сайт өзгеруі немесе жойылып кетуі мүмкін. Немесе сайттың контентін мүлдем өзгертіп тастаған жаңа иесі де болуы мүмкін. Сондықтан интернеттегі деректерді пайдаланбас бұрын, кез келген кодты орындамас бұрын немесе оны кез келген маңызды пайдаланушыларға көрсетпес бұрын бағдарламаңыз деректердің сіз қалағандай екенін тексеріп алыңыз!

Мұнда ```requests``` (сұраулар) модулін қолданатын сәл басқа мысал келтірілген. Бұл модуль python арқылы таратылатын стандартты кітапхананың бөлігі емес, бірақ оны пайдалану оңай және python арқылы таратылған ```urllib``` модуліне қарағанда әлдеқайда күшті. Модульді орнату және пайдалану жолын білу үшін Google-дан іздестіріп қарап, толығырақ танысыңыз. Мұнда веб-ресурсты жергілікті дискіге сақтаудың орнына, біз оны тікелей жолға оқимыз және сол жолды басып шығарамыз:

```python
import requests

url = "http://xml.resource.org/public/rfc/txt/rfc793.txt"
response = requests.get(url)
print(response.text)
```

Қашықтағы URL мекенжайын ашу серверден жауапты қайтарады. Бұл жауап ақпараттың бірнеше түрін қамтиды және сұраулар модулі оларға әртүрлі жолдармен қол жеткізуге мүмкіндік береді. 5-жолда жүктеп алынған құжатты бір жол ретінде аламыз. Біз оны келесідей жол-жол оқи аламыз:

```python
import requests

url = "http://xml.resource.org/public/rfc/txt/rfc793.txt"
response = requests.get(url)
for line in response:
    print(line)
```

## 13.9. Глоссарий 

**бөлгіш** / **delimiter**
Мәтіннің жеке бөліктері арасындағы шекараны анықтау үшін пайдаланылатын бір немесе бірнеше таңбалар тізбегі.

**каталог/папка** / **directory**
Файлдар жинағының атауы, папка, каталог ағылшын тілінде folder/directory бәрі бір мағынаны білдіреді. Каталогтар файлдарды және басқа каталогтарды қамтуы мүмкін.
Ішкі каталогтар _subfolders_ не _subdirectories_ деп аталады

**файл** / **file**
Әдетте қатты дискіде, иілгіш дискіде немесе CD-ROM-да сақталатын, таңбалар жиынын қамтитын атаулы нысан.

**файлдық жүйе** / **file system**
Файлдар мен ондағы деректерді атауға, қол жеткізуге және ұйымдастыруға арналған әдіс.

**тұтқа** / **handle**
Негізгі ресурсқа (мысалы, файл) қосылған бағдарламамыздағы нысан. Файл тұтқасы біздің бағдарламамызға дискіміздегі нақты файлды өңдеуге/оқуға/жазуға/жабуға мүмкіндік береді.

**режимі** / **mode**
Компьютерлік бағдарлама ішінде жұмыс істеудің ерекше әдісі. Python-дағы файлдарды төрт режимнің бірінде ашуға болады: оқу ( "r" ), жазу ( "w" ), қосу ( "a" ) және оқу/жазу ( "+" ).

**тұрақты жад** / **non-volatile memory**
Қуатсыз күйін сақтай алатын жады. Қатты дискілер, флэш-дискілер және қайта жазылатын компакт-дискілер (CD-RW) тұрақты жадтың әрбір мысалы болып табылады.

**жол** / **path**
Файлдың нақты орнын көрсететін каталог атауларының тізбегі.

**мәтіндік файл** / **text file**
Жаңа жол таңбаларымен бөлінген, жолдарға реттелген (басып шығарылатын) таңбаларды қамтитын файл.

**тұрақсыз жады** / **volatile memory**
Жад күйін сақтау үшін электр тогын қажет етеді. Компьютердің _негізгі жады_ немесе жедел жады тұрақсыз болып табылады. ЖЖҚ-да сақталған ақпарат компьютер өшірілгенде жоғалады.

## 13.10. Жаттығулар 

1. Файлды оқитын және жолдардың кері ретімен жаңа файлды жазатын бағдарламаны жазыңыз (яғни ескі файлдағы бірінші жол жаңа файлдағы соңғы жолға айналады).

2. Файлды оқитын және ```доп``` ішкі жолды қамтитын жолдарды ғана басып шығаратын программа жазыңыз. (prints text with substring ```ball```)

3. Мәтіндік файлды оқитын және файлдың көшірмесі болып табылатын шығыс файлын шығаратын бағдарламаны жазыңыз, тек әрбір жолдың алғашқы бес бағанында төрт таңбалы жол нөмірі, одан кейін бос орын болуы керек. Шығару файлындағы бірінші жолды нөмірлеуді 1-ден бастаңыз. Әрбір жол нөмірі шығыс файлында бірдей енге пішімделгеніне көз жеткізіңіз. Осы жаттығу үшін сынақ деректері ретінде Python бағдарламаларының бірін пайдаланыңыз: сіздің шығысыңыз Python бағдарламасының басып шығарылған және нөмірленген тізімі болуы керек.

4. Алдыңғы жаттығудың нөмірленуін болдырмайтын бағдарламаны жазыңыз: ол нөмірленген жолдармен файлды оқып, жол нөмірлері жоқ басқа файлды шығаруы керек.

5. Жоғарыда қолданылған сөздікті алып, 1337sp34k көмегімен кейбір сөздерді қайтаратын бағдарламаны жазыңыз.
