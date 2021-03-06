---
## Front matter
title: "Лабораторная работа №6"
subtitle: "Операционные системы"
author: "Миронов Дмитрий Адреевич"

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

Ознакомление с инструментами поиска файлов и фильтрации текстовых данных.
Приобретение практических навыков: по управлению процессами (и заданиями), по
проверке использования диска и обслуживанию файловых систем. 

# Задание


6.3. Последовательность выполнения работы
1. Осуществите вход в систему, используя соответствующее имя пользователя.
2. Запишите в файл file.txt названия файлов, содержащихся в каталоге /etc. Допи-
шите в этот же файл названия файлов, содержащихся в вашем домашнем каталоге.
3. Выведите имена всех файлов из file.txt, имеющих расширение .conf, после чего
запишите их в новый текстовой файл conf.txt.
Кулябов Д. С. и др. Операционные системы 59
4. Определите, какие файлы в вашем домашнем каталоге имеют имена, начинавшиеся
с символа c? Предложите несколько вариантов, как это сделать.
5. Выведите на экран (по странично) имена файлов из каталога /etc, начинающиеся
с символа h.
6. Запустите в фоновом режиме процесс, который будет записывать в файл ~/logfile
файлы, имена которых начинаются с log.
7. Удалите файл ~/logfile.
8. Запустите из консоли в фоновом режиме редактор gedit.
9. Определите идентификатор процесса gedit, используя команду ps, конвейер и фильтр
grep. Как ещё можно определить идентификатор процесса?
10. Прочтите справку (man) команды kill, после чего используйте её для завершения
процесса gedit.
11. Выполните команды df и du, предварительно получив более подробную информацию
об этих командах, с помощью команды man.
12. Воспользовавшись справкой команды find, выведите имена всех директорий, имею-
щихся в вашем домашнем каталоге.

# Выполнение лабораторной работы

1. Осуществите вход в систему, используя соответствующее имя пользователя.

2. Запишите в файл file.txt названия файлов, содержащихся в каталоге /etc. Допи-
шите в этот же файл названия файлов, содержащихся в вашем домашнем каталоге. (рис. [-@fig:001])

![Запись в файл file.txt всего необходимого](/home/damironov1/os-intro/labs/lab06/report/image/1.png){ #fig:001 width=70% }

3. Выведите имена всех файлов из file.txt, имеющих расширение .conf, после чего
запишите их в новый текстовой файл conf.txt.(рис. [-@fig:002])

![Вывод имён всех файлов из file.txt, имеющих расширение .conf](/home/damironov1/os-intro/labs/lab06/report/image/2.png){ #fig:002 width=70% }

4. Определите, какие файлы в вашем домашнем каталоге имеют имена, начинавшиеся
с символа c? Предложите несколько вариантов, как это сделать.(рис. [-@fig:003])

![Определение файлов с именами начинающимися на с](/home/damironov1/os-intro/labs/lab06/report/image/3.png){ #fig:003 width=70% }

5. Выведите на экран (по странично) имена файлов из каталога /etc, начинающиеся
с символа h.(рис. [-@fig:004])

![Вывод на экран файлов из /etc, начинающиеся с h](/home/damironov1/os-intro/labs/lab06/report/image/4.png){ #fig:004 width=70% }

6. Запустите в фоновом режиме процесс, который будет записывать в файл ~/logfile
файлы, имена которых начинаются с log.(рис. [-@fig:005])

![Запуск в фоновом режиме необходимого процесса](/home/damironov1/os-intro/labs/lab06/report/image/5.png){ #fig:005 width=70% }

7. Удалите файл ~/logfile.(рис. [-@fig:006])

![Удаление ~/logfile](/home/damironov1/os-intro/labs/lab06/report/image/6.png){ #fig:006 width=70% }

8. Запустите из консоли в фоновом режиме редактор gedit.
9. Определите идентификатор процесса gedit, используя команду ps, конвейер и фильтр
grep. Как ещё можно определить идентификатор процесса?(рис. [-@fig:007])

![](/home/damironov1/os-intro/labs/lab06/report/image/7.png){ #fig:007 width=70% }

10. Прочтите справку (man) команды kill, после чего используйте её для завершения
процесса gedit.(рис. [-@fig:008])

![Прочли справку команды kill](/home/damironov1/os-intro/labs/lab06/report/image/8.png){ #fig:008 width=70% }

11. Выполните команды df и du, предварительно получив более подробную информацию
об этих командах, с помощью команды man.(рис. [-@fig:009])

![Выполнили команды df и du ](/home/damironov1/os-intro/labs/lab06/report/image/9.png){ #fig:009 width=70% }

12. Воспользовавшись справкой команды find, выведите имена всех директорий, имею-
щихся в вашем домашнем каталоге.(рис. [-@fig:010])

![Вывод имён всех директорий, имеющихся в вашем домашнем каталоге ](/home/damironov1/os-intro/labs/lab06/report/image/10.png){ #fig:010 width=70% }

# Выводы

В ходе лабораторной работы я ознакомился с иструментами поиска файлов и фильтрации текстовых данных. Приобрел практических навыков: по управлению процессами (и заданиями), по
проверке использования диска и обслуживанию файловых систем. Лабораторная работа была выполнена. 

# Контрольные вопросы к лекции

1. Какие потоки ввода вывода вы знаете?
Stdin и stdout, stderr 
2. Объясните разницу между операцией > и >>.
Первый перенаправляет, а второй открывает в режиме добавления. 
3. Что такое конвейер?
Конвейер (pipe) служит для объединения простых команд или утилит в цепочки, в которых
результат работы предыдущей команды передаётся последующей. 
4. Что такое процесс? Чем
это понятие отличается от программы?
Компьютерная программа сама по себе — лишь пассивная последовательность инструкций. В
то время как процесс — непосредственное выполнение этих инструкций. Также, процессом
называют выполняющуюся программу и все её элементы: адресное пространство, глобальные
переменные, регистры, стек, открытые файлы и так далее. 
5. Что такое PID и GID?
PID – это айди процесса.
GID - Группы пользователей применяются для организации доступа нескольких
пользователей к некоторым ресурсам. 
6. Что такое задачи и какая команда позволяет ими
управлять?
Любую выполняющуюся в консоли команду или внешнюю программу можно запустить в фоновом
режиме. Для этого следует в конце имени команды указать знак амперсанда &. Например:
gedit &. 
7. Найдите информацию об утилитах top и htop. Каковы их функции?
Top - отобразить запущенные процессы, используемые ими ресурсы и другую полезную
информацию (с автоматическим обновлением данных)
Htop - показывает динамический список системных процессов, список обычно выравнивается
по использованию ЦПУ. В отличие от top, htop показывает все процессы в системе. Также
показывает время непрерывной работы, использование процессоров и памяти. Htop часто
применяется в тех случаях, когда информации даваемой утилитой top недостаточно,
например при поиске утечек памяти в процессах. 
8. Назовите и дайте характеристику
команде поиска файлов. Приведите примеры использования этой команды.
Команда find используется для поиска и отображения на экран имён файлов,
соответствующих заданной строке символов. Формат команды: find путь [-опции] 
9. Можно ли по контексту (содержанию) найти файл? Если да, то как?
Да, через команду grep. Например: grep Aug -R /var/log/* вывода строки, содержащие
"Aug", во всех файлах, находящихся в директории /var/log и ниже 
10. Как определить объем свободной памяти на жёстком диске?
Для определения объёма свободного пространства на файловой системе можно
воспользоваться командой df, которая выведет на экран список всех файловых систем в
соответствии с именами устройств, с указанием размера и точки монтирования. 
11. Как определить объем вашего домашнего каталога?
Команда du показывает число килобайт, используемое каждым файлом или каталогом. 
12. Как удалить зависший процесс?
Можно удалить через kill, написав id процесса
