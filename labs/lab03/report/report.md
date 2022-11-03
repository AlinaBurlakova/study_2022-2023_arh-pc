---
## Front matter
title: "Лабараторная работа №3. Язык разметки Markdown"
subtitle: "Дисциплина: "Архитектура компьютеров""
author: "Бурлакова Алина Андреевна"

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

Целью работы является освоение процедуры офрмления отчетов с помощью легковесного языка разметки Markdown.

# Задание

Составить отчет по выполнению лабараторной работы №3 в Markdown.

# Теоретическое введение

**Базовые сведения о Markdown.**

1) Для того, чтобы создать заголовок в Marcdown,используется знак #.
2) Для того,чтобы задать для текста полужирное начертание, текст заключается в двойные звездочки.
3) Для того, чтобы задать для текста курсивное начертание, текст нужно заключить в одинарные звездочки.
4) Чтобы задать для текста полужирное и курсивное начертание, текст нужно заключить в тройгые звездочки.
5) Блоки цитирования создаются с помощью символа >.
6) Для того, чтобы вложить один список в другой, нужно добавить отступ для элементов дочернего списка.
7) Неупорядоченный (маркированный) список можно отформатировать с помощью звездочек или тире.

**Оформление формул в Markdown**

Внутритекстовые формулы делаются аналогично формулам LaTeX.
 Например, формула sin2(𝑥) + cos2(𝑥) = 1, запишется как:
$\sin^2 (x) + \cos^2 (x) = 1$

**Оформление изображений в Markdown****

В Markdown вставить изображение в документ можно с помощью непосред-
ственного указания адреса изображения. Синтаксис данной команды выглядит
следующим образом:
![Подпись к рисунку](/путь/к/изображению.jpg "Необязательная
подсказка"){ #fig:fig1 width=70% }↪
Таким образом:
• в квадратных скобках указывается подпись к изображению;
• в круглых скобках указывается URL-адрес или относительный путь изоб-
ражения, а также (необязательно) всплывающую подсказку, заключённую
в двойные или одиночные кавычки.
• в фигурных скобках указывается идентификатор изображения (#fig:fig1)
для ссылки на него по тексту и размер изображения относительно ширины
страницы (width=90%).

**Обработка файлов в формате Markdown**

 Преобразовать файл README.md можно следующим образом:
pandoc README.md -o README.pdf или pandoc README.md -o README.docx
 Для компиляции отчетов по лабораторным работам предлагается использо-
вать следующий Makefile
FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
@echo $(FILES)
clean:
-rm $(FILES) *~

# Выполнение лабораторной работы

1. Открываем терминал (рис. [-@fig:001])

!(image/1.jpeg){ #fig:001 width=95%}

2. Перейдем в каталог курса сформированный при выполнении лабораторной работы №3: (рис. [-@fig:002])

!(image/2.jpeg){ #fig:002 width=95%}

3. Обновим локальный репозиторий, скачав изменения из удаленного репозитория с помощью команды git pull (рис. [-@fig:003]) 

!(image/3.jpeg){ #fig:003 width=95%}

4. Перейдем в каталог с шаблоном отчета по лабораторной работе №4 (рис. [-@fig:004]) 

!(image/4.jpeg){ #fig:004 width=95%}

5. Проведем компиляцию шаблона с использованием Makefile. Для этого введем команду make clean (рис. [-@fig:005])

!(image/5.jpeg){ #fig:005 width=95%}

6. (рис. [-@fig:006])

!(image/6.jpeg){ #fig:006 width=95%}

# Выводы

В ходе лабораторной работы я освоила процедуры офрмления отчетов с помощью легковесного языка разметки Markdown.

# Список литературы{.unnumbered}

::: {#refs}
:::
