---
## Front matter
title: "Лабораторная работа № 4"
subtitle: "Дискреционное разграничение прав в Linux. Расширенные атрибуты"
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

Получение практических навыков работы в консоли с расширенными атрибутами файлов.

# Выполнение лабораторной работы

От имени пользователя guest определим расширенные атрибуты файла /home/guest/dir1/file1 командой lsattr /home/guest/dir1/file1. Установим командой chmod 600 file1 на файл file1 права, разрешающие чтение и запись для владельца файла.

Попробуем установить на файл /home/guest/dir1/file1 расширенный атрибут a от имени пользователя guest:
chattr +a /home/guest/dir1/file1. В итоге у нас это не получается сделать (рис. @fig:001)

![установка на файл /home/guest/dir1/file1 расширенного атрибута](image/1.png){#fig:001 width=70%}

Переходм в терминал с правами администратора и от имени суперпользователя попробуем установить расширенный атрибут a на файл /home/guest/dir1/file1: chattr +a /home/guest/dir1/file1. В итоге получается это сделать (рис. @fig:002)

![установка на файл /home/guest/dir1/file1 расширенного атрибута](image/2.png){#fig:002 width=70%}

От пользователя guest проверим правильность установления атрибута: lsattr /home/guest/dir1/file1. Выполним дозапись в файл file1 слова «test» командой echo "test" /home/guest/dir1/file1. После этого выполним чтение файла file1 командой cat /home/guest/dir1/file1. Видим, что test было успешно записано в file1. (рис. @fig:003)

![запись файла file1](image/3.png){#fig:003 width=70%}

Попробуем удалить файл file1 либо стереть имеющуюся в нём информацию командой
echo "abcd" > /home/guest/dirl/file1 и установить на файл file1 права запрещающие чтение и запись для владельца файла chmod 000 file1. Видим, что у нас это не получается сделать, так как действует расширенный атрибут на файл (рис. @fig:004)

![удаление и изменение прав доступа к файлу](image/4.png){#fig:004 width=70%}

Под именем суперпользователя уберем расширенный атрибут a с файла /home/guest/dirl/file1 командой
chattr -a /home/guest/dir1/file1. Далее повторим операции, которые ранее не удавалось выполнить. После удаления расширенного абрибута у нас получилось изменить права доступа к файлу от имени пользователя guest (рис. @fig:005)

![удаление и изменение прав доступа к файлу](image/5.png){#fig:005 width=70%}

От имени суперпользователя добавим атрибут i к файлу file1 и попробуем провести команды, выполняемые ранее (рис. @fig:006). 

![добавление атрибута i](image/6.png){#fig:006 width=70%}

# Выводы

В ходе выполнения лабораторной работы были приобретены практические навыки работы в консоли с расширенными
атрибутами файлов.
