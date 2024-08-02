1. [About](#Cards-View-snippet)
   - [Showcase](#Some-popular-themes-with-the-snippet)
3. [How it works](#How-it-works)
4. [What is possible](#What-is-possible)
5. [Installation](#Installation)
6. [Usage](#Usage)
   - [Style Settings plugin](#Style-Settings-plugin)
   - [Dataview](#Dataview-query)
      - [span](#Span-Tag)
      - [Progress Bar](#Progress-Bar)
9. [Implicit settings](#Implicit-settings)
10. [Support cssclasses](#Support-classes)
11. [todo/future features](#TODO)


# Cards-View-snippet
*Click ★ if you liked the snippet*

This is a snippet for alternative display style of `Dataview` results. Most appropriate case of using is creating personal libraries.
Here is a demo result with quick show case for different themes:

**Desktop version**

![DEMO GIT 2](https://github.com/user-attachments/assets/3b93e913-b51d-4a51-adf4-791ebb376c81)

Here is how you can use it with Tabs plugin.

![Tabs plugin + cards snippet](https://github.com/user-attachments/assets/24442df2-0dab-4fb5-97cd-2743c3112d08)

**Mobile version**

<img width=300 height=auto src="https://github.com/user-attachments/assets/b365a371-5736-4f90-acac-2c8f45474831"/>


## Some popular themes with the snippet
(Default, AnuPpuccin, Vauxhall, 80s Neon, Obsidian Nord)

![Images compilation](https://github.com/user-attachments/assets/ddcd8be8-e269-4106-889f-51658bb386ad)





**Remember, it's a raw and new snippet, so there are some things that you and me don't expect <3**

# How it works
It works with [Dataview](https://github.com/blacksmithgu/obsidian-dataview) table and changes its display view from table to cards. Also there are supporting plugin: [Style Settings](https://github.com/mgmeyers/obsidian-style-settings), [Tabs](https://github.com/xhuajin/obsidian-tabs) and [Book Search](https://github.com/anpigon/obsidian-book-search-plugin)
> [!TIP]
> You can download a **Hover Editor** plugin and be able to edit your notes without opening it in a new tab.

# What is possible
- Changing card width
- Changing card background
- Changing image size
- Chaning gaps between rows and columns
- Changing border width
- Changing font-sizes
- Changing icons
- Changing Mobile style
- and more

# Installation
> [!TIP]
> You can download vault as whole. It has everything described below(plugins/templates). Click this button and download zip -> Open as a new vault in Obsidian as a new vault via **Manage vault**
> ![image](https://github.com/user-attachments/assets/9c9bb2d5-d44d-4e6a-b6e1-8118a0944f81)


0. DOWNLOAD **Style Settings plugin** and turn it on (https://github.com/mgmeyers/obsidian-style-settings).
1. Download and enable **Dataview plugin**, learn it. (Some examples you can find in files)
2. Download file [**Cards.css**](https://github.com/DeusEx01/Cards-View-snippet/blob/main/.obsidian/snippets/Cards.css) and insert it in your Obsidian's folder `snippets`(see documentantion https://help.obsidian.md/Extending+Obsidian/CSS+snippets) e.g. `C:\Users\User\Obsidian_folder\.obsidian\snippets\Cards.css`
3. Enable snippet in `Settings > Appearance > CSS snippets`
4. Create a book note. (You can copy or download demo [Demo Book](https://github.com/DeusEx01/Cards-View-snippet/blob/main/Books/Omniscient%20Reader's%20Viewpoint.md)
Expected result: ![image|200](https://github.com/user-attachments/assets/59523ea8-2c90-4505-9723-346487332ce6)

> [!TIP]
> Don't forget about property `cssclasses: cards` and `cards-readline-off` in your note with library

6. Create new note with Dataview query. [Demo Library](https://github.com/DeusEx01/Cards-View-snippet/blob/main/Cards%20view.md)
Expected result: ![image|200](https://github.com/user-attachments/assets/91c4aad7-1336-4083-8e0f-917e6e4f59bf)
Now it's done and you can see a default cards view.

# Usage
## Style Settings plugin
1. Open **Style Settings** plugin. I'd recommend to open it in a split view.
   - Open **Command Palette** `Ctrl + P`
   - Insert `Style Settings: Show style settings view`
   - Now **Style Settings** are opened in new tab. Drag and drop the tab to the left or to the right
   - Now you can change style and see result. Convenient

 ![Style Settings demo](https://github.com/user-attachments/assets/621a0fcd-1048-4681-99f1-5c9bb4eca84d)
  

2. In **Style Settings** you can see two settings. For Desktop version and mobile version. `Cards snippet - DeusEx01` and `Mobile Cards snippet - DeusEx01` respectively.
> [!TIP]
> Mobile version is activated if width of screen less than 400 points. To change the width go to the snippet and find `@media(max-width:400pt)`, then change `max-width:` to your value.
3. If you want to restore default style click `Restore default` button:

![image](https://github.com/user-attachments/assets/ce569a55-8859-4454-a8a2-0d5958f1664f)

## Dataview query
> [!WARNING]
> Try to follow original format of cards.
> It includes
> 1. **Cover image** (important)
> 2. **Link (note title)** (important)
> 3. **Rows with additional information** (can be omitted)
> 4. **Progress bar** (can be omitted)
>
> You can to not follow the template but I'm not sure in good visual result.

## Span Tag
Dataview query is quite basic, the only thing I've added and what is not so common is 
```css
"<span " + "class='cards-icon'>" + "PROPERTY_NAME" + "</span>" + PROPERTY_VALUE as PROPERTY_NAME
```
Here you can define a name of property `PROPERTY_NAME` followed by its actual value `PROPERTY_VALUE` which is taken by Dataview query from your YAML properties. You can delete this  `"<span " + "class='cards-icon'>" + "PROPERTY_NAME" + "</span>" +` and leave only `PROPERTY_VALUE as PROPERTY_NAME`

## Progress Bar
```js
"<progress max=" + 
volume + " value=" + number(
timestamp) + "> </progress> "  + number(
timestamp) + " of " + number(
volume) + " " + 
units + " (" +round(number(
timestamp)/number(
volume)*100) + "%" + ")" as Progress
```

Where
1. `volume` - *yaml property* where you store a total number of pages, chapters, episodes and so on. It has to be a `number` value
2. `timestamp` - *yaml property* where you store your current page, chapter, episode and so on. It has to be a `number` value
3. `units` - *yaml property* where you store your name of units. How you measure your book or series. (e.g. book and chapters, series and eposodes). It has to be a `text` value


## Implicit settings
1. `Rows Before Clip` in **Title** and **Rows** sections. It allows you to say how many rows of text you want to see before it's clipped if it's too long. Last symbols are replaced with three dots `...`. By default 2 rows are shown. E.g.

![image](https://github.com/user-attachments/assets/1315d68b-9339-450c-bb78-f31efd2f001c)

2. **Property Name Style** is dedicated to text which contains name of property inside `"<span " + "class='cards-icon'>" + "Series" + "</span>"` code from demo version of Dataview. E.g.

![image](https://github.com/user-attachments/assets/5df360d1-6345-47ee-871b-5667fcbf1f71)

   - **Left Icon** and **Right Icon** are icons that surround **Property Name**. By default `•`. You can change it to any symbol or emoji e.g.
![image](https://github.com/user-attachments/assets/f94b8733-e263-4c01-bf9c-d7c349e8a034)

## Support classes
 - `cards-readline-off` (breaks limits of option Readable line length so you can see library with full width.
 
![image](https://github.com/user-attachments/assets/dfb2fbcf-96e3-4fa9-acae-151f33329338)
Before: ![image|200](https://github.com/user-attachments/assets/c99be477-49f4-46a5-8eda-e1af3d066bcb)
After: ![image|200](https://github.com/user-attachments/assets/beb0ef09-b99e-401f-80b9-125578e9e8db)


# TODO
- [x] Make adaptive cards (mobile version) for different resolutions(devices) e.g. @media (max-width: 400pt)
- [x] Add font-family support via Style Settings (cancelled)
- [x] Make individual `.cards-icon` styles.
- [x] Collect feedbacks and make a list of needed fixes/bugs. (no feedbacks ;c)
- [x] Check popular themes and make better compability.
- [x] Think about merging with MetaData + Dataview + Snippet (Right now it's too slow for working with). Made test version with `dwjs` and `db.markdownTable`, non-public
- [x] Change selector for readable line length to `--file-line-width` native variable
- [x] Add changable styles for links inside rows (canceled)
- [x] Add an ability to add background for every single card(think about it) (canceled)
- [x] Add several hover animations (underway in other repo)
