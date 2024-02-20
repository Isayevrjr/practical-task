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


Удалённые репозитории
