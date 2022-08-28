### Домашнее задание 3
Работа с репозиториями

## Task1. Создание своего репозитория с нуля (push -u origin master)
* `git init`
* `git add .`
* `git commit -m "Initial commit"`
*  зайти на https://github.com/iRezograf/ и создать репозиторий Task1 
```
git remote add origin https://github.com/iRezograf/Task1.git
git branch -M master
git push -u origin master
```

## Task2. Клонирование удаленного репозитория ( clone)
1. Подготовительная работа: создание удаленного репозитория 
* заходим на https://github.com/iRezograf в раздел "your repositiories"
* нажимаем кнопку NEW 
* вводим имя репозитория, например Task2.git
* заполняем остальные поля. Сохраняем/
2. В VSCode открываем новое окно.
3. Выбираем Clont Git Repostory ...
4. В окне вводим/выбираем путь к клонируемому репозиторию, например https://github.com/iRezograf/Task2
5. Создаем этот текст. Сохраняем. Пушим на Github
* `git add Task2.md`
* `git commit -m "Создали файл Task2.md"`
* `git push`
* 
## Task3. Участие в чужом проекте (Fork)
1. Заходим в совместный проект, например:
https://github.com/killkuruzzza/git_lesson_3
2. В верхнем правом углу нажимаем Fork->Create new Fork
3. Создаем свою копию и открываем ее на локальном компьютере. См - `Task2. Клонирование удаленного репозитория ( clone)`
4. Создаем новую ветку, например Task3
   * `git branch RRA_Task3`
   * `git checkout RRA_Task3` 
5. Правим этот файл.
6. Сохраняем, пушим:
   ```
   git add .
   git commit -m "Добавлен файл Task3.md"
   git push --set-upstream origin RRA_Task3
   ```  
7. Заходим на `https://github.com/iRezograf/git_lesson_3`
8. 