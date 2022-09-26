# Инструкция по командам Git

## init

Команда используется для инициализации системы контроля версий по текущему пути.

```shell
git init
```

## add

Добавление наблюдения за файлом или индексация изменённых файлов

```shell
git add README.md
git add *.py
```

## commit

Фиксация изменений, обязательно при вызове указывать комментарий с ключом `-m`:

```shell
git commit -m "added README.md"
```

## diff

Просмотр изменений

```shell
git diff git.md
```

## log

Просмотр истории фиксаций

```shell
git log
git log --graph
```

## branch

Просмотр веток

```shell
git branch
```

Создание ветки

```shell
git branch issue/12
```

Удаление ветки

```shell
git bransh -d issue/12
```

## checkout

Переключение активной ветки

```shell
git checkout issue/15
```

Также можно создать и переключиться на новую метку с применением ключа `-b`:

```shell
git checkout -n isuue/16
```

Это аналогично выполнению двух команд:

```shell
git bransh issue/16
git checkout issue/16
```

## merge

Слияние изменений

```shell
git merge issue/12
```

NB! Выполнять слияние из той ветки, **куда** производится слияние.
