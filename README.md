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

# Installation
1. Download and enable **Dataview plugin**, learn it.
2. Download **Cards.css** file and insert it in your folder e.g. `C:\Users\User\Obsidian_folder\.obsidian\snippets\Cards.css`
3. Enable snippet in `Settings > Appearance > CSS snippets`
4. Create a book note. (You can copy or download demo **Omniscient Reader's Viewpoint.md**)
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
cover: https://dn-img-page.kakao.com/download/resource?kid=z48Gf/hyxJFaD6gv/vikqKckSp6ZduKfoKLH6Ik&amp;filename=th3
cssclasses:
---


# ANNOTATION
>Beautiful annotation would be placed here

# QUOTES
1. Don't forget your quotes

# NOTES
>Notes is a key to remembering everything

# CHARACTERS
1. Characters are characters

```
Expected result: ![image|200](https://github.com/user-attachments/assets/59523ea8-2c90-4505-9723-346487332ce6)
5. Create new note with Dataview query. Below a demo dataview from screenshots.  (You can copy or download demo **Cards view.md**)

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
Expected result: ![image|200](https://github.com/user-attachments/assets/91c4aad7-1336-4083-8e0f-917e6e4f59bf)
Now it's done and you can see a default cards view.

# Usage
Now it's time to change cards to your taste.

There are some basic tweaks, that we can apply using YAML property `cssclasses`. In YAML property `cssclasses`, by default if you downloaded demo is stored 1 value `cards`. It enables the whole snippet on specific note.
![image|200](https://github.com/user-attachments/assets/556ce3c8-0cba-402c-a5cd-6387c597da49)
There are also some additional values
1. text-left (text aligns to left)
2. text-right (text aligns to right)
3. cards-readline-off (breaks limits of option Readable line length so you can see library with full width. ![image](https://github.com/user-attachments/assets/dfb2fbcf-96e3-4fa9-acae-151f33329338)
Before: ![image|200](https://github.com/user-attachments/assets/c99be477-49f4-46a5-8eda-e1af3d066bcb)
After: ![image|200](https://github.com/user-attachments/assets/beb0ef09-b99e-401f-80b9-125578e9e8db)
That's it for basic things.

Now if we want to change colors, border-width, width of cards, gaps between cards and so on, follow next steps:
1. Find and open downloaded `Cards.css` snippet with any code redactor (I use a VS code)
2. Scroll down to 22nd line ![image](https://github.com/user-attachments/assets/51562121-fafc-4f1b-9e3d-2a0c166954dd)

Here are placed some basic styles to your convenience. Lets check a few lines
1. `--cards-min-width: 200px;` changing 200px to your number we can narrow or widen width of cards.
200px: 
![image|200](https://github.com/user-attachments/assets/ccde1a5f-fc17-46e4-b66c-df97ceb0d73e)
350px:
![image|200](https://github.com/user-attachments/assets/b44bd89d-7230-4740-94b1-dc5eb0dc3b8d)
2. `--cards-border-color: purple;` and `--cards-progressbar-color: lightgreen;`
![image"200](https://github.com/user-attachments/assets/924e9c80-b8d3-4f6f-b0e9-441b33e18f6c)
3. `--cards--header-lines-hide: 2;` and `--cards-lines-hide: 2;`. These styles allow to say how many rows we want to see before it's trucated **if it's too long**. E.g. we have value 1 in first property, it means if link text is too long for 1 row then last symbols are replaced with `...` at the end 
Original link text ![image](https://github.com/user-attachments/assets/e897e1c1-de84-43f6-a359-aba743ca4fa1)
Long text with 2+ rows ![image](https://github.com/user-attachments/assets/b25ef864-3f99-46b2-b44a-053261d182fb)
Long text with 1+ rows ![image](https://github.com/user-attachments/assets/8f448762-c740-482c-9c1c-fbc34b4ce64f)

> I tried to name styles very understandable so it's easy to find needed one. Good luck.


# To-Do
- [ ] Make adaptive cards for different resolutions(devices) e.g. @media (max-width: 400pt)
