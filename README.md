# Работа с удаленными репозиториями

1. Делаем форк (fork) нужного нам репозитория.При этом у нас создается свой репозиторий в гитхабе с названием файла, которого форкали.
2. На своем рабочем столе открываем папку, в которой будем работать через VSC.
3. Копируем ссылку в своем репозитории на гитхабе и командой 

    **git clone   _наша скопированная ссылка_**
создаем копию на своем локальном компе.
4. После этого для начала работы нужно поменять директории чтобы активировать нашу вставленную папку, это делаем командой 

    **cd  _имя этой папки_** 
5. В эту папку добавляем файл, в котором будем вносить все наши изменения, принято его называть **"README.md"** или вставляем уже наш готовый файл.
6. Все изменения делаются на отдельной своей ветке, создаем ветку **"git branch _имя своей ветки_"**, переходим на нее, убеждаемся в этом и работаем только в этой ветке.
7. По готовности сохраняемся, коммитимся и командой     
**"git push"** отправляем наш файл с изменениями в свой репозиторий на гитхабе. При этом гитхаб подскажет, чтопрописать после слов **_git push_**.
8. Переходим на гитхаб, обновляем его, смотрим наши изменения, что они там есть, и в гитхабе появляется взможность (кнопочка **Compare @ pull reguest**).нажимаем ее, тем самым предлагаем владельцу программы посмотреть наши изменения и принять их, ну или не принять.
9. Команда **git pull** позволяет нам с нашего репозитория на гитхабе выкачать в свой локальный репозиторий все актуальные изменения, которые мы там можем делать с другого компьютера.

По удаленным репозиториям для начала готово!



# Работа с ветками

## Команда **git branch**

знак * стоит напротив той ветки, в которой мы находимся.

branch - ветка

Эта команда служит для того, чтобы посмотреть, в какой ветке мы сейчас находимся. Заодним показывает все ветки, какие есть.

## Команда **git branch название ветки**

Это команда для создания новой ветки. 

## Команда **git branch -d название ветки**

Это команда для удаления ненужной ветки.

## Команда **git checkout название ветки**

Команда для перехода на нужную нам ветку.

## Команда **git log --graph**

## Команда **git merge**

<<<<<<< HEAD
Команда по слиянию веток производится из той ветки, в которую мы хотим поместить все новые дополнения.
=======
Это команда для слияния веток. После merge ставим название ветки, которую сливаем с нашей. 
>>>>>>> kommerge
**почему-то не предлагает выбор как было у Ильнара в лекции, просто сразу сливает оба варианта и просто предлагает самому их отредактировать**

## Заключение
