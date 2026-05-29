# Obsidian CSS snippets

Obsidian CSS snippets I code and/or frankenstein together.
If applicable, the credits can be found down below and in the files.

I am by no means skilled in CSS, I am learning as I go.
If you found an issue, I can certainly take a look, but I may not be able to help you. We can always brainstorm together.
If you found a solution or something you would like to add or change, feel free to fork this repository and/or make a pull request.

---

## How to use

### Scrollable Callouts (based on breezy-codes Scrollable Callouts)

  This snippet adds the option to make your callouts scrollable.
  Unlike the original, you can add "scrollable" (w/o the "") to any callout, including custom ones.
  You don't need to alter the code of the orignal callouts at all.
  
  "scrollable" is added to the callouts metadata. This means you add an | after the callout type. See [examples](#examples) to see it in action.
  You can also specify 5 custom lengths by adding "#line-(1-5)" behind "scrollable" (again, w/o the "").

#### Style Settings

  This snippet is customizable with the plugin Style Settings (https://github.com/obsidian-community/obsidian-style-settings).
  To use this feature, you must have it installed and enabled.

  Within Obsidian, navigate to the Style Settings-settings. Here, you should see a new header called "Scrollable Callout".
  You can specify the different line lengths here, they will be used throughout your vault.
  
  - **Default Line Count**: Specify the line length you want to see when adding "scrollable" to a callout.
  - **Line Count (1-5)**: Specify the line length you want to see when adding "#line-length(1-5)" to a scrollable callout.
    
#### Examples:

  You can copy and paste these examples in your vault:
  
```
> [!note|scrollable] this is a title
> this is a body. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et
```
``` 
> [!tip|scrollable#length-3] this is a title
> this is a body. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et
``` 

### Further customization

You can always add or subtract new line count categories. To do this, open the .css file in a program like Visual Studio Code.
  
1. Copy and paste the following code in it, just under the list of similar looking code.
 
```
.callout[data-callout-metadata*="#line-{X}"] .callout-content {
    max-height: calc(var(--line-height-normal) * 1rem * var(--line-count{X}));
}
```

  Replace the {X} with a number not currently used. (6, for example.)
  You can also delete "#line-X" with something entirely different, but remember to alter the rest of the code accordingly. Keep the "".

2. Under the last item in body{} (on top of the page), add the following code.
   Remember to change the {X} to your number.
   
```
    --line-count{X}: {your desired default line length number here};
```
  
  #### Save the file. You can now use your newly specified snippet in your vault!

If you want to be able to customise your added option in Style Settings, add the following code to the @settings section.
The hypen at the end is important. Remember to change {X} to your number. To "default", add the number you specified in body{}.
   
```
            id: line-count{X}
            title: Line Count {X}
            type: variable-number
            default: 4
    -
```
Near the top of @settings, you see the following code:
  
```
        id: line-count-title
        title: Line Count Settings
        type: heading
        level: 5
        collapsed: true
```
Change "level: 5" to the amount of setting blocks now present under it.
If you followed the steps above and have added one block, the amount now is 6.

---

## How to install

Dektop:
1. Open Settings > icon.
2. Under Appearance → CSS snippets, select Open snippets folder > icon.
3. In the snippets folder, create a CSS file that contains your snippet.
4. In Obsidian, under Appearance → CSS snippets, select Reload snippets > icon to see the snippet in the list.
5. Enable snippet by clicking the toggle.
— https://obsidian.md/help/snippets

You can also navigate to the snippets folder in your file manager. Navigate into your vault folder, then into .obsidian.
Here you should find a folder labelled "snippets". If not, you can create one. Place the .css file in here.

The .obsidian folder is hidden by default (note the . on front). To make it visible, press CTRL + H. (On Linux atleast)

For mobile, please follow the instructions on the Obsidian Website linked above.

---

## Credits

1. calloutScrollable.css is based on Obsidian-Callouts by breezy-codes, available at https://github.com/breezy-codes/Obsidian-Callouts under GPLv3
    - the .css file explains the changes I made

---
## License

This project is licensed under GPLv3, as stated in LICENSE and below.
    
    Copyright (C) 2026 IamBugs

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
