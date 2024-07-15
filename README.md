# Cards-View-snippet
This is a snippet for alternative display style of `Dataview` results. Most appropriate case of using is creating personal libraries.
![image](https://github.com/user-attachments/assets/77f006cc-be0b-4f69-ab98-bfcea79f863f)

# How it works
First of all this snippet was inspired my Minimal theme cards. It wark in with Daaview table changing its display view from table to cards.

# What is possible
- Changing card width
- Changing card background
- Changing image size
- Chaning gaps between rows and columns
- Changing border width
- Changing font-sizes
- e.t.c.

# Usage
1. Download and enable **Dataview plugin**, learn it.
2. Download **Cards.css** file and insert it in your folder e.g. `C:\Users\User\Obsidian_folder\.obsidian\snippets\Cards.css`
3. Enable snippet in `Settings > Appearance > CSS snippets`
4. Create new note with Dataview query. Below a demo dataview from screenshots.  (You can copy or download demo **Library_demo.md**)

```
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
5. Create a book note. (You can copy or download demo **Book_demo.md**)
```
---
tags:
  - book
aliases:
  - 전지적 독자 시점
year: "2018"
author:
  - Sing-Shong
series: ORV
series_part: "1"
started: 2023-10-10
finished: 
genres:
  - Fiction
  - Fantasy
  - Novell
volume: "551"
timestamp: "67"
units: chapters
status: ongoing
rate:
  - ★★★★★
cover: "[[Pasted image 20240714173312.png]]"
cssclasses:
---
![[Pasted image 20240714173312.png|300]]

# ANNOTATION
>Beautiful annotation would be placed here

# QUOTES
1. Don't forget your quotes

# NOTES
>Notes is a key to remembering everything

# CHARACTERS
1. Characters are characters

```




# To-Do
- [ ] Make adaptive cards for different resolutions(devices) e.g. @media (max-width: 400pt)
