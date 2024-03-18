git init - делает папку с проектом(директорию) репозиторием
git status - показывает текущее состояние репозитория
git add - с помощью этой команды гит сможет отслеживать и хранить информацию файлов в директории
git add . - добавляет текущую папку целиком в целиком для отслеживания и хранения
git commit -m - создает коммит файлов с последующем описанием
git log - позволяет увидеть историю коммитов
ls -la .ssh/ - показывает список shh ключей
git remote add - привязать удаленный репозитория к локальному
git remote -v - показывает что репозитории связаны
git push - загружает содержимое локального репозитория на GitHub
git log --oneline - получаем сокращенный лог коммита

Схема mermaid

```swift
graph LR;
untracked -- "git add" --> staged;
staged    -- "???"     --> tracked/commited;

%% стрелка с текстом для примера:
A -- "text" -->B
```

git commit --amend --no-edit - позволяет дополнить последний коммит ФАЙЛОМ не изменяя описание коммита (При этом сам файл не должен быть запушен)

Пример

```
touch File1.md && touch File2.md
git add File1.md
git commit -m "Some text"

git add File2.md
git commit --amend --no-edit
```

git commit --amend -m "New message" - позволяет изменить сообщение в коммите
git restore --staged example.txt - команда, которая позволяет убрать файл из staging (после команды git add)

```
git add example.txt
git restore --staged example.txt
```
git restore --staged . - сбрасывает все файлы из staging обратно в untracked/modified
git reset --hard <commit hash> - возвращает состояние репозитория к более раннему(все коммиты, файлы и код проекта которые были сделаны после коммита к которому мы вернулись удаляются безвозвратно!)
git restore <file> - возвращает файл (который не попал ни в staging, ни в коммит) до последней версии, которая была сохранена через git commit или git add

```
# случайно изменили файл example.txt
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
          modified:   example.txt

$ git restore example.txt
$ git status
On branch main
nothing to commit, working tree clean
```
git diff - позволяет увидеть изменения файлов. Эта команда сравнит последнюю закоммиченную версию файла с текщей(измененной) версией. Работает команда в modified файлах
git diff --staged - позволяет увидеть изменения в staged файлах

