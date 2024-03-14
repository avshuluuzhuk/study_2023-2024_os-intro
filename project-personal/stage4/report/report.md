---
## Front matter
title: "Индивидуальный проект. 4 этап"
subtitle: Операционные системы
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

Добавить к сайту ссылки на научные и библиометрические ресурсы.

# Задание

1. арегистрироваться на соответствующих ресурсах и разместить на них ссылки на сайте

2. Сделать пост по прошедшей неделе.

3. Добавить пост на тему по выбору:

    - Оформление отчёта.
    - Создание презентаций.
    - Работа с библиографией.

# Выполнение индивидуального проекта 

В каталоге content в файле index.md добавим ссылки на ресурсы Youtube и GitHub(рис. @fig:001) (рис. @fig:002)

![добавление ссылок](image/1.png){#fig:001 width=70%}

![результат](image/2.png){#fig:002 width=70%}

Добавим пост по прошедшей неделе (рис. @fig:003) (рис. @fig:004).

![редактирование поста My last week](image/3.png){#fig:003 width=70%}

![результат](image/4.png){#fig:004 width=70%}

Создадим пост по теме "Оформление отчета на Markdown" (рис. @fig:005) (рис. @fig:006)

![редактирование поста](image/5.png){#fig:005 width=70%}

![результат](image/6.png){#fig:006 width=70%}

# Выводы

В ходе выполнения 4 этапа индивидуального проекта мы добавили ссылки на ресурсы вдалельца сайта. Также сделали пост по прошедшей неделе и пост по теме "Оформление отчета на Markdown" 

