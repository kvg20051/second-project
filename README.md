# Основы работы с Git

## правим .gitconfig
```
git config --global user.name 'Victor G. Krivulets'
```
```
git config --global user.email victor.krivulets@yandex.ru
```
### создаем папку для локального репозитория
```
mkdir second-project
```
### чтобы инициировать Git, заходим в папку с репозиторием и выполняем
```
git init
```
### добавляем файл в репозиторий
```
git add имя_файла
```
### добавляем все файлы в репозиторий
```
git add --all
```
```
git add .
```
### добавляем файл в репозиторий
```
git commit -m 'changed README.md'
```
### добавляем удаленный репозиторий
```
git remote add origin git@github.com:kvg20051/second-project.git
```
### синхронизация локального репозитория с удаленным (первый пуш):
```
git push -u origin master
```
### далее для всех последующих пушей выполняем
```
git push
```
### посмотреть историю коммитов
```
git log
```
```
git log --oneline
```
### создать новую ветку
```
git branch new_branch
```
### перейти в ветку new_branch
```
git checkout new_branch
```
# SSH-keys

### SSH-keys github.com
```
ssh -T git@github.com
```
### SSH-keys gitea
```
???
```







## Выделение текста

Вы можете выделять текст в markdown с помощью символов `_` или `*`. Например:

Пример _курсива_ и **жирного** текста.

## Заголовки

Заголовки можно создавать с помощью символа `#`. Чем больше `#`, тем меньше заголовок. Например:

# Заголовок первого уровня
## Заголовок второго уровня
### Заголовок третьего уровня

## Выделение кода
