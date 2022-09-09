# Инструкция по работе с Git и удаленными репозиториями

## Что такое Git

Git - реализация распределнных контролей версий, имеющая локальные и удаленные репозиториии

## Подготовка репозитория
Для создания репозитория необходимо выполнить *git init* в папке с репозиторием, создатся репозиторий и появится скрытая папка .git


### Основные команды:
* *git log* — вызывать список действий и сохранений
* *git init* — создать репозиторий в папке на локальной машине
* *git add* — отслеживать добавленные файлы
* *git commit* + *комментарий* — сохранить текущее состояние
* *git diff* — показать разницу между версиями
* *git chechout* — переключиться между разными версиями.




## Разметка текста

### Выделение текста 
- **Bold** или  __Bold2__
- *Italics* или _Italics2_
- ~~strickethrough~~

### Нумерованный список
1. First string
2. Second string
3. Third string


## Работа с ветĸами

### Git branch
    * git branch* "options" [-r] | [-a] --merged --no-merged   
    * git branch* "options"  [-l] [-f] branch-name start-point  
    * git branch* "options"  [-r] (-d | -D) branch-name ...  
    * git branch* "options"  (-m | -M) [old-branch] new-branch  
    * git branch* "options"  (-c | -C) [old-branch] new-branch  
    * git branch* "options"  [-r | -a] [--points-at]  
    * git branch* "options"  [-r | -a] [--format]  

### Git branch option
    *  -v, --verbose    show hash and subject, give twice for upstream branch
    *  -q, --quiet  suppress informational messages
    * -t, --track   et up tracking mode (see git-pull(1))
    * -u, --set-upstream-to upstream    change the upstream info
    * --unset-upstream      unset the upstream info
    * --color[=when]      use colored output
    * -r, --remotes         act on remote-tracking branches
    * --contains commit   print only branches that contain the commit
    * --no-contains commit  print only branches that don't contain the commit
    * --abbrev[<n]    use n digits to display object names


### Переключение между ветками
    * *git checkout* *название ветĸи* — переĸлючиться в ветĸу
    * *git checkout* -b *название ветĸи* — создать новую ветĸу и сразу в неё переĸлючиться  

 #### Опции для git checkout
    * git checkout [-q] [-f] [-m] [branch]
    * git checkout [-q] [-f] [-m] --detach [branch]
    * git checkout [-q] [-f] [-m] [--detach] commit
    * git checkout [-q] [-f] [-m] [[-b|-B|--orphan] new-branch] [start-point]
    * git checkout [-f|--ours|--theirs|-m|--conflict=<style][tree-ish] [--] pathspec
    * git checkout [-f|--ours|--theirs|-m|--conflict=<style] [tree-ish --pathspec-from-file=file [--pathspec-file-nul]
    * git checkout (-p|--patch) [tree-ish] [--] [pathspec​] 


## Удалённые репозитории

* _git remote -v_   показать список удалённых репозиториев, связанных с локальным
* _git branch -r_   показать удаленные ветки
* _git branch -a_  показать все ветки(локальные и удаленные)       
* _git remote remove origin_  # убрать привязку удалённого репозитория с сокр. именем origin
* *git remote add origin https://...*  # добавить удалённый репозиторий (с сокр. именем origin) с указанным URL
*_ git remote rm origin_      # удалить привязку удалённого репозитория
* _git fetch origin_         # скачать все ветки с удаленного репозитория (с сокр. именем origin), но не сливать со своими ветками
* _git fetch origin master_   скачивается только указанная ветка
* _git checkout --track origin/github_branch_ # создать локальную ветку github_branch (данные взять из удалённого репозитория с сокр. именем origin, ветка github_branch) и переключиться на неё
* git push origin master     # отправить в удалённый репозиторий (с сокр. именем origin) данные своей ветки master
* _git pull origin_          # влить изменения с удалённого репозитория (все ветки)
* _git pull origin master_   # влить изменения с удалённого репозитория (только указанная ветка)




