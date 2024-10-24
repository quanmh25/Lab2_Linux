﻿# <a name="_hlk180669145"></a>Лабораторная работа №2
# Работа с командной оболочкой bash в ОС семейства Linux



Командная оболочка (shell) предназначена для того, чтобы обеспечивать взаимодействие пользователя и ОС через командную строку. В разных дистрибутивах ОС семейства Linux могут применяться разные командные оболочки. Видов командных оболочек, конечно, несравнимо меньше, чем количество видов дистрибутивов Linux, однако с большой долей вероятности, на самых популярных дистрибутивах вам попадется оболочка bash.

В отличии от графического интерфейса, командная оболочка это универсальный способ взаимодействия с Linux-системами. Более того, командная оболочка дает самые широкие возможности по настройке, управлению ОС, а также выполнению рутинных задач.

Доступ к командной оболочке осуществляется через виртуальные терминалы, либо через эмулятор терминала. В данной работе мы будем работать с эмулятором терминала и для краткости в дальнейшем будем называть его просто «терминал».

Терминал работает по принципу REPL (Read-Eval-Print-Loop). Фактически взаимодействие с пользователем осуществляется по следующему сценарию:

1) Read — шелл ждёт ввода команды от пользователя
1) Eval — шелл исполняет введённую команду
1) Print — шелл выводит результат
1) Loop — возвращаемся к первому пункту

*Полезные ссылки:*

- Поучительная притча <https://www.livelib.ru/quote/61563-iskusstvo-programmirovaniya-dlya-unix-erik-c-rejmond>
- Для тех, кто хочет глубже разобраться с терминалами <https://habr.com/ru/company/neobit/blog/330764/> 
- Удобный сайт, объясняющий введенную команду <https://explainshell.com/> 


*Важно*

Далее по тексту: где указываются команды, которые необходимо вводить в терминал, знак **$** вводить не нужно. Этим знаком обозначается обычное приглашение консоли.

*Требования к отчету*

Сопроводите свою работу несколькими скриншотами. Весь процесс фиксировать картинками не нужно. В отчете ответьте на вопросы, которые задаются по ходу работы, а также добавьте требуемые данные (например, содержимое секретного файла). К отчету приложите файл record\_result. Это текстовый файл с вашими командами.



## Ход работы

*Подготовка*

1. Запустите виртуальную машину и дождитесь загрузки ОС. 
1. Откройте терминал. Это можно сделать с помощью основного меню или сочетанием клавиш **Ctrl+Alt+T**. Для запуска через основное меню нажмите на  Menu->System Tools->Mate Terminal (см. Рисунок 1). 
<p align="center">
  <img src="pattern_1.png" width="480" title="Pattern_1">
</p>

Рисунок 1 Открытие терминала через графический интерфейс

1. **Запустите запись терминала.**  **Это важно!**  Именно файл с записью истории ваших команд будет основной частью отчета. Для этого введите и запустите команду 

   $ script -a record\_result

1. Убедитесь, что команда выполнилась без ошибок. Введите нижеуказанную команду и найдите имя файла record\_result** в ее выводе:

   $ ls -l


*Навигация*

1. Поместите на рабочий стол файл lab2.py, прилагаемый к этому руководству. 
1. Вернитесь в терминал, в котором уже идет запись (см. Подготовка). 
1. Выведите путь текущей рабочей директории. Для этого:

   $ pwd

1. Выведите список всех файлов и каталогов в этой директории.  Для этого введите:

   $ ls -l

1. Перейдите на рабочий стол. Для этого:

   $ cd ./Desktop

   в случае с русским языком нужно использовать экранирование пробела

   $ cd ./Рабочий\ стол/

1. Выведите список всех файлов и каталогов. Убедитесь, что в выводе есть файл lab2.py

   $ ls -l
1. Запустите генерацию вашего варианта (Рисунок 2). Вывод этой команды добавьте в отчет в виде скриншота.  Для генерации:

   $ python lab2.py
<p align="center">
  <img src="pattern_2.png" width="480" title="Pattern_2">
</p>
 
Автоматически созданное описание](Aspose.Words.6f6d3255-36fc-49f7-8bce-7313009fea64.002.png)

   Рисунок 2 Результат генерации варианта

1. Посмотрите на задание Task 1. Там указано название директории, которую вам надо исследовать. Task 2 и Task 3 нам понадобятся позднее, пока они не нужны.
1. Исследуйте структуру созданной директории через терминал. Для этого используйте следующие команды:

   $ ls -l # перечисляет папки и файлы рабочей директории 

   $ cd my\_dir # переходит в директорию my\_dir

   $ cd /absolute/path # можно перейти по абсолютному пути

   $ cd ./relative/path # можно перейти по относительному пути

   $ cd .. # вернуться на уровень вверх

   $ сd ../.. # вернуться на два уровня вверх

   $ cd ~ # перейти в домашнюю директорию

1. Среди директорий найдите текстовый файл. Выведите его содержимое в терминал. Его содержимое добавьте в отчет. Для вывода:

   $ cat имя\_найденного\_файла
1. Нарисуйте дерево, соответствующее структуре исследованной вами папки, любым удобным способом и поместите в отчет.


*Манипулирование файлами*


1. Посмотрите на раздел Task 2 вашего варианта, который вывела нам ранее запущенная команда генерации заданий python lab2.py
1. Перед собой вы увидите дерево директорий, представленное в символьном виде в терминале (Рисунок 2). 
1. Создайте соответствующую дереву структуру директорий с помощью терминала. Для этого вам понадобятся команды:

   $ mkdir dir\_name # создает директорию

   $ mkdir -p вложенные/папки/ # рекурсивно создает директории

   $ cd dir\_name # перейти в директорию

   $ ls -l # перечисляет папки и файлы рабочей директории

   $ rm dir\_name # удаляет директорию

   $ rm -rf dir\_name # удаляет директорию рекурсивно 

1. Перейдите в корневую папку вашего дерева.
1. В корневой папке создайте три файла. Следующей командой:

   $ touch фамилия\_1 фамилия\_2 фамилия\_3

1. Откройте каждый файл и запишите в него что-нибудь. Для этого откройте консольный редактор nano. Запишите что-то. Чтобы сохранить нажмите ctrl+x, затем «Y»:

   $ nano file\_name

1. Файл фамилия\_1 скопируйте и положите рядом с существующим. Для этого:

   $ cp фамилия\_1 copy\_name

1. Файл фамилия \_2 переместите в папку на уровень ниже(глубже) и переименуйте. Для этого:

   $ mv фамилия\_2 ./dir\_name/new\_name\_2

1. Удалите файл фамилия\_3:

   $ rm -rf фамилия\_3

1. Удалите рекурсивно все файлы, название которых заканчивается на цифру 

   $ find . -type f -name '\*[0-9]' -delete



*Ключи и аргументы команд*

1. Посмотрите справку команды tar. Для этого воспользуйтесь следующими командами справки:

   $ tar --help

   $ man tar

   $ info tar

1. Изучите формат команды. Ответьте на вопросы. Какой ключ используется чтобы создать архив? Какой ключ используется чтобы извлечь архив? Какой ключ используется для выбора формата компрессии? Какой ключ используется для установки имени архива/директории?


1. Создайте архив my\_new\_archive.tar.gz из директории, созданной в предыдущем разделе «Манипулирование файлами» с использованием команды tar. Прикрепите его к отчету.

1. ` `Извлеките файл из архива, созданного в предыдущем разделе «Навигация» в Task 3 с использованием команды tar. Прочитайте содержимое secret\_file из архива и добавьте в отчет.
1. ` `Завершите запись команд, набрав в терминале:

   $ exit





