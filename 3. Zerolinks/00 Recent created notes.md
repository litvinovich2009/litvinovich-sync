# Недавно созданные заметки
```dataview
table file.ctime as "Дата самой новой заметки"
from ""
where file.ctime > (date(now) - dur(7 days))
sort file.ctime desc
limit 10
```
