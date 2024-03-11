---
title: Дерек типтері. Көбірек
isFree: true
---

# Көбірек дерек түрлерін қарастырайық

Сіз Python ұсынатын ең маңызды деректер түрлерін кездестірдіңіз: bools, ints, floats, strings, кортеждер, тізімдер және сөздіктер. Дегенмен, бұған дейін айтылғаннан да көп нәрсе бар. Бұл бөлімде біз негізінен кортеждер мен тізімдерге назар аударамыз және жиындар мен мұздатылған жинақтарды енгіземіз.

## 9.1 Өзгермейтін және бүркеншік атын өзгерту

Python тіліндегі кейбір деректер түрлері өзгермелі. Бұл олардың мазмұнын жасалғаннан кейін өзгертуге болатынын білдіреді. Тізімдер мен сөздіктер өзгермелі деректер типтерінің жақсы мысалдары болып табылады.

```python
>>> my_list = [2, 4, 5, 3, 6, 1]
>>> my_list[0] = 9
>>> my_list
[9, 4, 5, 3, 6, 1]
```

Кортеждер мен жолдар өзгермейтін деректер типтерінің мысалдары болып табылады, олар жасалғаннан кейін олардың мазмұнын өзгерту мүмкін емес:

```python
>>> my_tuple = (2, 5, 3, 1)
>>> my_tuple[0] = 9
Traceback (most recent call last):
File "<interactive input>", line 2, in <module>
TypeError: 'tuple' object does not support item assignment
>>>
```

Өзгергіштік әдетте пайдалы, бірақ ол бүркеншік деп аталатын нәрсеге әкелуі мүмкін. Бұл жағдайда екі айнымалы бір нысанға сілтеме жасайды және біреуін мутациялау екіншісін де өзгертеді:

```python
>>> list_one = [1, 2, 3, 4, 6]
>>> list_two = list_one
>>> list_two[-1] = 5
>>> list_one
[1, 2, 3, 4, 5]
```

Бұл орын алады, себебі list_one және list_two екеуі де нақты тізімді қамтитын бір жад мекенжайына сілтеме жасайды. Мұны кірістірілген функция идентификаторы арқылы тексеруге болады:

```python
>>> list_one = [1, 2, 3, 4, 6]
>>> list_two = list_one
>>> id(list_one) == id(list_two)
True
```

Тізімнің көшірмесін жасау арқылы бұл мәселеден құтылуға болады:

```python
>>> list_one = [1, 2, 3, 4, 6]
>>> list_two = list_one[:]
>>> id(list_one) == id(list_two)
False
>>> list_two[-1] = 5
>>> list_two
[1, 2, 3, 4, 5]
>>> list_one
[1, 2, 3, 4, 6]
```

Дегенмен, бұл бірдей себепке байланысты кірістірілген тізімдер үшін жұмыс істемейді. Модуль көшірмесі мұны шешуге арналған функцияларды қамтамасыз етеді.


## 9.2 Жинақтар мен мұздатқыштар

Кортеждер мен тізімдердің реттелгенін, ал сөздіктердің ретсіз екенін ескере отырып, біз келесі кестені құра аламыз.

![pic](https://user-images.githubusercontent.com/84173441/176156811-212c5dc0-82f0-45ee-87bc-c25a7820c5a2.JPG)

Бұл бос орынды көрсетеді: біз әлі ешбір өзгермейтін, ретсіз деректер түрлерін білмейміз. Бұған қоса, сөздік бұл кестеге жатпайды деп дауласуға болады, өйткені ол салыстыру түрі, ал тізімдер мен кортеждер жоқ: сөздік мәндердің кілттерін салыстырады. Жиындар мен мұздатылған жиынтықтар осы жерде енеді. Жиын ретсіз, өзгермелі деректер түрі болып табылады; және мұздатылған жинақ ретсіз, өзгермейтін деректер түрі болып табылады.


Жиындар мен мұздатылған жинақтар ретсіз болғандықтан, олар сөздіктермен кейбір қасиеттерді бөліседі: мысалы, оның элементтері бірегей. Жиын жасау және оған элементтер қосу оңай.

```python
>>> my_set = set([1, 4, 2, 3, 4])
>>> my_set
{1, 2, 3, 4}
>>> my_set.add(13)
>>> my_set
{1, 2, 3, 4, 13}
```

Жоғарыдағы мысалда жиынтықтар сұрыпталған болып көрінуі мүмкін, бірақ бұл мүлдем кездейсоқ. Жиындар мүшелік тестілеу сияқты жалпы әрекеттерді де қолдайды (my_set ішінде 3); және итерация (my_set: ішіндегі x үшін). Сонымен қатар, жиындарды бір-бірінен қосуға және азайтуға болады:

```python
set1 = set([1, 2, 3])
set2 = set([4, 5, 6])
print(set1 | set2) # {1, 2, 3, 4, 5, 6}
print(set1 & set2) # set()
set2 = set([2, 3, 4, 5])
print(set1 & set2) # {2, 3}
print(set1 - set2) # {1}
```

Frozensets негізінен жиынтықпен бірдей, басқасын өзгерту мүмкін емес; яғни элементтерді қосу немесе жою мүмкін емес. Сондай-ақ онлайн құжаттаманы қараңыз.

Кезектер, стектер және реттелген сөздіктер сияқты экзотикалық деректер түрлері Python жинақтар модулінде берілген. Құжаттаманы мына жерден таба аласыз.