---
## Front matter
title: "Отчёт по лабораторной работе №2"
subtitle: "*Дисциплина: Архитерктура компьютера*"
author: "Долгаев Евгений Сергеевич НММбд-01-24"

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

Цель работы — исследовать концепции и использование систем контроля
версий, а также приобрести практические навыки работы с git.

# Задание

1) Техническое обеспечение
	1) Настройка github
	2) Базовая настройка git
	3) Создания SSH ключа
	4) Создание рабочего пространства и репозитория курса на основе шаблона
	5) Создание репозитория курса на основе шаблона
	6) Настройка каталога курса
2) Задание для самостоятельной работы

# Теоретическое введение

Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. [-@tbl:std-dir] приведено краткое описание стандартных каталогов Unix.

: Описание некоторых каталогов файловой системы GNU Linux {#tbl:std-dir}

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

Более подробно про Unix см. в [@tanenbaum_book_modern-os_ru; @robbins_book_bash_en; @zarrelli_book_mastering-bash_en; @newham_book_learning-bash_en].

# Выполнение лабораторной работы

Для начала создадим учётную запись на сайте https://github.com/ и заполним основные данные (рис. [-@fig:001]).

![Учётная запись на сайте https://github.com](image/1.png){#fig:001 width=70%}

Сначала сделаем предварительную конфигурацию git, указав имя и email владельца репозитория (рис. [-@fig:002]).

![Параметры user.name и user.email](image/2.png){#fig:002 width=70%}

Настроим utf-8 в выводе сообщений git, зададим имя начальной ветке(будем называть её master), укажем значение параметров autocrlf и safecrlf (рис. [-@fig:003]).

![Настройка utf-8 вывода, имени ветки и параметров autocrlf и safecrlf](image/3.png){#fig:003 width=70%}

Для последующей идентификации пользователя на сервере репозиториев сгенерируем пару ключей(приватный и открытый (рис. [-@fig:004]).

![Создание SSH ключа](image/4.png){#fig:004 width=70%}

Далее загрузим сгенерированный открытый ключ на Github, предварительно скопировав его в буфер обмена (рис. [-@fig:005], [-@fig:006]).

![Копирование ключа в буфер обмена](image/5.png){#fig:005 width=70%}

![Загрузка ключа на Github](image/6.png){#fig:006 width=70%}

Создадим каталог для предмета «Архитектура компьютера" для последующего создания рабочего пространства (рис. [-@fig:007]).

![Создание каталога для предмета «Архитектура компьютера»](image/7.png){#fig:007 width=70%}

Через web-интерфейс github создадим репозиторий на основе шаблона, указав имя study_2024–2025_arh-рс (рис. [-@fig:008]).

![Создание репозитория](image/8.png){#fig:008 width=70%}

Перейдем в каталог курса и скопируем в него созданный репозиторий с помощью ссылки для клонирования (рис. [-@fig:009], [-@fig:010]).

![Ссылка для клонирования](image/9.png){#fig:009 width=70%}

![Клонирование репозитория](image/10.png){#fig:010 width=70%}

Перейдём в каталог курса, удалим лишние файлы, создадим нужные каталоги и загрузим файлы на сервер (рис. [-@fig:011], [-@fig:012], [-@fig:013], [-@fig:014]).

![Удаление лишних файлов](image/11.png){#fig:011 width=70%}

![Создание нужных каталогов](image/12.png){#fig:012 width=70%}

![Загрузка файлов на сервер](image/13.png){#fig:013 width=70%}

![Загрузка файлов на сервер(2)](image/14.png){#fig:014 width=70%}

Проверим правильность введённых команд (рис. [-@fig:015]).

![Проверка](image/15.png){#fig:015 width=70%}

Приступим к выполнению заданий для самостоятельной работы. Скопируем отчёты по выполнению прошлых лабораторных работ и сохраним отчет по выполнению данной лабораторной работы в соответствующих каталогах рабочего пространства (рис. [@fig:016]).

![Копирование прошлых отчётов](image/16.png){#fig:016 width=70%}

# Выводы

В ходе выполнения этой я исследовал концепции и познакомился с использованием систем контроля версий, а также приобрёл практические навыки работы с git.

# Список литературы{.unnumbered}

::: {#refs}
:::
