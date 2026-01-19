## All books
```dataview
table
	author as "Автор",
	published as "Год",
	file.inlinks as "Упоминание",
	tags as "Key words",
	dateformat(file.ctime, "DD") as "Создан"
from #кулинария
```


## Книги по [[Кулинария]]
```dataview
Table
	author as "Автор",
	published as "Год",
	file.inlinks as "Упоминание"
From #кулинария
```

## Книги по Python
```dataview
Table
	author as "Автор",
	published as "Год",
	file.inlinks as "Упоминание"
From #python
```
| Book | Price |    
|------|------|
| $100 | $200 |






