 Руководство по работе с Git 

## Что такое **Git**?
*Git* — самая популярная распределённая система контроля версиями.
Основное предназначение Git – это сохранение снимков последовательно улучшающихся состояний проекта.

## *Настройка Git!*

- Первое, что вам следует сделать после установки Git — указать ваше имя и адрес электронной почты. Это важно, потому что каждый коммит в Git содержит эту информацию, и она включена в коммиты, передаваемые вами, и не может быть далее изменена. 
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com

- Второе, когда вы указали своё имя, самое время выбрать текстовый редактор, который будет использоваться, если будет нужно набрать сообщение в Git. По умолчанию Git использует стандартный редактор вашей системы, которым обычно является Vim. 

- Третье: настройка ветки по умолчанию.
Когда вы инициализируете репозиторий командой git init, Git создаёт ветку с именем master по умолчанию. Начиная с версии 2.28, вы можете задать другое имя для создания ветки по умолчанию.ы

Например, чтобы установить имя main для вашей ветки по умолчанию, выполните следующую команду:

$ git config --global init.defaultBranch main.
## Подготовка репозитория
Для создания репозитория необходимо выполнить команду *git init* в папке с репозиторием и у вас появится репозитори
Например, чтобы установить имя main для вашей ветки по умолчанию, выполните следующую команду:

$ git config --global init.defaultBranch main.

### Coздание коммитов
- Для добавления измнения в коммит используется команда *git add <имя файла>*
- Для того, чтобы создать коммит (сохранить)необходимо написать в терминале *git commit -m "комментарий"*
- Чтобы посмотреть состояние репыозитория используют команду *git status*.

###  Основные команды Git
 - git log: Журнал изменений.
Перед переключением версии файла в Git
используйте команду git log, чтобы увидеть
количество сохранений 
- git checkout: переключение между версиями.
Для работы нужно указать не только
интересующий вас коммит, но и вернуться 
в тот, где работаем, при помощи команды 
git checkout master;
- git branch - выводит список веток;
- git branch name -создать новую ветку;
- git merge name - слить две ветки воедино;
- git branch -d (название ветки)-удалить ветку.


 -  git diff: показывает разницу между текущим файлом
и сохранённым
Перед переключением версии файла в Git
используйте команду git log, чтобы увидеть
количество сохранений.
- Изменнения последнего коммита.
Внести изменения в последний коммит можно параметром commit с флагом --amend. Например, вы записали изменения, внесённые в ряд файлов, и поняли, что допустили ошибку в сообщении коммита. В этом случае можете воспользоваться указанной командой, чтобы отредактировать сообщение предыдущего коммита, не изменяя его снимок.
- git clone клонирование репозитория;
- git reset удаление изменения из индекса.

# **Шпаргалка по совместной работе и обновлению проектов**
Не так уж много команд в Git требуют сетевого подключения для своей работы, практически все команды оперируют с локальной копией проекта. Когда вы готовы поделиться своими наработками, всего несколько команд помогут вам работать с удалёнными репозиториями.
- git clone <url-  адрес репозитория> - клонирование внешнего репозитория на локальный ПК
- git fetch
Команда git fetch связывается с удалённым репозиторием и забирает из него все изменения, которых у вас пока нет и сохраняет их локально.

- git pull
Команда git pull работает как комбинация команд git fetch и git merge, т.е. Git вначале забирает изменения из указанного удалённого репозитория, а затем пытается слить их с текущей веткой.

- git push
Команда git push используется для установления связи с удалённым репозиторием, вычисления локальных изменений отсутствующих в нём, и собственно их передачи в вышеупомянутый репозиторий. Этой команде нужно право на запись в репозиторий, поэтому она использует аутентификацию.

- git remote
Команда git remote служит для управления списком удалённых репозиториев. Она позволяет сохранять длинные URL репозиториев в виде понятных коротких строк, например "origin", так что вам не придётся забивать голову всякой ерундой и набирать её каждый раз для связи с сервером. Вы можете использовать несколько удалённых репозиториев для работы и git remote поможет добавлять, изменять и удалять их.

- git archive
Команда git archive используется для упаковки в архив указанных коммитов или всего репозитория.

Дополнительно о работе с git можно почитать  [тут](https://habr.com/ru/articles/541258/)

