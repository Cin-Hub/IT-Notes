# Vim
- [Modes](vim.md#Modes)
- [Basic Triggers](vim.md#Basic%20Triggers)
- [Vim as Language](vim.md#Vim%20as%20Language)
- [Commands](vim.md#Commands)
- [Modifiers](vim.md#Modifiers)
- [Targets (Text objects)](vim.md#Targets%20(Text%20objects))
- [Nouns/Movements](vim.md#Nouns/Movements)
- [Useful](vim.md#Useful)
- [Registers](vim.md#Registers)
- [Others](vim.md#Others)
- [Deleting](vim.md#Deleting)
- [Change case](vim.md#Change%20case)
- [Notes](vim.md#Notes)
- [Commands](vim.md#Commands)
- [Substitute (search and replace)](vim.md#Substitute%20(search%20and%20replace))
- [Useful substitute commands](vim.md#Useful%20substitute%20commands)
- [Macros](vim.md#Macros)
- [Interesting resources](vim.md#Interesting%20resources)

## External links
- [vimhelp.org - Official online help](https://vimhelp.org)
- [duckduckgo.com - Vim Cheat Sheet](https://duckduckgo.com/?q=vim+cheat+sheet&ia=cheatsheet&iax=1)
- [quickref.me - Vim Cheat Sheet](https://quickref.me/vim)

Document Metainformations:
- "Triggers" -> Keys or Commands which indicate an action
- ":" -> Must be used in Command mode (`ESC`)

## Modes

| Trigger    | Description                                                                                                                                                                   |
| ---------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `i`        | Insert mode - Insert text in a document. The shortcut is: "i" (insert text where the cursor is) or "o" (insert text at the beginning of the following line).                  |
| `V`        | Visual mode - Permits the user to select the text as you would do with a mouse but using the keyboard instead of the mouse. Useful to copy several lines of text for example. |
| `ESC`      | Normal mode - When you are in another mode you can use the escape key (sometimes you'll need to hit it twice) to come back to the normal mode at any time.                    |
| `ctrl`+`v` | Visual block mode.                                                                                                                                                            |
| `q`        | Macro mode - in this mode you are recording a macro (check out the [Macros](vim.md#Macros) section below)                                                                     |
| `:`        | Command mode - type `help <ENTER>` in command mode, to enter the internal vim manual.                                                                                         |

## Basic Triggers

| Trigger | Description                               |
| ------- | ----------------------------------------- |
| :`w`    | save                                      |
| :`q`    | quit                                      |
| :`q!`   | force quit and throw away unsaved changes | 
| :`wq`   | save and quit                             |
| :`x`    | save and quit (alternative)               |
| !       | force command (example :`q!`)             |
| `y`     | copy                                      |
| `yy`    | copy a line                               |
| `p`     | paste                                     |
| `d`     | cut                                       |
| `dd`    | cut a line                                |

## Vim as Language

Vim commands are formed from a combination of verbs and targets. The targets could be objects (words, sentences, paragraphs, lines, the contents of parentheses) or movements (jump to the end of a word, jump to end of the paragraph, jump forward until the letter ‘e’, etc). Forming objects generally involves the use of a modifier. You can also add a count to perform the action count times.

### Commands

| Trigger        |     Description                                                                |
|---------|---------------------------------------------------------------------|
| v       | enter visual mode                                                   |
| V       | enter visual mode and select current line                           |
| c       | change                                                              |
| cc      | delete current line and then enter insert mode                      |
| C       | Delete from the cursor position to the end of the line then enter insert mode |
| d       | delete (remove from the document and put in buffer)                 |
| dd      | delete current line                                                 |
| D       | Delete from the cursor position to the end of the line              |
| y       | yank/copy                                                           |
| yy or Y | yank/copy the line                                                  |
| i       | enter insert mode                                                   |
| I       | enter insert mode at the beginning of the line                      |
| p       | paste the buffer after the cursor                                   |
| P       | paste the buffer before the cursor                                  |
| r\[char\] | replace the character under the cursor \[char\]                       |
| R       | enter Replace mode                                                  |
| s       | delete the character under the curser and puts you into insert mode |
| S       | delete current line and then enter insert mode (same as `cc`)       |
| x       | delete the character under the cursor                               |
| u       | undo the last command                                               |
| a       | append and enter insert mode after the carat                        |
| A       | append to line (enter insert mode at the end of the line)           |
| o       | open a line after the current one and enter insert mode             |
| O       | open a line before the current one and enter insert mode            |

### Modifiers

| Trigger        |                Description                               |
|---------|-----------------------------------------------|
| i       | inside                                        |
| a       | around                                        |
| t\[char\] | till... finds a character                     |
| T\[char\] | like t but in opposite direction              |
| f\[char\] | find... like till except including the \[char\] |
| F\[char\] | like f, but in opposite direction             |
| /       | search...find a string/regex                  |
| ?       | like / but in opposite direction              |

### Targets (Text objects)

| Trigger  |   Description                                                                                |
|---|-----------------------------------------------------------------------------------|
| w | word                                                                              |
| W | WORD (consists of a sequence of non-blank characters, separated with white space) |
| s | sentence                                                                          |
| p | paragraph                                                                         |
| b | block/parentheses                                                                 |
| t | tag, works for html/xm                                                            |

## Nouns/Movements

Nouns or movements are commands for moving within the document or representing an area within a document.

| Trigger     | Description                                                           |
| ----------- | --------------------------------------------------------------------- |
| h, j, k, l  | move, equivalent to the arrow keys left, down, up, right              |
| H           | move to the top of screen                                             |
| M           | move to the middle of screen                                          |
| L           | move to the bottom of screen                                          |
| zz          | scroll the line with the cursor to the center of the screen           |
| zt          | scroll the line with the cursor to the top                            |
| zb          | scroll the line with the cursor to the bottom                         |
| gg          | go to the first line                                                  |
| G           | go to the last line                                                   |
| Ctrl-D      | move half-page down                                                   |
| Ctrl-U      | move half-page up                                                     |
| Ctrl-B      | page up                                                               |
| Ctrl-F      | page down                                                             |
| 0           | move to the very beginning of the current line                        |
| ^           | move to the first non-whitespace character on the line                |
| $           | move to the end of the line                                           |
| w, b        | move to the next/previous word                                        |
| W, B        | as w/b only Words are bigger                                          |
| ), (        | move to the next/previous sentence                                    |
| }, {        | move to the next/previous paragraph                                   |
| /\[regexp\] | like t but instead of finding a character, it finds a regexp          |
| ?\[regexp\] | like `/`, but search in opposite direction                            |
| %           | jump to the matching parenthesis (vim understands nested parenthesis) |
| _           | move to the current line (useful for making commands line-based)      |
| \#\[char\]  | jump to the previous instance of the word under \[char\]              |
| >>          | indent line (shift line one shiftwidth rightwards)                    |
| <<          | outdent line (shift line one shiftwidth leftwards)                    |
| ==          | reindent current line                                                 |
| *\[char\]   | jump to the next instance of the word under \[char\]                  |
| ddp / ddkP  | are common commands to move a line one down / up                      |

# Useful

|   trigger       |   Description                                                                                                                                  |
|----------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|
| vi\[char\] | visualize all content inside that \[char\] excluding delimiter                                                                                              |
| va\[char\] | visualize all content inside that \[char\] including delimiter                                                                                              |
| vi{      | select all content inside curly braces excluding braces                                                                                                   |
| va{      | select all content inside curly braces including braces                                                                                                   |
| viw      | select world under the cursor                                                                                                                             |
| vit      | visually select text in a tag                                                                                                                             |
| vat      | visually select text around a tag                                                                                                                         |
| vap      | visually select paragraph under cursor                                                                                                                    |
| gc       | toggles line comment, example `gcc` to toggle line comment for the current line and `gc2j` to toggle line comments for the current line and the next line |
| gC       | toggles block comment, example `gCi` to comment out everything within parenthesis                                                                         |
| ciw      | change inner word will change the whole word under the cursor                                                                                             |
| cw       | change the word from the current cursor position                                                                                                          |
| /        | enter regex search mode                                                                                                                                   |
| n        | find the next instance of the search term                                                                                                                 |
| N        | find the previous instance of the search term                                                                                                             |
| .        | repeat last change (extremely powerful)                                                                                                                   |
| ^ or 0   | move to the beginning of the line                                                                                                                         |
| Shift+0  | move to the end of the line                                                                                                                               |
| Shift+i  | move to the beginning of the line and switch to insert mode                                                                                               |
| Ctrl-R   | redo the last undo (sidenote: in vim undo/redo forms a tree, changes aren’t lost)                                                                         |
| Ctrl-\[   | exit insert mode                                                                                                                                          |
| Ctrl-c   | exit insert mode                                                                                                                                          |
| Ctrl-ww  | window switching                                                                                                                                          |
| gg=G     | Autoformat/indent code                                                                                                                                    |


</br>

## Registers

Registers in Vim let you run actions or commands on text stored within them. To access a register, you type `a` before a command, where a is the name of a register.
Please, note some of these commands are not supported by VSCodeVim yet.

| Trigger     |     Description                                                                                  |
|------|---------------------------------------------------------------------------------------|
| :reg | access all currently defined registers                                                |
| "kyy | copy the current line into register `k`                                               |
| "Kyy | append to a register by using a capital letter                                        |
| "kp  | paste value of the register                                                           |
| "+p  | paste from system clipboard on Linux                                                  |
| "*p  | paste from system clipboard on Windows (or from "mouse highlight" clipboard on Linux) |

## Others

| Trigger   | Description                                                                       |
| --------- | --------------------------------------------------------------------------------- |
| dat       | delete the current tag (and all its content)                                      |
| f\[char\] | find character and move cursor at position \[char\]                               |
| t\[car\]  | find character and move cursor at one position before \[char\]                    |
| vi\[      | visual select inside `[`                                                          |
| i\[car\]  | expand selection to that \[char\], similar including `a\[char\]`                  |
| gt        | move the cursor to next tab                                                       |
| gT        | move the cursor to prior tab                                                      |
| nnngt     | numbered tab                                                                      |
| :tabonly  | close all tabs and keep open only the focused one                                 |
| :split    | split into two windows, top half and bottom half                                  |
| :sp       | same as :split                                                                    |
| :vsplit   | split into two windows, left and right                                            |
| :vsp      | same as :vsplit                                                                   |
| :sp       | spit current document in two horizontally                                         |
| :vs       | spit current document in two vertically                                           |
| Ctrl-y    | move the screen up one line                                                       |
| Ctrl-e    | move the screen down one line                                                     |
| Ctrl-u    | move cursor & screen up ½ page                                                    |
| Ctrl-d    | move cursor & screen down ½ page                                                  |
| Ctrl-b    | move the screen up one page, cursor to the last line                              |
| Ctrl-f    | move the screen down one page, cursor to the first line                           |
| Ctrl-y    | only change the cursor position if it would be moved off-screen, same as Ctrl-e   |
| zt        | move current line to the top of the screen                                        |
| zb        | move current line to the bottom of the screen                                     |
| t         | till, example dt. (delete till dot) or df.(delete till dot included)              |
| Ctrl-O    | retrace your movements in file in backward                                        |
| Ctrl-I    | retrace your movements in file in forwards                                        |
| J         | joins the line the cursor is on with the line below                               |
| viwp      | visual select inner word and paste (change a selected word using current buffer ) |
| "+y       | copy to clipboard                                                                 |
| "+p       | paste to clipboard                                                                |

### Deleting

| Trigger | Description                                                                         |
| ------- | ----------------------------------------------------------------------------------- |
| dw      | delete from the current cursor position to the beginning of the next word character |
| diw     | delete inner word will delete the whole word under the cursor                       |
| d$      | delete from the current cursor position to the end of the current line              |
| D       | as d$                                                                               |
| dtX     | delete forward up to character X                                                    |
| dfX     | delete forward through character X                                                  |
| dTX     | delete backward up to character X                                                   |
| dFX     | delete backward through character X                                                 |
| :%d     | delete all content of the document                                                  |

### Change case

| Trigger | Description                                               |
| ------- | --------------------------------------------------------- |
| ~       | changes the case of current character                     |
| guu     | change the current line from upper to lower               |
| Vu      | change the current line from upper to lower, like guu     |
| gUU     | change the current line from lower to upper               |
| VU      | change the current line from lower to upper, like gUU     |
| guw     | change to the end of current word from upper to lower     |
| guaw    | change all of the current word to lower.                  |
| gUw     | change to the end of the current word from lower to upper |
| gUaw    | change all of the current word to upper                   |
| g~~     | invert case to entire line                                |
| guG     | change to lowercase until the end of document             |

### Notes

- The quickest way to retrace your movements is to hit either: two apostrophes or two backticks. The difference is that the backtick goes to the same location on the line, whereas the apostrophe goes to the start of the line. There are loads of useful marks like this, see :help mark-motions.
- Move to the end of the line in normal mode in VIM: Jump to last nonblank g_ or use $ which moves to the last character on the line.
- You can use Ctrl-W direction to switch windows (where direction is one of the normal hjkl cursor movement keys, or the arrow keys).
- The focus is on the new split initially. To move between splits first press Ctrl-w.

# Commands

##### Open vim manual:
```
:help
```

##### Display vim options:
```
" brief descriptions of all options
:options

" currently modified options
:set

" all current option settings
:set all
```

##### Wrap lines, to fit in window (effects view, not the buffer):
```vim
:set wrap
:set nowrap
" don't wrap in the middle of a word
:set linebreak
```

##### Map a macro (`z`) to a F-Key (`<F9>`):
```
:map <F9> @z
```
_Yes, the [<> notation](https://vimhelp.org/intro.txt.html#%3C%3E) can be used here. But you need to escape `<` and `\`, like so: `\<` and `\\`_

##### Display registers:
```
" display all
:reg

" dispay register z
:reg z
```

##### Go to line 42:
```
:42

" or in normal mode
42G
```

# Substitute (search and replace)

[vimhelp.org - change.txt #substitute](https://vimhelp.org/change.txt.html#%3Asubstitute)

Change each foo to bar, but ask for confirmation first:  
```shell
:%s/foo/bar/gci
```

| Flag | Description                                |
|:----:| ------------------------------------------ |
|  g   | global – each match in the line is changed |
|  c   | confirmation needed for each change        |
|  i   | case insensitive (ignore case)             |
|  e   | don't issue an error message and continue  | 

See also [RegEx](../misc/RegEx.md)

## Useful substitute commands

Remove all whitespaces at the end of line:
```bash
%s/\s\+$//e
```

Replace multiple empty lines with one:
```bash
%s/^\n\{2,\}/\r/e
```

Markdown - remove empty lines between bullet points:
```bash
%s/^\(- .\+\n\)\n\+\(- .\+\n\)/\1\2/ge | %&& | %&&
```

# Macros

- [vimhelp.org - Complex repeats](https://vimhelp.org/repeat.txt.html#complex-repeat)
- [GitHub.com - iggredible / Learn-Vim : ch09_macros](https://github.com/iggredible/Learn-Vim/blob/master/ch09_macros.md)

## Recording macros

0. Enter the normal mode `<ESC>`.
1. Hit `q`.
2. Hit a lower case character (a-z) as the macro register/name (e.g. `a`). The recording has now started!
3. Execute the tasks you want to record.
4. When done with recording, enter the normal mode `<ESC>`.
5. Hit `q`. The recording has now stopped. The macro is saved under the register (e.g. `a`)

## Executing macros

You need to be in normal mode `<ESC>` to execute macros.

| Trigger              | Description                                                                        |
| -------------------- | ---------------------------------------------------------------------------------- |
| `@<macro-register>`  | Execute Macro which has the register/name `<macro-register>` (e.g. `@a`).          |
| `5@<macro-register>` | Execute Macro which has the register/name `<macro-register>` 5 times (e.g. `5@a`). |
| `@@`                 | Rerun the macro which has been run as last.                                        |

## Examples

##### Adding `> ` at the beginning of lines (quote in markdown)

Recording the macro:

0. `<ESC>` - entered normal mode
1. `qa` - started recording macro with the name/register `a`
2. `I` - entered insert mode at the beginning of the line
3. `> ` - inserted a greater-than symbol and a space
4. `<ESC>` - entered normal mode
5. `j0` - moved one line down `j` and then to the beginning of the line `0`
6. `q` - stopped recording the macro

Executing the macro

0. Enter normal mode `<ESC>`
1. Place the cursor on the line you want to quote (put `> ` the the beginning)
2. Execute the macro
    - `@a` to "quote" one line
    - `7@a` to "quote" 7 consecutive lines
        - `@@` need one more
        - `42@@` oops, I've meant 42 more lines

## Editing a macro

Macros are saved in [registers](https://vimhelp.org/change.txt.html#%3Aregisters). To list registers execute:
```
# display all registers
:reg

# display a specific register z
:reg z
```

Let's assume we want to change the macro `@z`:

0. Place cursor on an empty line
1. `"zp` - pastes the content of the register `z` after the cursor ([vimhelp.org](https://vimhelp.org/change.txt.html#put))
2. Edit the macro
3. Mark the whole macro in visual (`v`) mode
4. `"zy` - copies (yanks) the marked content to the register `z` ([vimhelp.oeg](https://vimhelp.org/change.txt.html#yank))

## Writing a macro by hand

Assuming we want a macro `z` which copies the current line and inserts a commented out (`#`) copy above. The command `:` would look something like this:
```
let @z='yyPI# ^['
```
_`^[` is the character for the `[Esc]` switch - check out the **tip** below._

If you add this command to your vimrc file, then the macro will be loaded to the register `z` every time you start vim.

> [!tip]
> 
> To insert the character of a switch like `[Esc]` or `[Enter]` you need to use the "verbatim insert" (default: `Ctrl`+`v`).
> 
> So when you hit `Ctrl`+`v` and then `[Esc]` in vim's insert mode, you should get the `^[` symbol. This is the Escape Switch symbol and it's not the same as simply typing the `^` and `[` symbols.
> 
> See the section about ["\<\> notation" in the vim manual](https://vimhelp.org/intro.txt.html#%3C%3E) for further details.

# Interesting resources

- [vimhelp.org - Official online help](https://vimhelp.org)
- [DuckDuckGo.com - Vim Cheat Sheet](https://duckduckgo.com/?q=vim+cheat+sheet&ia=cheatsheet&iax=1)
- [vim.wikia.com - Using marks](http://vim.wikia.com/wiki/Using_marks)
- [YouTube.com - Vim + Tmux](https://www.youtube.com/watch?v=5r6yzFEXajQ&t=1269s)
- [YouTube.com - Mastering the Vim Language](https://www.youtube.com/watch?v=wlR5gYd6um0)
- [vim.fandom.com - All the right moves](https://vim.fandom.com/wiki/All_the_right_moves)
- [eggplant.pro - Graphical cheat sheet](https://eggplant.pro/blog/wp-content/uploads/2016/12/vi-vim-tutorial.pdf)
- [YouTube.com - Vim Visual Block Mode](https://www.youtube.com/watch?v=Ydzw70SvF-g)
- [SpaceVim.org - A community-driven vim distribution](https://spacevim.org/)
- [freeCodeCamp.org - Vimrc Configuration Guide](https://www.freecodecamp.org/news/vimrc-configuration-guide-customize-your-vim-editor/)
- [vimcasts.org - Learn Essential Vim Skills with Drew Neil, author of Practical Vim](http://vimcasts.org/)