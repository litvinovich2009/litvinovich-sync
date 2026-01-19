---
created: 2025-07-08
tags: 
aliases:
---

# Firefox

**Путь к папке моего профиля в Firefox:**
- C:\Users\Vladislav\AppData\Roaming\Mozilla\Firefox\Profiles\euua80lr.default-release

Также, можно зайти в папку своего профиля, написав в поисковую строку `about:config` :
- ![[Pasted image 20250708114356.png]]
	- Используется тот профиль, под которым написано: "Этот профиль сейчас используется и не может быть удален".

Код для смены бэкграунда на **свое фото**:
```
@-moz-document url("about:home"), url("about:newtab") {
  body {
    background: url("имя\файла") center/cover no-repeat fixed !important;
  }
}
```

Чтобы поставить вместо фото **цвет**:
```
@-moz-document url("about:home"), url("about:newtab") {
  body {
    background: #ff0000 !important;
  }
}
```