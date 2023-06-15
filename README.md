![](/git_lesson_3/git-logo.png)

# Инструкция по работе с Git и удалёнными репозиториями

## Что такое Git?

Git - мощная и сложная распределённая система контроля версий. Понимание всех возможностей git открывает для разработчика новые горизонты в управлении исходным кодом.

 Линус Торвальдс

>Я очень доволен Git. Он работает исключительно хорошо с кодом ядра и по-прежнему следует моим ожиданиям

## Установка git 

**[скачать и установить https://git-scm.com/](https://git-scm.com/)**


## Установка имени и электронной почты

Выполните следующие команды, чтобы git узнал ваше имя и электронную почту.

*git config --global user.name "Your Name"*

*git config --global user.email "your_email"*

## Создайте папку и файл

Начните работу в пустом рабочем каталоге с создания пустой папки с любым именем, затем войдите в него и создайте там файл с нужным для вас расширением.

## Создайте репозиторий

Теперь у вас есть папка с одним файлом. Чтобы создать git репозиторий из этой папки, выполните команду *git init*.


zrdfguijknbgfzertyutyolj
## Добавьте страницу в репозиторий

Давайте добавим в репозиторий файл, который перед этим создали в папке.

*git add название вашего файла*

*git commit -m "First Commit"*

## Проверьте состояние репозитория

* Используйте команду *git status*, чтобы проверить текущее состояние репозитория.

* Измените ваш файл, а затем проверьте состояние *git status*

* вы увидите:

     *$ git status*

    *On branch master*

    *Changes not staged for commit:*

   *(use "git add <file>..." to update what will be committed)*

  *(use "git checkout -- <file>..." to discard*

  *changes in working directory)*

	*modified:   ваш файл*

    *no changes added to commit (use "git add" and/*

    *or "git commit -a")*

## Индексация изменений

Дайте команду git проиндексировать изменения

*git add ваш файл*

Проверьте состояние *git status*

## Коммит

Сделаем коммит того, что мы изменили 

*git commit -m "ваш комментарий"*

Команда  *git commit --amend* позволяет объединить проиндексированные изменения с предыдущим коммитом без создания нового коммита.

## Как просмотреть все коммиты

С помощью *git log*

## Как вернуться к предыдущему состоянию 

с помощью *git checkout хеш-данные*

## Как вернуться в текущую версию

с помощью *git checkout master*

## Как изменить содержание коммита

набираем команду *git commit* без *m*, вам откроется редактор для изменения содержания коммита 

## Создание ветки

набираем команду *git branch <имя файла>*

чтобы перейти на новую ветку набираем *git checkout <имя файла>*

Можно использовать более короткую команду, которая позволяет создать ветку и сразу перейти на неё, набираем *git checkout -b <имя файла>*, например git checkout -b style.


## Конфликт 

Вам необходимо вручную разрешить конфликт.
Затем сделать коммит решения конфликта

## Как удалить ветку

Набираем команду *git branch -d <имя файла>*
## Слияние ветки

Слияние веток делать оттуда, куда хотите добавить ветку. Набираем команду *git merge <имя файла>. При слиянии веток может возникнуть конфликт.


### P.S. использован язык разметки Markdown

![изображение](images/Markdown-Logo.png "Логотип Markdown")




