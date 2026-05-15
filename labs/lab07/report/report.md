---
## Front matter
title: "Отчёт по лабораторной работе 7"
subtitle: "Режим Однократного Гарммирования"
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

Освоить применение режима однократного гаммирования.

# Выполнение лабораторной работы

Я написала на Python функцию, которая создаёт случайный ключ.

![Функция для генерации ключа](image/1.png){#fig:001 width=70%}

У меня получилась одна функция, которая умеет как зашифровывать, так и расшифровывать текст.

![Функция для шифрования и дешифрования](image/2.png){#fig:002 width=70%}

Необходимо найти ключ, при котором шифротекст превращается в фрагмент текста. Для этого создала функцию поиска возможных ключей по фрагменту.

![функция для нахождения возможных ключей](image/3.png){#fig:003 width=70%}

Проверила работу программы: шифрование и дешифрование выполняются верно, ключи для расшифровки фрагмента текста также находятся правильно.

![Проверка](image/4.png){#fig:004 width=70%}

# Выводы

Выполняя эту работу, я научилась использовать режим однократного гаммирования.
