---
created: 2025-06-07
tags:
  - obsidian
aliases:
  - Метаформатирование
---

# Meta editing

Для метаформатирования даты я использовал скрипт в python:

```python
import os
import re
FOLDER_PATH=r"C:\Users\Vladislav\AppData\Roaming\Л.В\VladisLove\5. Main folder"
date_pattern= re.compile(r"(date\s*:\S*)(\d{2})\.(\d{2})\.(\d{4})")
for filename in os.listdir(FOLDER_PATH):
    print(f"Проверка файла: {filename}")
    if filename.endswith(".md"):
        file_path=os.path.join(FOLDER_PATH, filename)

        with open(file_path, "r", encoding="utf-8") as file:
            content=file.read()

        def replace_date(match):
            prefix=match.group(1)
            day=match.group(2)
            month=match.group(3)
            year=match.group(4)
            new_date=f"{year}-{month}-{day}"
            print(f"was changed: {day}.{month}.{year}—>{new_date} in file {filename}")
            return prefix + new_date
        new_content=re.sub(r'(date:\s*)(\d{2})\.(\d{2})\.(\d{4})', replace_date, content)

        if content!=new_content:
            with open(file_path, "w", encoding="utf-8") as file:
                file.write(new_content)

            print(f"Обновлён: {filename}")

```

- `FOLDER_PATH=re"C:\Users\..."` — путь к папке с файлами, в которых нужно сделать метаформатирование;

Для того, чтобы запустить скрипт, нужно:
1. Открыть терминал (`Win+R`) и прописать *cmd*;
2. Ввести команды: **cd \путь\к\папке\со\скриптом** и затем написать **python название_скрипта.py** .
