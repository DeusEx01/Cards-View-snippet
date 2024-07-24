1. [About](#Cards-View-snippet)
   - [Showcase](#Some-popular-themes-with-the-snippet)
3. [How it works](#How-it-works)
4. [What is possible](#What-is-possible)
5. [Installation](#Installation)
6. [Usage](#Usage)
   - [Style Settings plugin](#Style-Settings-plugin)
   - [Dataview](#Dataview-query)
      - [span](#<span/>)
      - [Progress Bar](#Progress-Bar)
9. [Headers](#headers)
10. [Headers](#headers)


# Cards-View-snippet
*Click ★ if you liked the snippet*

This is a snippet for alternative display style of `Dataview` results. Most appropriate case of using is creating personal libraries.
Here is a demo result with quick shows case different themes:

**Desktop version**

![DEMO GIT 2](https://github.com/user-attachments/assets/3b93e913-b51d-4a51-adf4-791ebb376c81)

**Mobile version**

![image](https://github.com/user-attachments/assets/b365a371-5736-4f90-acac-2c8f45474831)

## Some popular themes with the snippet
(Default, AnuPpuccin, Vauxhall, 80s Neon, Subtlegold)

![image](https://github.com/user-attachments/assets/3849bd1b-e69b-45cb-97a7-fc470b0b5231)
![image](https://github.com/user-attachments/assets/a78f31dc-cc22-4cc8-a1d4-bdb9d0c31766)
![image](https://github.com/user-attachments/assets/e1f3cbc4-9186-49f1-abeb-4b198934f7e4)
![image](https://github.com/user-attachments/assets/df12c7ad-49c8-484f-9701-b003b5d0c3db)
![image](https://github.com/user-attachments/assets/eac0c333-dcb6-4d8d-b73e-1b3e6d8c0e0d)

And here is my personal tweaked snippet like a showcase(I've changed some stuff to my taste and you can do it too. See **Usage** section):

![image](https://github.com/user-attachments/assets/9f90822b-5f49-4439-b4d4-abe2a6ae13a9)


**Remember, it's a raw and new snippet, so there are some things that you and me don't expect <3**

# How it works
It works with Dataview table and changes its display view from table to cards.
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
> You can download demo vault https://github.com/DeusEx01/Cards-View-snippet/tree/main/Demo%20Vault

0. DOWNLOAD **Style Settings plugin** and turn it on (https://github.com/mgmeyers/obsidian-style-settings).
1. Download and enable **Dataview plugin**, learn it. (Some examples you can find in files)
2. Download **Cards.css** file (https://github.com/DeusEx01/Cards-View-snippet/blob/main/Cards.css) and insert it in your folder Obsidian's folder `snippets`(see documentantion https://help.obsidian.md/Extending+Obsidian/CSS+snippets) e.g. `C:\Users\User\Obsidian_folder\.obsidian\snippets\Cards.css`
3. Enable snippet in `Settings > Appearance > CSS snippets`
4. Create a book note. (You can copy or download demo **Omniscient Reader's Viewpoint.md**) https://github.com/DeusEx01/Cards-View-snippet/blob/main/Omniscient%20Reader's%20Viewpoint.md
Expected result: ![image|200](https://github.com/user-attachments/assets/59523ea8-2c90-4505-9723-346487332ce6)

5. Create new note with Dataview query. (https://github.com/DeusEx01/Cards-View-snippet/blob/main/Cards%20view.md) (You can copy or download demo **Cards view.md**)
Expected result: ![image|200](https://github.com/user-attachments/assets/91c4aad7-1336-4083-8e0f-917e6e4f59bf)
Now it's done and you can see a default cards view.

# Usage
## Style Settings plugin
1. Open **Style Settings** plugin. I'd recommend to open it in a split view.
   - Open **Command Palette** `Ctrl + P`
   - Insert `Style Settings: Show style settings view`
   - Now **Style Settings** are opened in new tab. Drag and drop the tab to the left or to the right
   - Now you can change style and see result. Convenient
   
![image](https://github.com/user-attachments/assets/a19f1760-ec9c-4cf3-924a-ba44dff413fb)
2. In **Style Settings** you can see two settings. For Desktop version and mobile version. `Cards snippet - DeusEx01` and `Mobile Cards snippet - DeusEx01` respectively.
> [!TIP]
> Mobile version is activated if width of screen less than 400 points. To change the width go to the snippet and find `@media(max-width:400pt)`, then change `max-width:` to your value.
3. If you want to restore default style click `Restore default` button:

![image](https://github.com/user-attachments/assets/ce569a55-8859-4454-a8a2-0d5958f1664f)

## Dataview query
> [!WARNING]
> Try to follow original format of cards.
> It includes
> 1. **Cover image**
> 2. **Link (note title)**
> 3. **Rows with additional information** 
> 4. **Progress bar**
>
> You can to not follow the template but I'm not sure in good visual result.

## `<span/>`
Dataview query is quite basic, the only thing I've added and what is not so common is `"<span " + "class='cards-icon'>" + "PROPERTY_NAME" + "</span>" + PROPERTY_VALUE as PROPERTY_NAME` code. Here you can define a name of property `PROPERTY_NAME` followed by its actual value `PROPERTY_VALUE` which is taken by Dataview query from your YAML properties. You can delete this  `"<span " + "class='cards-icon'>" + "PROPERTY_NAME" + "</span>" +` and leave only `PROPERTY_VALUE as PROPERTY_NAME`

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

## Some implicit styles
1. `Rows Before Clip` in **Title** and **Rows** sections. It allows you to say how many rows of text you want to see before it's clipped if it's too long. Last symbols are replaced with three dots `...`. By default 2 rows are shown. E.g.

![image](https://github.com/user-attachments/assets/1315d68b-9339-450c-bb78-f31efd2f001c)

2. **Property Name Style** is dedicated to text which contains name of property inside `"<span " + "class='cards-icon'>" + "Series" + "</span>"` code from demo version of Dataview. E.g.

![image](https://github.com/user-attachments/assets/5df360d1-6345-47ee-871b-5667fcbf1f71)

   - **Left Icon** and **Right Icon** are icons that surround **Property Name**. By default `•`. You can change it to any symbol or emoji e.g.
![image](https://github.com/user-attachments/assets/f94b8733-e263-4c01-bf9c-d7c349e8a034)

## Some support classes for `cssclasses` property.
 - `cards-readline-off` (breaks limits of option Readable line length so you can see library with full width.
 
![image](https://github.com/user-attachments/assets/dfb2fbcf-96e3-4fa9-acae-151f33329338)
Before: ![image|200](https://github.com/user-attachments/assets/c99be477-49f4-46a5-8eda-e1af3d066bcb)
After: ![image|200](https://github.com/user-attachments/assets/beb0ef09-b99e-401f-80b9-125578e9e8db)


# To-Do
- [x] Make adaptive cards (mobile version) for different resolutions(devices) e.g. @media (max-width: 400pt)
- [ ] Add font-family support via Style Settings
- [x] Make individual `.cards-icon` styles.
- [ ] Collect feedbacks and make a list of needed fixes/bugs.
- [x] Check popular themes and make better compability.
- [ ] Think about merging with MetaData + Dataview + Snippet (Right now it's too slow for working with)
- [ ] Change selector for readable line length to `--file-line-width` native variable
- [ ] Add changable styles for links inside rows
- [ ] Add an ability to add background for every single card(think about it)
- [ ] Add several hover animations
- [ ] Add 
