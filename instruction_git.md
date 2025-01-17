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

## Работа с удаленным репозиторием в git

### Есть несколько вариантов работы с удаленным репозиторием гита. 

1. Залитиь свой локальный репозиторий на один из сервисов, например GitHub

2. Скопировать чейто удаленный репозиторий

3. предложить/принять изменения в удаленный репозиторий

### Для того чтобы создать свой репо на гитхабе:

Чтобы создать свой репохиторий в гитхабе, надо предварительно создать свой аккаунт на сервисе. далее создать новый удаленный репозиторий и получить ссылку на него.

### Как перенести свой локальный репозиторий на гитхаб.

Для переноса локального репо, на гит хаб нам следует выполнить последовательно ряд следующих команд. Так же эта инструкция появится после создания новго репо на гитхаб, где можно использовать копирование команд.

    git remote add origin "ссылка на удаленный репо"

Данную команду мы используем для задания адреса пуша гиту.

    git branch -M main

В даненом случае мы обозначаем какая ветка будет являться основной, как правило это ветка мастер.

    git push -u origin main

этой командой мы непосредственно отправляем содержимое нашего локального репо на гитхаб

### Как скопировать удаленный репо другого пользователя с гитхаб

Есть небольшое различие в функциях. 

1. Мы можем скопировать чейто(в том числе и свой) без создания аккаунта репозиторий и работать с ним локально. 

2. Мы можем создать копию удаленного репозитория пользователя в своем аккаунте и в дальнейшем вносить в него изменения и затем предлогать их автору

* Для простого копирования мы используем зеленую кнопку "< code >"

После чего в терминал вводим команду

    git clone "ссылка полученая по кнопке код"

после этого мы получаем локальную копию выбранного удаленного репо

* Для создания удаленной копии с возможностью редактирования и внесения предложений изменений автору мы должны использовать кнопку форк. После этого будет создана копия удаленного репозитория в нашем аккаунте.

дале мы повторяем деййствия с кнопкой код и командой git clone

