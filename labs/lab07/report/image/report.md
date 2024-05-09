---
## Front matter
title: "Лабораторная работа № 5"
subtitle: "Дискреционное
разграничение прав в Linux. Исследование
влияния дополнительных атрибутов"
author: "Шулуужук Айраана Вячеславовна НПИбд-02-22"
## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучение механизмов изменения идентификаторов, применения
SetUID- и Sticky-битов. Получение практических навыков работы в кон-
соли с дополнительными атрибутами. Рассмотрение работы механизма
смены идентификатора процессов пользователей, а также влияние бита
Sticky на запись и удаление файлов.

# Выполнение лабораторной работы

Войдем в систему от имени пользователя guest и создадим  программу simpleid.c (рис. @fig:001)

![программа simpleid.c](image/1.png){#fig:001 width=70%}

Скомплилируем программу и убедимся, что файл программы создан: gcc simpleid.c -o simpleid. Выполним программу simpleid: ./simpleid. Выполним системную программу id: id и сравним их вывод (рис. @fig:002)

![программа simpleid.c](image/2.png){#fig:002 width=70%}

Усложним программу, добавив вывод действительных идентификаторов, и сохраним ее  simpleid2.c. (рис. @fig:003)

![программа  simpleid2.c.](image/3.png){#fig:003 width=70%}

Скомпилируем и запустим simpleid2.c: gcc simpleid2.c -o simpleid2 

./simpleid2  (рис. @fig:004)

![запуск программы simpleid2.c.](image/4.png){#fig:004 width=70%}

От имени суперпользователя выполните команды:

chown root:guest /home/guest/simpleid2

chmod u+s /home/guest/simpleid2 

Выполним проверку правильности установки новых атрибутов и смены владельца файла simpleid2: ls -l simpleid2. Запустим simpleid2 и id и сравним результаты (рис. @fig:005) 

![запуск программы simpleid2.c.](image/5.png){#fig:005 width=70%}

Создадим программу readfile.c и откомпилируем ее (рис. @fig:006) 

![программа readfile.c](image/6.png){#fig:006 width=70%}

Выясним, установлен ли атрибут Sticky на директории /tmp, для чего
выполним команду ls -l / | grep tmp. От имени пользователя guest создадим файл file01.txt в директории /tmp
со словом test: echo "test" > /tmp/file01.txt. Просмотрим атрибуты у только что созданного файла и разрешим чтение и запись для категории пользователей «все остальные» (рис. @fig:007) :

ls -l /tmp/file01.txt

chmod o+rw /tmp/file01.txt

ls -l /tmp/file01.txt (рис. @fig:007) 

![файл file01.txt](image/7.png){#fig:007 width=70%}

От пользователя guest2 (не являющегося владельцем) попробуем прочитать файл /tmp/file01.txt:
cat /tmp/file01.txt. От пользователя guest2 попробуем дозаписать в файл /tmp/file01.txt слово test2 командой
echo "test2" > /tmp/file01.txt. В итоге нам не удалось это сделать. Проверим содержимое файла командой
cat /tmp/file01.txt. От пользователя guest2 попробуйте записать в файл /tmp/file01.txt слово test3, стерев при этом всю имеющуюся в файле информацию командой echo "test3" > /tmp/file01.txt. Снова нам не удалось выполнить операцию. Проверьте содержимое файла командой cat /tmp/file01.txt. От пользователя guest2 попробуйте удалить файл /tmp/file01.txt командой rm /tmp/fileOl.txt. Удалить файл не получилось (рис. @fig:008)

![запись и удаление файла file01.txt](image/8.png){#fig:008 width=70%}

Повысим свои права до суперпользователя следующей командой su - и выполним после этого команду, снимающую атрибут t (Sticky-бит) с директории /tmp: chmod -t /tmp. Покинем режим суперпользователя командой exit.
От пользователя guest2 проверим, что атрибута t у директории /tmp нет: ls -l / | grep tmp. После удаления атрибута у нас получилось удалить файл от имени пользователя guest2 (рис. @fig:009)

![удаление атрибута t](image/9.png){#fig:009 width=70%}

Повысим свои права до суперпользователя и верните атрибут t на директорию /tmp:
chmod +t /tmp (рис. @fig:010)

![атрибут t](image/10.png){#fig:010 width=70%}

# Выводы

В ходе выполения лабораторной работы мы изучили механизмы изменения идентификаторов, применения
SetUID- и Sticky-битов. Получили практическе навыкы работы в консоли с дополнительными атрибутами. Рассмотрели работу механизма смены идентификатора процессов пользователей, а также влияние бита Sticky на запись и удаление файлов.
