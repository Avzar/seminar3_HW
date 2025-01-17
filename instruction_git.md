# **Инструкция по работе с системой контроля версий Git**

![Эмблема Git](git.jpg)

Git (произносится «гит») — распределённая система управления версиями. Проект был создан Линусом Торвальдсом для управления разработкой ядра Linux, первая версия выпущена 7 апреля 2005 года. На сегодняшний день его поддерживает Джунио Хамано.

## Инициализация репозитория

Чтобы создать (инициализировать) новый репозиторий нужно в терминале ввести команду:

    git init

Репозиторий будет создан в той папке, из которой вызывалась команда

## Проверка состояния репозитория

Чтобы проверить текущее состояние репозитория нужно ввести в терминале команду:

    git status

## Добавление изменения к отслеживанию версионности

Чтобы добавить сделанное изменение к отслеживанию (поместить в индекс) нужно ввести команду:

    git add <имя файла>

где вместо <имя файла> вводится путь к файлу относительно расположения репозитория.

## Фиксация изменений

Чтобы зафиксировать изменение используется команда:

    git commit

В таком случае откроется окно для ввоба краткого описания сделанных изменений.

Чтобы сделать это одновременно с фиксацией используется команда:

    git commit -m "комментарий"

## Просмотр истории изменений

Чтобы посмотреть историю изменений используется комада

    git log

Для просмотра изменений с выводом одного коммита в одну строку используется команда

    git log --oneline

Для просмотра всех имеющихся коммитов используется команда

    git log --all

Для просмотра лога с графическим изображением веток используется команда

    git log --graph

Все указанные флаги могут использоваться вместе:

    git log --all --oneline --graph

## Просмотр различий между изменениями

Для просмотра отличий между текущим состоянием репозитория и последним сохраненным изменением используется команда

    git diff

Можно также посмотреть разницу между любыми двуми коммитами. Для этого используется команда

    git diff <хэш1> <хэш2>

## Переключение на нужное изменение

Чтобы переключиться на нужный коммит используется команда

    git checkout <хэш>

## Ветки в Git

### Создание новой ветки

Чтобы создать новую ветку используется команда

    git branch <имя_ветки>

### Просмотр всех веток

Чтобы посмотреть какие ветки существуют и на какой мы находимся используется команда

    git branch

### Переключение между ветками

Чтобы переключиться на другую ветку используется команда

    git checkout <имя_ветки>

### Слияние веток

Чтобы влить одну ветку в другую необходимо находясь в целевой ветке (КУДА будем делать слияние) выполнить команду

    git merge <имя_вливаемой_ветки>

### Конфликты при слиянии

Если одна и та же строка в разный версиях записана по разному возникнет конфликт.
Чистый гит автоматически сохраняет оба изменения, далее требуется вручную внести нужные правки и сделать коммит.

VSСode дает возможность выбрать какое изменение сохранить (входящее, существующее или оба).

### Удаление ветки

Чтобы удалить ветку, которая больше не нужно (например после слияния) используется команда

    git branch -d <имя_ветки>

### Работа с удаленными репозиториями

Для того, чтобы создавать, просматривать и удалять подключения к другим репозиториям используется команда

    git remote

Для того чтобы загрузить коммиты, файлы и ссылки из удаленного репозитория в ваш локальный репозиторий, но при этом не вынуждает вас выполнять слияние изменений с вашим репозиторием используется команда

    git fetch

Для того чтобы выгрузить содержимое локального репозитория в удаленный репозиторий и передать коммиты из локального репозитория в удаленный, используется команда

    git push

Для того чтобы извлечь и загрузить содержимое из удаленного репозитория и немедленного обновления локального репозитория этим содержимым используется команда

    git pull

### URL-адреса репозиториев

Git поддерживает различные способы ссылки на удаленный репозиторий. Два наиболее простых способа доступа к удаленному репозиторию: протоколы HTTP и SSH. Протокол HTTP — простой способ разрешить к репозиторию анонимный доступ только для чтения. Пример ниже

    http://host/path/to/repo.git

### Просмотр удаленных репозиториев

По умолчанию команда _git remote_ отображает ранее сохраненные удаленные подключения к другим репозиториям. Создается однострочный список закладок с именами удаленных репозиториев:

    $ git remote
    origin
    upstream
    other_users_repo