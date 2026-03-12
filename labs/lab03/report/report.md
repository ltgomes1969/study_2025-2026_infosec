---
## Front matter
title: "Отчёта по лабораторной работе 3"
subtitle: "Дискреционное разграничение прав в Linux."
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

Получить практические навыки работы в консоли с атрибутами файлов дя групп пользоватей.

# Задание

1. Создать пользователя guest2 и добавить его в группу пользователей.
2. Заполнить таблицы.

# Выполнение лабораторной работы

Так как пользователь guest уже есть, я создаю guest2 и задаю ему пароль.

![Создание guest2](image/1.png){#fig:001 width=70%}

Добавляю guest2 в группу guest:

![Добавление в группу](image/2.png){#fig:002 width=70%}

Использую команду su, чтобы войти в систему от имени guest на одной консоли и от имени guest2 — на другой.

![вход в guest](image/3.png){#fig:003 width=70%}

![окна guest и guest2](image/4.png){#fig:004 width=70%}

С помощью команды pwd определяю своё текущее местоположение.

![Комманда pwd](image/5.png){#fig:005 width=70%}

Текущая директория, выведенная командой pwd, совпадает с приглашением командной строки.

![Комманда pwd](image/6.png){#fig:006 width=70%}

С помощью whoami проверяю имя пользователя. id показывает группы и их gid.groups выводит список групп.
id -Gn — названия групп.
id -G — только коды групп.

![Проверка](image/7.png){#fig:007 width=70%}

![Проверка](image/8.png){#fig:008 width=70%}

Вывела интересующее меня содержимое файла etc/group, видно, что в группе guest два пользователя, а в группе guest2 один:

![содержиемое etc/group](image/9.png){#fig:009 width=70%}

![содержиемое etc/group](image/10.png){#fig:0010 width=70%}

Использую команду newgrp guest, чтобы зарегистрировать пользователя guest2 в группе guest.

![создание новой группы](image/11.png){#fig:011 width=70%}

Далее добавляю права на читение, запись и исполнение пользователей группы guest:

![вход в /home/guest](image/12.png){#fig:012 width=70%}

![Изменение права доступа](image/13.png){#fig:013 width=70%}

Снимаю все атрибуты с dir1 (созданной в предыдущей работе) и проверяю, что права действительно сняты.

![Проверка изменения](image/14.png){#fig:014 width=70%}

Затем от имени guest2 проверяю доступ к файлам в dir1 и на основе результатов заполняю таблицы.

![Проверка атрибутов](image/15.png){#fig:0015 width=70%}



## Заполнение таблицы

| Права директории | Права файла | Создание файла | Удаление файла | Запись в файл | Чтение файла | Смена директории | Просмотр файлов в директории | Переименование файла | Смена атрибутов файла |
|------------------|-------------|----------------|----------------|---------------|--------------|------------------|------------------------------|----------------------|-----------------------|
| d (000) | (000) | - | - | - | - | - | - | - | - |
| d--x (010) | (000) | - | - | - | - | + | - | - | + |
| d-w- (020) | (000) | - | - | - | - | - | - | - | - |
| d-wx (030) | (000) | + | + | - | - | + | - | + | + |
| d-r- (040) | (000) | - | - | - | - | - | - | - | - |
| d-rx (050) | (000) | - | - | - | - | + | + | - | + |
| d-rw (060) | (000) | - | - | - | - | - | - | - | - |
| d-rwx (070) | (000) | + | + | - | - | + | + | + | + |
| d--x (010) | r-- (040) | - | - | - | + | + | - | - | - |
| d--x (010) | -w- (020) | - | - | + | - | + | - | - | - |
| d--x (010) | -wx (030) | - | - | + | - | + | - | - | - |
| d--x (010) | r-x (050) | - | - | - | + | + | - | - | - |
| d--x (010) | rw- (060) | - | - | + | + | + | - | - | - |
| d--x (010) | rwx (070) | - | - | + | + | + | - | - | - |
| d-rx (050) | r-- (040) | - | - | - | + | + | + | - | - |
| d-rwx (070) | r-- (040) | - | - | - | + | + | + | - | - |
| d-rwx (070) | -w- (020) | - | - | + | - | + | + | - | - |
| - | - | - | - | - | - | - | - |


Таблица 3.1 «Установленные права и разрешенные действия для групп»


| Операция | Минимальные права на директорию | Минимальные права на файл |
|----------|---------------------------------|---------------------------|
| Создание файла | -wx (030) | не применяется |
| Удаление файла | -wx (030) | не применяется |
| Чтение файла | --x (010) | r-- (040) |
| Запись в файл | --x (010) | -w- (020) |
| Переименование файла | -wx (030) | не применяется |
| Создание поддиректории | -wx (030) | не применяется |
| Удаление поддиректории | -wx (030) | не применяется |


Таблица 3.2 «Минимальные права для совершения операций от имени пользователей входящих в группу»


# Выводы

В результате работы я получила навыки работы в консоли с атрибутами файлов.


