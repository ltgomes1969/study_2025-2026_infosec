---
## Front matter
title: "Отчёт по индивидуальному проекту этап 5"
subtitle: "Burp Suite"
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

Научиться использовть Burp Suite.

# Выполнение лабораторной работы

Запускаю локальный серевер DVWA: 

![Запуск сервера](image/1.png){#fig:001 width=70%}

Запускаю burp suite:

![Запуск Burp suite](image/2.png){#fig:002 width=70%}

Я захожу в сетевые настройки браузера и настраиваю прокси-сервер так, чтобы браузер работал через Burp Suite — это позволит перехватывать данные.

![сетевые настройки сервера](image/3.png){#fig:003 width=70%}

В Burp Suite я меняю параметры прокси.

![настройки proxy](image/4.png){#fig:004 width=70%}

Включаю intercept во вкладе proxy:

![Включение intercept](image/5.png){#fig:005 width=70%}

Чтобы Burp Suite работал с локальным сервером, требуется изменить параметр network_allow_hijacking_localhost на true. Я выполнила эту настройку.

![Установка параметра локального хоста](image/6.png){#fig:006 width=70%}

вкладка proxy

![вкладка proxy](image/7.png){#fig:007 width=70%}

![окно dvwa](image/8.png){#fig:008 width=70%}

При вводе неверных логина и пароля в запросе отображаются введённые данные. Я отправила этот запрос в Intruder (send to intruder) через вкладку Target. Во вкладке Intruder изменила тип атаки на Cluster Bomb и данные для входа.

![Измененные данные](image/9.png){#fig:009 width=70%}

![Тип атака](image/10.png){#fig:010 width=70%}

Отметила два параметра для подбора, поэтому создала два списка со значениями для подбора в payload:

![Список 1](image/11.png){#fig:011 width=70%}

![Список 2](image/12.png){#fig:012 width=70%}

Запускаю атаку и начинаю подбор. При открытии POST-запроса виден GET-запрос — туда перенаправило после ввода пары. 

![Правильная пара](image/13.png){#fig:013 width=70%}

В подокне Render получаю то, как выглядит полученная страница:

![Полученная страница](image/14.png){#fig:0144 width=70%}


# Выводы

Научилась использовать Burp Suite.



