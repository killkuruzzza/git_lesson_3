# Инструкция по работе с Git.

1. ## Авторизация.

2. ## Создание файла.

3. ## Работа с удаленными репозиториями.



   1. Установили Git и теперь его настроим. Авторизуемся командами: 
* **git config --global user.name "<Имя автора>"** 
* **git config --global user.email "<Емаил автора>"**

    Далее проверяем корректность авторизации, водим команды: 
* **git config --global user.name**

* **git config --global user.email** 

  Если действия были совершены верно, то при нажатии клавиши Inter после введенных команд в терминале мы увидим имя автора <Иван Иванов> и почту <Email - почта>

  2. Чтобы программа отслеживала изменения в файле необходимо инициализироваться введя в терминале команду:
* **git init**

  Нажимаем Inter и в этой папке программа начинает отслеживать изменения.

## Создание файла.

Созадим в папке файл с названием Homework.md где будим составлять текстовый документ по работе с программой.
  Вводим команду: 
* **git add .**

Эта команда позволит программе следить за изменением всех файлов в папке.

* **git commit --m "комментарий"** 

Команда *git commit* используется для создания коммита по которым можно отслеживать конкретные изменения в файле и находить их.

* **git log**

Команда *git log* выводит все истории коммитов с их хеш кодами.

* **git checkout**

С помощью команды *git checkout* можно изменить файл на необходимую версию введя первые четыре символа, что бы понять какую версию нам нужно запустить.

## Работа с удаленными репозиториями.

Копировать внешний репозиторий на свой ПК можно командой 

* **git clone**

она не только загружает все изменения, но и пытается слить все ветки на локальном компьютере и в удаленном репозитории.

* **git pull** 

Эта команда позволяет скачать все из текущего репозитория и автоматически сделать merge с нашей версией.

* **git push**

Эта команда позволяет отправить свою версию репозитория во внешний репозиторий. При первом её использовании нужна авторизация.

* **pull request**

Команда для предложения изменений и запрос на вливание изменений в репозиторий производится командой *pull request* 