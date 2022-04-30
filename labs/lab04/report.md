---
## Front matter
title: "Лабораторная работа №4"
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

Приобретение практических навыков взаимодействия пользователя с системой по-
средством командной строки.

# Задание

1. Определите полное имя вашего домашнего каталога.Далее относительно этого ката-
лога будут выполняться последующие упражнения.
2. Выполните следующие действия:
2.1. Перейдите в каталог /tmp.
2.2. Выведите на экран содержимое каталога /tmp.Для этого используйте команду ls
с различными опциями.Поясните разницу в выводимой на экран информации.
2.3. Определите,естьли в каталоге /var/spool подкаталог с именем cron?
2.4. Перейдите в Ваш домашний каталог и выведите на экран его содержимое.Опре-
делите,кто является владельцем файлов и подкаталогов?
3. Выполните следующие действия:
3.1. В домашнем каталоге создайте новый каталог с именем newdir.
3.2. В каталоге ~/newdir создайте новый каталог с именем morefun.
3.3. В домашнем каталоге создайте одной командойтри новых каталога с именами
letters,memos,misk.Затем удалите эти каталоги одной командой.
3.4. Попробуйте удалить ранее созданный каталог ~/newdir командой rm.Проверьте,
был ли каталог удалён.
3.5. Удалите каталог ~/newdir/morefun из домашнего каталога.Проверьте,был ли
каталогудалён.
4. С помощью команды man определите, какую опцию команды ls нужно использо-
ватьдля просмотра содержимое нетолько указанного каталога,но и подкаталогов,
входящих в него.
5. Спомощьюкомандыman определитенаборопцийкомандыls,позволяющийотсорти-
ровать по времени последнего изменения выводимый список содержимого каталога
с развёрнутым описанием файлов.
6. Используйте команду man для просмотра описания следующих команд: cd,pwd,mkdir,
rmdir,rm.Поясните основные опции этих команд.
7. Используя информацию,полученную при помощи команды history,выполните мо-
дификацию и исполнение нескольких команд из буфера команд.

# Теоретическое введение

В операционной системетипа Linux взаимодействие пользователя с системой обычно
осуществляется с помощью командной строки посредством построчного ввода ко-
манд.При этом обычно используется командные интерпретаторы языка shell: /bin/sh;
/bin/csh; /bin/ksh.

# Выполнение лабораторной работы
Определите полное имя вашего домашнего каталога
Определение полного имени домашнего каталога (рис. [-@fig:001])

![Определение полного имени домашнего каталога](/home/damironov1/os-intro/labs/lab04/report/image/1.jpg){ #fig:001 width=70% }
Перейдите в каталог /tmp. Выведите на экран содержимое каталога /tmp.Для этого используйте команду ls с различными опциями.Поясните разницу в выводимой на экран информации. 
(рис. [-@fig:002]) (рис. [-@fig:003]) (рис. [-@fig:004]) 
![Вывод на экран с помощью команды ls без опций](/home/damironov1/os-intro/labs/lab04/report/image/2.jpg){ #fig:002 width=70% }
![Вывод на экран с помощью команды ls -а](/home/damironov1/os-intro/labs/lab04/report/image/3.png){ #fig:003 width=70% }
![Вывод на экран с помощью команды ls -l](/home/damironov1/os-intro/labs/lab04/report/image/4.png){ #fig:004 width=70% }
Определите,есть ли в каталоге /var/spool подкаталог с именем cron и кто является владельцем файлов и подкаталогов в домашнем каталоге 
(рис. [-@fig:005])
![Опредиление есть ли в каталоге /var/spool подкаталог с именем cron и кто является владельцем файлов и подкаталогов в домашнем каталоге](/home/damironov1/os-intro/labs/lab04/report/image/5.png){ #fig:005 width=70% }
Выполнение третьего пункта задания (рис. [-@fig:006])
![Последовательное выполнение подпунктов задания 3](/home/damironov1/os-intro/labs/lab04/report/image/6.png){ #fig:006 width=70% }
С помощью команды man определите набор опций командыls,позволяющий отсортировать по времени последнего изменения выводимый список содержимого каталога с развёрнутым описанием файлов.(рис. [-@fig:007])
![Определение нужной опции для команды ls ](/home/damironov1/os-intro/labs/lab04/report/image/7.png){ #fig:007 width=70% }

Скриншоты для оставшихся двух заданий слишком большие и их достаточно много поэтому их лучше посмотреть в видео.
# Выводы
Цель лабораторной работы была достигнута, команды и опции для них были изучены и пременены на практике.



