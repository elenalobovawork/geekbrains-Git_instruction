##  Инструкция GIT ![логотип git](git.jpg)
Git — это система контроля версий, которая позволяет отслеживать любые изменения в файлах, хранить их версии и оперативно возвращаться в любое сохранённое состояние.

*Памятка по Git, с которой можно ознакомиться по ссылкам:* 
>[команды часть 1](https://habr.com/ru/post/541258/)

>[команды часть 2](https://habr.com/ru/post/542616/)

### Создание репозитория
Пререйдите в папку вашего проекта и выполните команду

```
git init
```
### Создание коммитов
Для добавления содержимого рабочей директории в индекс для последующего комммита выполните команду
```
git add <имя файла>
```

Для фиксафии изменений в репозитории используем команду
```
git commit - m "текст комментария"
```
Для просмотра состояния репозитоия и проверки наличия изменений, которые нужно закоммитить используе команду
```
git status
```
Для просмотра журнала изменений и количества сохранений используйте команду
```
git log
```
Чтобы вывести список комитов и их идентификаторы так же можно воспользоваться командой 
```
git log --oneline
```
___
*После просмотра многострочного ответа нажатие клавиши "q" возвращает в исходное окно терминала*
___

Для отбражения разницы между текущим состоянием файла и сохраненным используйте команду
```
git diff
```
Для просмотра изменений двух разных коммитов можно использовать команду
```
git diff <хеш первого коммита> <хеш второго коммита>
```

### Переключение между версиями
Для того, чтобы переключаться между сохраненными версиями используйте команду

```
git checkout <первые 4 цифры коммита>
```
Для того, чтобы вернуться в главную ветку, где мы работаем, используем команду
```
git checkout master
```
### Создание новых веток
Для того, чтобы посмотреть какие ветки у нас есть, и в какой мы сейчас находимся, используем команду:
```
git branch
```
Для того, чтобы создать новую ветку, необходимо выполнить команду:
```
git branch <имя новой ветки>
```
Для того, чтобы начать работать в новой ветке, необходимо на нее переключиться, используя команду:
```
git checkout <имя ветки, на которую хотим переключиться>
```
### Слияние веток
Для того, чтобы слить любую ветку с текущей, используем команду:
```
git merge <имя ветки для слияния с текущей>
```
### Удаление веток
Чтобы удалить ветку, которая больше не нужна (например, мы слили ее с главной веткой, либо отказались от изменений), необходимо использовать команду:
```
git branch -d <имя ветки, которую хотим удалить>
```
_Нужно помнить о том, что удалить ветку, в которой находимся нельзя, необходимо перейти на другую ветку для удаления ненужной_

### Игнорирование файлов
При совместной работе над проектом могут возникнуть ситуации, когда мы не хотим, чтобы какие то файлы или части проекта были видны другим участникам команды.

Например, в Git не принято добавлять файлы изображений, их хранят на сторонних носителях.
Для того, чтобы Git игнорировал и не отслеживал определенные файлы необходимо создать файл: 
```
.gitignore
```
+ Добавить в этот файл наименование файлов, которые не нужно отслеживать, сохранить этот файл;
+ Закоммитить этот файл с помощью команды:
```
git add .gitignore 
```
и
```
git commit -m "Сообщение, например, о том, что мы создали данный файл"
```
### Визуализация веток
Чтобы отобразить все изменения в ветках проекта, используем команду:
```
git log --graph
```
### Работа с удаленными репозиториями
![Git and GitHub](git_github.jpg)

Для того, чтобы копировать внешний репозиторий на свой ПК, используем команду:
```
git clone <ссылка на удаленный репозиторий>
```
Для того, чтобы отправить свою версию репозитория во внешний репозиторий, используем команду:
```
git push
```
_При первом использовании данной команды необходимо авторизоваться на внешнем репозитории._

Для того, чтобы получить изменения из удаленного репозитория и обновить свою рабочую копию в соответствии с ними, используем команду:
```
git pull
```
_Стоит заметить, что это составная команда, она подгружает изменения и сливает ветки локального и удаленного репозитория_

Чтобы создать запрос на вливание своих изменений во внешний репозиторий, используем команду на платформах GitHub, GitLab, Bitbucket и других:
```
pull request
```
_Алгоритм создания pull request запроса_
+ Делаем fork (ответвление) репозитория
+ Делаем git clone своей версии репозитория
+ Создаем с помощью git branch <имя новой ветки> новую ветку и в нее вносим свои изменения
+ Фиксируем изменения (делаем коммиты)
+ Отправляем свою версию в свой GitHub
+ На сайте GitHub нажимаем кнопку pull request




