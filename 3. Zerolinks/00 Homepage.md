---
cssclasses:
  - fullscreen-note
banner: "![[Новый проект 1.png]]"
banner_y: 0.45592
banner_x: 0.45402
---
---
```dataviewjs
const container = dv.el("div", "", {cls: "live-clock"});

function capitalizeFirst(str) {
  return str.charAt(0).toUpperCase() + str.slice(1);
}

function updateClock() {
  const now = new Date();
  const time = now.toLocaleTimeString(); // Часы на английском (12-часовой формат)
  
  // Получаем день недели и дату
  const options = { weekday: "long", year: "numeric", month: "long", day: "numeric" };
  let date = now.toLocaleDateString("en-US", options);

  // Делаем первую букву заглавной
  date = capitalizeFirst(date);

  container.innerHTML = `
    <div class="time" style="color: #723493" >${time}</div>
    <div class="date">${date}</div>
  `;
}

updateClock();
setInterval(updateClock, 1000);
```

---
>[!multi-column]
>>[!note] Today's tasks
>>```dataview
>>list
>>from "5. Main folder"
>>limit 0
>>```
>
>>[!note] Projects
>>```dataview
>>task
>>from #project
>>limit 0
>>```

---
>[!multi-column]
>>[!example] Recent modified notes
>>```dataview
>>list
>>from ""
>>sort file.mtime desc
>>limit 5
>>```
>
>>[!example] Recent created notes
>>```dataview
>>list
>>from ""
>>where created and !contains(file.folder, "4. Templates")
>>sort created desc
>>limit 5
>>```

---

>[!multi-column]
>
>>### Book reading
>>```tracker
>>searchType: frontmatter
>>searchTarget: Reading
>>datasetName: Book reading
>>folder: Daily
>>fixedScale: 0.8
>>month:
>>	startWeekOn: 'Mon'
>>	yMin: 0
>>	yMax: 30
>>	color: "#A67D5A"
>>	todayRingColor: purple
>>	headerMonthColor: black
>>	headerYearColor: purple
>>	selectedRingColor: "#DB6015"
>>	circleColorByValue: true
>>```
>
>>### English practice
>>```tracker
>>searchType: frontmatter
>>searchTarget: English
>>datasetName: English practice
>>folder: Daily
>>fixedScale: 0.8
>>month:
>>	startWeekOn: 'Mon'
>>	yMin: 0
>>	yMax: 30
>>	color: "#C77E56"
>>	todayRingColor: purple
>>	headerMonthColor: black
>>	headerYearColor: purple
>>	selectedRingColor: "#DB6015"
>>	circleColorByValue: true
>>```
>
>>### Keyboard typing
>>```tracker
>>searchType: frontmatter
>>searchTarget: Typing
>>datasetName: Keyboard typing
>>folder: Daily
>>fixedScale: 0.8
>>month:
>>	startWeekOn: 'Mon'
>>	yMin: 0
>>	yMax: 10
>>	color: "#A89A89"
>>	headerMonthColor: black
>>	headerYearColor: purple
>>	todayRingColor: purple
>>	selectedRingColor: "#DB6015"
>>	circleColorByValue: true
>>```

