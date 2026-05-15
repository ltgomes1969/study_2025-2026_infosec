---
## Front matter
lang: ru-RU
title: Структура по индивидуальному проекту этап 5
subtitle: Burp Suite
author:
  - Гомес Лопес Теофания
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 05 2026

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
---

# Цель работы

Научиться использовть Burp Suite.

# Выполнение лабораторной работы

## Запуск сервера

Запускаю локальный серевер DVWA: 

![Запуск сервера](image/1.png){#fig:001 width=70%}

## Запуск Burp suite

Запускаю burp suite:

![Запуск Burp suite](image/2.png){#fig:002 width=70%}

## сетевые настройки сервера

Я захожу в сетевые настройки браузера и настраиваю прокси-сервер так, чтобы браузер работал через Burp Suite — это позволит перехватывать данные.

![сетевые настройки сервера](image/3.png){#fig:003 width=70%}

## настройки proxy

В Burp Suite я меняю параметры прокси.

![настройки proxy](image/4.png){#fig:004 width=70%}

## Включение intercept

Включаю intercept во вкладе proxy:

![Включение intercept](image/5.png){#fig:005 width=70%}

## Установка параметра локального хоста

Чтобы Burp Suite работал с локальным сервером, требуется изменить параметр network_allow_hijacking_localhost на true. Я выполнила эту настройку.

![Установка параметра локального хоста](image/6.png){#fig:006 width=70%}

## вкладка proxy

вкладка proxy

![вкладка proxy](image/7.png){#fig:007 width=70%}

## окно dvwa

![окно dvwa](image/8.png){#fig:008 width=70%}

## Измененные данные

При вводе неверных логина и пароля в запросе отображаются введённые данные. Я отправила этот запрос в Intruder (send to intruder) через вкладку Target. Во вкладке Intruder изменила тип атаки на Cluster Bomb и данные для входа.

![Измененные данные](image/9.png){#fig:009 width=70%}

## Тип атака

![Тип атака](image/10.png){#fig:010 width=70%}

## Список 1

Отметила два параметра для подбора, поэтому создала два списка со значениями для подбора в payload:

![Список 1](image/11.png){#fig:011 width=70%}

## Список 2

![Список 2](image/12.png){#fig:012 width=70%}

## Правильная пара

Запускаю атаку и начинаю подбор. При открытии POST-запроса виден GET-запрос — туда перенаправило после ввода пары. 

![Правильная пара](image/13.png){#fig:013 width=70%}

## Полученная страница

В подокне Render получаю то, как выглядит полученная страница:

![Полученная страница](image/14.png){#fig:0144 width=70%}


# Выводы

Научилась использовать Burp Suite.



