---
cssclasses:
  - cards
---


```dataview
TABLE WITHOUT ID choice(contains(cover, "http"), ("![coverimg|100](" + cover + ")"), embed(link(cover, "150")) ) as "Cover",
file.link,
"<span " + "class='cards-icon'>" + "Author" + "</span>" + author as Author,
"<span " + "class='cards-icon'>" + "Started" + "</span>" + started as Started,
"<span " + "class='cards-icon'>" + "Genres" + "</span>" + genres as Genred,
"<span " + "class='cards-icon'>" + "Rating" + "</span>"  + rate as Series,
"<progress max=" + 
volume + " value=" + number(
timestamp) + "> </progress> "  + number(
timestamp) + " of " + number(
volume) + " " + units + " (" +round(number(
timestamp)/number(
volume)*100) + "%" + ")" as Progress
FROM #book 
SORT started DESC
```
