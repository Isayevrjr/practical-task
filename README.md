Список базовых команд

Чтобы переместиться из одной папки в другую - cd имя_папки
Если в названии есть пробел, использовать кавычки
Чтобы вернуться назад - cd ..
чтобы посмотреть в какой папке находимся - pwd
Создать новую папку - mkdir имя_папки
Создать файлы - touch hello.txt 
Переименовать - mv hello.txt helloWorld.txt (если вместо второго файла написать имя папки, файл переместится туда)
Удалить файл - rm имя_файла
Удалить папку - rmdir имя_папки
Удалить папку с файлами - rm -r имя_папки
Написать, добавить в файл текст - echo "Какой-то текст" >> имя_папки
Вывести содержимое файла прямо в командную строку - cat имя_папки


Работа с git

Посмотреть мои настройки - git config --list 
Выйти из просмотра настроек можно по клавише Q, от англ. quit – покинуть, выйти

По умолчанию git в macOS не чувствителен к регистру: если Git запомнил название файла как practicum.txt, то изменение его на PRACTICUM.txt не будет расценено как изменение. Это вызывает неудобства в Xcode
Чтобы научить git быть внимательным к регистру, можно перенастроить его такой командой - git config --global core.ignorecase=false 

Чтобы Git начал отслеживать изменения в проекте, папку с файлами этого проекта нужно сделать Git-репозиторием.
Для этого следует переместиться в неё и ввести команду - git init

Если случайно сделали репозиторием не ту папку, необходимо удалить .git -         rm -rf .git

Текущее состояние репозитория - git status

Чтобы сохранить в репозитории новый файл - git add имя_файла
Для неск файлов - git add --all
Альтернатива git add .

Сделать коммит можно командой git commit с ключом -m(от англ. message – сообщение), который присваивает коммиту название.
Обычно в таком сообщении содержится пояснение, что именно было изменено. Названия нужны, чтобы найти полезную версию и посмотреть состояние репозитория на момент этого коммита.
Сделайте свой первый коммит, откройте консоль и вызовите команду:
git commit -m "Мой первый коммит!" 
После выполнения команды текущая версия файлов будет сохранена в репозитории под версией "Мой первый коммит!". А в консоль выведется сообщение о добавленных изменениях
Выход из Vim - :q!

И сохранить и закомитить - git add . && git commit -m "Обновить README"


Удалённые репозитории

 всю команду git push -u origin main можно читать как «Git, отправь мои изменения из локальной ветки main в главную ветку удалённого репозитория (origin) и установи её как основную для будущих использований команды push».
После первого раза достаточно просто git push, но только после git commit -m ""

Запомним! Команда git push — вторая основная команда после git commit. Вы будете использовать её каждый раз, когда захотите опубликовать свои изменения в удалённом репозитории.

git clone git@github.com:<ВАШ НИКНЕЙМ>/first-project-git.git second-project-git
cd second-project-git 
Разберём, как устроена команда:
git clone — так объявляется команда Git для клонирования репозитория.
git@github.com:<ВАШ НИКНЕЙМ>/first-project-git.git — адрес репозитория в GitHub, с которого вы хотите сделать копию.
second-project-git — название папки на вашем компьютере, куда будет склонирован репозиторий. Если вы не укажете это название, Git создаст папку с тем же названием, что и у репозитория на GitHub — в нашем случае first-project-git. Нам этот вариант не подходит: у нас уже есть папка с названием репозитория в project.
Теперь вы можете работать над этим же репозиторием, но условно из другого места.
Точно так же вы можете действовать, если захотите поработать с другого компьютера.
И так же будут действовать ваши друзья, помогая развивать проект.
Запомним! Команда git clone копирует проект в указанное место.
Теперь представим, что папка second-project-git находится не на вашем компьютере — в ней работает ваш друг. Он вносит изменения и пушит их в репозиторий. Вам бы очень хотелось их получить!
У Git есть и на это команда: git pull; а pull на английском — «тянуть».
Она противоположна команде git push: если первая выталкивала изменения в удалённый репозиторий, то git pull их вытягивает.


Ветки

Просмотреть ветку на которой находимся - git branch
Создать новуб ветку - git branch <название_ветки>
Переключаться между ветками - git checkout <название_ветки>

Можно создать ветку и сразу начать в ней работать. За это отвечает команда git checkout с флагом -b (от англ. branch) и названием ветки. Эта команда делает то же самое, что и последовательность команд git branch <название_ветки> && git checkout <название_ветки>.

git checkout -b another_branch # создали ветку и сразу на неё переключились

Чтобы слить одну ветку с другой, в первую очередь нужно быть в главной main, далее команда - git merge <название_присоединяемой_ветки>

Чтобы запушить ветку - git push -u origin <название_ветки>
