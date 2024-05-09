---
## Front matter
lang: ru-RU
title: Индивидуальный проект. 3 этап
subtitle: Использование Hydra
author:
  - Шулуужук Айраана Вячеславовна, НПИбд-02-22
institute:
  - Российский университет дружбы народов, Москва, Россия
 
date: 16 марта 2024

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
---

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Шулуужук Айраана Вячеславовна 
  * НПИбд-02-22
  * 1132221890
  * Российский университет дружбы народов

:::
::: {.column width="30%"}

:::
::::::::::::::

# Цели и задачи

Установить DVWA в гостевую систему к Kali Linux.

# Выполнение индивидуального проекта

## Выполнение индивидуального проекта

Клонируем репозиторий

![клонирование репозитория](image/1.png){#fig:001 width=70%}

## Выполнение индивидуального проекта

Загружаем скрипт, используя команду: wget https://raw.githubusercontent.com/IamCarron/DVWA-Script/main/Install-DVWA.sh

![загрузка скрипта](image/2.png){#fig:002 width=70%}

## Выполнение индивидуального проекта

Сделаем скрипт испольняемым и запустим его 

![установка](image/3.png){#fig:003 width=40%}

## Выполнение индивидуального проекта

Устанавливаем Docker

![установка Docker](image/4.png){#fig:004 width=70%}

## Выполнение индивидуального проекта

После установки Docker просмотрим его версию

![версия Docker](image/6.png){#fig:006 width=70%}

## Выполнение индивидуального проекта

В терминале перейдем в папку/каталог DVWA и проведем команду docker compose up -d. После переходим на локальную страницу database.setup

![локальная страница database setup](image/8.png){#fig:008 width=40%}

## Выполнение индивидуального проекта

Создадим базу данных и в качестве имени пользователя и пароля используем admin/password

![регистрация для DVWA](image/9.png){#fig:009 width=40%}

## Выполнение индивидуального проекта

DVWA установлен

![переход на локальную страницу DVWA](image/10.png){#fig:010 width=40%}

# Выводы

В ходе выполнения 2 этапа индивидуального проекта мы установили DVWA в гостевую систему к Kali Linux.

