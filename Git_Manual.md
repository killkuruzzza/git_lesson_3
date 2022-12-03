
Контроль версий (Git)
=====================

Аннотация  
----------

Git - распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

Среди проектов, использующих Git — ядро Linux, Swift, Android, Drupal, Cairo, GNU Core Utilities, Mesa, Wine, Chromium, Compiz Fusion, FlightGear, jQuery, PHP, NASM, MediaWiki, DokuWiki, Qt, ряд дистрибутивов Linux.

Ниже будет приведена краткая инструкция по наиболее часто используемым командам Git. Помните, как готовясь к экзаменам, делали шпаргалки? Вот и сейчас, назовем ее шпаргалкой. Шпаргалкой по командам Git.

## Шпаргалка по командам Git

1. **Configuration** - описание конфигурации
    * git config --global user.name "FirstName LastName"
    * git config --global user.email @your-email@email-provider.com

2. **Starting a repository** - инициализация репозитария
    * git init
    * git status

3. **Staging files** - подготовка к сохранению
    * git add file-name
    * git add file-name another-file-name yet-another-file-name
    * git add .
    * git add --all
    * git add -A
    * git rm -- cashed file-name
    * git reset file-name
4. **Committing to a repository** - сохранение (фиксация данных)
    * git commit -m "commentary"
    * git reset --soft HEAD^
    * git commit --amend -m "your message"
5. **Committing to a repository** - сохранение (фиксация данных)
    * git remote add origin --link--
    * git push -u origin master
    * git clone --clone--
    * git pull

    ## Cписок команд

    * git init = initialize project to use git - инициализировать репозитарий
    * git add . = add all changes to be saved - подготовить к сохранению все файлы 
    * git add *filename* = add single file to be saved - подготовить к сохранению файл с указанным именем
    * git commit -m "message" = save changes with message - сохранить (зафиксировать) изменения, указав комментарий
    * git push origin master = push changes to github master - сбросить изменения на github
    * git pull origin master = pull changes from github master - скачать изменения с github
    * git checkout -b new-branch = create a new branch - создвть новую ветвь
    * git status = check status of changes - запросить статус по изменениям
    * git log = see all previous saved changes - показать журнал всех изменений
    * git checkout *commit hash* = travel back to old commit -откатиься на раннюю контроьную точку (commit)

### Ссылки на первоисточники

***Git Tutorial For Dummies*** **by Nick White** 

<https://www.youtube.com/watch?v=mJ-qvsxPHpY>

!["Nick White"](NickWhite.png)