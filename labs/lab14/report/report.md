---
## Front matter
title: "Лабораторная работа №14"
subtitle: "Операционные системы"
author: "Миронов Дмитрий Андреевич"

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

Приобретение практических навыков работы с именованными каналами.

# Задание

Изучите приведённые в тексте программы server.c и client.c. Взяв данные примеры
за образец, напишите аналогичные программы, внеся следующие изменения:
1. Работает не 1 клиент, а несколько (например, два).
2. Клиенты передают текущее время с некоторой периодичностью (например, раз в пять
секунд). Используйте функцию sleep() для приостановки работы клиента.
3. Сервер работает не бесконечно, а прекращает работу через некоторое время (напри-
мер, 30 сек). Используйте функцию clock() для определения времени работы сервера.
Что будет в случае, если сервер завершит работу, не закрыв канал?

# Выполнение лабораторной работы

1. Создал необходимые для работы файлы. (рис. [-@fig:001])

![Процесс создания файлов](/home/damironov1/os-intro/labs/lab14/report/image/1.png){ #fig:001 width=70% }

2. Изменил коды программ, показанных в файле лабораторной работы. (рис. [-@fig:002])(рис. [-@fig:003])(рис. [-@fig:004])

![Изменил код common.h](/home/damironov1/os-intro/labs/lab14/report/image/2.png){ #fig:002 width=70% }

![Изменил код server.c](/home/damironov1/os-intro/labs/lab14/report/image/3.png){ #fig:003 width=70% }

![Изменил код client.c](/home/damironov1/os-intro/labs/lab14/report/image/4.png){ #fig:004 width=70% }

Makefile оставил в том виде, в котором он представлен.

3. После написания кодов использовал команду make all.(рис. [-@fig:005])

![Использование make all](/home/damironov1/os-intro/labs/lab14/report/image/5.png){ #fig:005 width=70% }

4. Запустил сервер и проверил его работу. (рис. [-@fig:006])

![Проверка работы сервера](/home/damironov1/os-intro/labs/lab14/report/image/6.png){ #fig:006 width=70% }

Если сервер завершит работу, не закрыв канал,то, когда мы будем запускать его повторно, появится ошибка <<Невозможно создать FIFO>>, так как у нас уже есть один канал.

# Выводы

Задания были выполнены. Практические навыки по работе с именованными каналами были преобретены.


