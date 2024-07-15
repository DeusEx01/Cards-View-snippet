---
cssclasses:
  - cards
  - cards-columns-5
  - cards-readline-off
---
```dataview
TABLE WITHOUT ID choice(contains(cover, "http"), ("![coverimg|100](" + cover + ")"), embed(link(cover, "150")) ) as "Cover",
file.link,
"<span " + "class='cards-icon'>" + "Series" + "</span>"  + series + " (" + series_part + ")" as Series,
"<span " + "class='cards-icon'>" + "Author" + "</span>" + author as Author,
"<span " + "class='cards-icon'>" + "Started" + "</span>" + started as Started,
genres as Genres,
"<progress max=" + 
volume + " value=" + number(
timestamp) + "> </progress> "  + number(
timestamp) + " of " + number(
volume) + " " + units + " (" +round(number(
timestamp)/number(
volume)*100) + "%" + ")" as Progress
FROM #book
```
