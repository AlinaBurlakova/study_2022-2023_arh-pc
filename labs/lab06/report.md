---
## Front matter
title: "Отчет по лабораторной работе №6"
subtitle: "Архитектура компьютера"
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

Освоение арифметических инструкций языка ассемблера NASM.

# Задание

Получить навыки в работе с ассемблером NASM.


# Выполнение лабораторной работы

1. Создадим каталог для программам лабораторной работы No 6, перейдем в него и создадим файл lab7-1.asm (рис. [-fig:001])

![Создание файла](image/1.png){ #fig:001 width=70% }

2. Введем в файл lab6-1.asm текст программы из листинга 6.1 (рис. [-fig:002])

![введение текста в файл](image/2.png){ #fig:002 width=70% }

3. Создадим исполняемый файл и запустим его. (рис. [-fig:003])

![Запуск файла](image/3.png){ #fig:003 width=70% }

4. Далее изменим текст программы и вместо символов, запишем в регистры числа. (рис. [-fig:004])

![Изменение текста](image/4.png){ #fig:004 width=70% }

5. Создадим исполняемый файл и запустим его. (рис. [-fig:005])

![Запуск файла](image/5.png){ #fig:005 width=70% }

6. Создадим файл lab6-2.asm в каталоге ~/work/arch-pc/lab06 и введем в него
текст программы из листинга 7.2. (рис. [-fig:006])

![Создание файла](image/6.png){ #fig:006 width=70% }

7. Введем в файл lab7-2.asm текст программы из листинга 6.2. (рис. [-fig:007])

![Ввод текста](image/7.png){ #fig:007 width=70% }

8. Создадим исполняемый файл и запустим его. (рис. [-fig:008])

![Запуск файла](image/8.png){ #fig:008 width=70% }

9. Изменим символы на числа в файле. (рис. [-fig:009])

![Изменение](image/9.png){ #fig:009 width=70% }

10. Создадим исполняемый файл и запустим его. (рис. [-fig:010])

![Запуск файла](image/10.png){ #fig:010 width=70% }

11. Создайте файл lab6-3.asm в каталоге ~/work/arch-pc/lab07. (рис. [-fig:011])

![Создание файла](image/11.png){ #fig:011 width=70% }

12. Введем текст программы из листинга 6.3 в lab6-3.asm и запустим его. (рис. [-fig:012])

![Ввод текста](image/12.png){ #fig:012 width=70% }

13. Создадим файл variant.asm в каталоге ~/work/arch-pc/lab06 (рис. [-fig:013])

![Создание файла](image/13.png){ #fig:013 width=70% }

14. Текст программы из листинга 6.4 введем в файл variant.asm. (рис. [-fig:014])

![Ввод текста](image/14.png){ #fig:014 width=70% }

15. Ответы на вопросы.

1) Какие строки листинга 7.4 отвечают за вывод на экран сообщения ‘Ваш
  вариант:’?
  
  mov eax,rem call sprint
  
  2) Для чего используется следующие инструкции? nasm mov ecx, x
  mov edx, 80 call sread
  
  mov ecx, x - запись входной переменной в регистр ecx;
  mov edx, 80 - запись размера перемнной в регистр edx; call
  sread - вызов процедуры чтония данных;
  
  3) Для чего используется инструкция “call atoi”?
  
  Вызов atoi – функции преобразующей ascii-код символа в целое число
  и записывающий результат в регистр eax.
  
  4) Какие строки листинга 7.4 отвечают за вычисления варианта?
  
  xor edx,edx mov ebx,20 div ebx inc edx
  
  5) В какой регистр записывается остаток от деления при выполнении ин-
  струкции “div ebx”?
  
  В регистр ebx.
  
  6) Для чего используется инструкция “inc edx”?
  
  Инструкция INC используется для увеличения операнда на единицу.
  
  7) Какие строки листинга 7.4 отвечают за вывод на экран результата вычис-
  лений?
  
  mov eax,rem call sprint mov eax,edx call iprintLF



# Выводы

Во время выполнения лабораторной работы я освоила арифметические инструкции языка ассемблера NASM.

# Список литературы{.unnumbered}

::: {#refs}
:::
