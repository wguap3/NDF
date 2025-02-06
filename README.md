## Создание репозитория
##### git init
##### touch README.md
##### git add README.md(git add --all(ДЛЯ ВСЕХ ФАЙЛОВ))
##### git commit -m "first commit"
##### git branch -M main
##### git remote add origin git@github.....t(Ссылка ssh)
##### git push -u origin main
## Хеш, лог и HEAD
#### Хеш — идентификатор коммита
#### После вызова git log появляется список коммитов с их описанием.
#### Вот из каких элементов состоит описание:
##### Строка из цифр и латинских букв после слова commit — это уже знакомый вам хеш коммита.
##### Author — имя автора и его электронная почта.
##### Date — дата и время создания коммита.
##### Сообщение к коммиту.
##### HEAD - то синоним хеша последнего коммита — его можно передавать командам Git в качестве параметра.
## Статусы untracked/tracked, staged и modified
## Как исправить коммит
#### git commit —amend —no-edit(—no-edit если не нужно менять текст коммита)
#### git commit --amend -m "Новое сообщение"
## Как откатиться назад, если «всё сломалось»
#### Выполнить unstage изменений(убрать файл из staged) — git restore --staged <file> 
#### git restore --staged .  - Уберет все файлы из staged
#### «Откатить» коммит — git reset --hard <commit hash>(указываем хэш до того коммита до которого все удалиться без скобок <>)
#### «Откатить» изменения, которые не попали ни в staging, ни в коммит, — git restore <file>
```mermaid
graph LR;
  untracked(неотслеживаемый) -- "git add" --> staged(в списке на коммит);
  staged(в списке на коммит) -- "git commit" --> tracked(отслеживаемый);
  tracked(отслеживаемый) -- "Изменения" --> modified(измененный);
  modified(измененный) -- "git add" --> staged(в списке на коммит);
