---
## Front matter
title: "Отчёт по индивидуальному проекту этап 3"
subtitle: "HYDRA"
author: "Гомес Лопес Теофания"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Цель работы — получить практические навыки использования Hydra для подбора паролей (брутфорса).

# Задание

Реализовать атаку на уязвимость, используя брутфорс (подбор паролей).

# Выполнение лабораторной работы

Перед началом работы я подготовила список часто встречающихся паролей. Проверяю, что список на месте, и продолжаю работу.

![Загружаю список паролей.](image/1.png){#fig:001 width=70%}

Затем вхожу в аккаунт DVWA, который создала в предыдущей работе, и перехожу в раздел Brute Force.

![DVWA — домашняя страница](image/2.png){#fig:002 width=70%}

Использую команду man, чтобы изучить справку Hydra и разобраться в её работе. Для выполнения задачи мне нужны опции -l (указывает логин) и -p (указывает пароль).

![информация по hydra](image/3.png){#fig:003 width=70%}

Выполняю подбор пароля для пользователя admin с помощью файла rockyou.txt. Использую GET-запрос, передавая параметры cookie и PHPSESSID. При указании опции -P программа показывает подобранный пароль и путь к файлу со списком паролей (home/mwakutaipa/rockyou.txt)

![пароль](image/4.png){#fig:004 width=70%}

Использую найденный пароль для входа в систему, чтобы убедиться, что пароль верный.

![Проверка](image/5.png){#fig:005 width=70%}

# Выводы

В результате выполнения работы я получила практические навыки использования Hydra для подбора паролей (брутфорса).


