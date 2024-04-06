---
## Front matter
title: "Индивидуальный проект. 3 этап"
subtitle: "Использование Hydra"
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

Установить DVWA в гостевую систему к Kali Linux.

# Выполнение индивидуального проекта 

Клонируем репозиторий (рис. @fig:001)

![клонирование репозитория](image/1.png){#fig:001 width=70%}

Загружаем скрмп, используя команду: wget https://raw.githubusercontent.com/IamCarron/DVWA-Script/main/Install-DVWA.sh   (рис. @fig:002)

![загрузка скрипта](image/2.png){#fig:002 width=70%}

Сделаем скрипт испольняемым и запустим его (рис. @fig:003) 

![установка](image/3.png){#fig:003 width=70%}

Устанавливаем Docker (рис. @fig:004), (рис. @fig:005)

![установка Docker](image/4.png){#fig:004 width=70%}

![установка Docker](image/5.png){#fig:005 width=70%}

После установки Docker просмотрим его версию (рис. @fig:006)  (рис. @fig:007)

![версия Docker](image/6.png){#fig:006 width=70%}

![версия Docker](image/7.png){#fig:007 width=70%}

В терминале перейдем в папку/каталог DVWA и проведем команду docker compose up -d. После переходим на локальную страницу database.setup (рис. @fig:008)

![локальная страница database setup](image/8.png){#fig:008 width=70%}

Создадим базу данных и в качестве имени пользователя и пароля используем admin/password (рис. @fig:009)

![регистрация для DVWA](image/9.png){#fig:009 width=70%}

DVWA установлен (рис. @fig:010)

![переход на локальную страницу DVWA](image/10.png){#fig:010 width=70%}

# Выводы

В ходе выполнения 2 этапа индивидуального проекта мы установили DVWA в гостевую систему к Kali Linux.

