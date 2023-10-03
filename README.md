# Vim Cheat Sheet 

This is my personal Vim commands cheat sheet, what I use on a regular basis. This is not meant to be a complete list of all available commands I use for the different work I have to do (coding in different languages & text writing).

Most of the commands are Vi commands, some are specific to Vim. All works on Vim and VS Code with the Vim motions extensions.

This cheatsheet is organized in the different main Vim modes: Normal, Insert, Visual, Command-line and Ex modes.

## Operators, Counts and Motions

Vim commands are composed of three things:

 * `[Operator][Counts][Motions]`

Operators are: `delete`, `change` or `yank` (_copy_)
Counts: some numbers
Motions: a range of movement motions within the editor

Both `operators` and `counts` are *optional*. This means that those two commands are equivalent: `2cw` and `c2w`.


## Normal mode

### Editing

| Text Object                     | Change      | Delete      | Copy         | Description                                                      |
| ------------------------------- | ----------- | ----------- | ------------ | ---------------------------------------------------------------- |
| One word                        | `cw`        | `dw`        | `yw`         | Affect one word. `cw` will switch to `INSERT` mode.              |
| Two words, whitespace seperated | `c2W`       | `d2W`       | `2yW`        | Affect two words seperated by a whitespace                       |
| One line                        | `cc`        | `dd`        | `yy` or `Y`  | Affect a full line                                               |
| To end of line                  | `c$` or `C` | `d$` or `D` | `y$`         | Affect from the cursor to the end of the line                    |
| To begining of the line         | `c0`        | `d0`        | `y0`         | Affect from the cursor to the begining of the line               |
| Single character                | `r`         | `x` or `X`  | `yl` or `yh` | Affect a single character, the one under the cursor              |
| 4 Characters                    | `4s`        | `5x`        | `5yl`        | Affect `x` number of characters, from the position of the cursor |

### Code specific editing

| Text Object       | Command        | Notes                                                                                                                                                                                                                                        |
| ----------------- | -------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Line              | `gc`           | Toggles line comment. For example `gcc` to toggle line comment for current line and `gc2j` to toggle line comments for the current line and the next two lines. From [vim-commentary](https://github.com/tpope/vim-commentary)               |
| Block             | `gC`           | Toggles block comment. For example `gCi)` to comment out everything within parentheses. From [vim-commentary](https://github.com/tpope/vim-commentary)                                                                                       |
| Function argument | `<operator>ia` | Perform an operation on an argument of a function. This one exludes arguments separators. `cia` - change the argument under the cursor while preserving separators like comma `,`. From [targets.vim](https://github.com/wellle/targets.vim) |
| Function argument | `<operator>aa` | Perform an operation on an argument of a function. This one includesarguments separators. `daa` will delete the whole argument under the cursor and the separators if applicable. From [targets.vim](https://github.com/wellle/targets.vim)  |
| Word              | `gb`           | Adds another cursor on the next word it finds which is the same as the word under the cursor. First `gb` shows the selection, second time `gb` it creates the actual cursor. *VS Code specific*                                              |
| Word              | `gh`           | Equivalent to hovering your mouse over wherever the cursor is. Handy for seeing types and error messages without reaching for the mouse! *VS Code specific* |

### Editing Actions

| Command | Notes                                                        |
| ------- | ------------------------------------------------------------ |
| `u`     | Undo the last action                                         |
| `U`     | Undo all the changes on the current line                     |
| `i`     | Insert text at the current position                          |
| `I`     | Insert text at the begining of the line                      |
| `a`     | Append text after the current position                       |
| `A`     | Append text at the end of the line                           |
| `o`     | Open a new line below the current line                       |
| `O`     | Open a new line above the current line                       |
| `r`     | Replace a single character under the cursor                  |
| `R`     | Overstrike existing characters with new text                 |
| `x`     | Delete a single character under the cursor                   |
| `X`     | Delete a single character before the cursor                  |
| `J`     | Join the current line with the next line                     |
| `~`     | Switch case of the character under the cursor                |
| `g~`    | Switch the case of the current word                          |
| `guw`   | Change the word to lower case                                |
| `gUw`   | Change the word to UPPER case                                |
| `s`     | Delete the current character and enter insert mode           |
| `S`     | Delete the current line and enter insert mode                |
| `p`     | Paste register to a new line below the cursor                |
| `P`     | Paste register to a new line above the cursor                |
| `.`     | Repeat the last action                                       |
| `gi`    | Insert at the place at which yhou were last editing the file |
| `gI`    | Insert at the beggining of the line                          |

### Movements

| Movement                                           | Commands   |
| -------------------------------------------------- | ---------- |
| Move Left                                          | `h`        |
| Move Right                                         | `l`        |
| Move Up                                            | `k`        |
| Move Down                                          | `j`        |
| To first character of the line                     | `+`        |
| To first character of the previous line            | `-`        |
| To en of word                                      | `e` or `E` |
| To beginning of word                               | `w` or `W` |
| To a particular line `n`                           | `nG`       |
| To begining of the file                            | `gg`       |
| To the end of a file                               | `G`        |
| Move to the middle of the line of the screen       | `gm`       |
| Scroll to the top of the screen                    | `H`        |
| Scroll to the middle of the screen                 | `M`        |
| Scroll to the bottom of the screen                 | `L`        |
| Move to column `n`                                 | `n\|`      |
| Move to beginning of current sentence              | `(`        |
| Move to beginning of the next sentence             | `)`        |
| Move to beginning of current paragraph             | `{`        |
| Move to beginning of the next paragraph            | `}`        |
| Move to the beginning of current section           | `[[`       |
| Move to the beginning of the next section          | `]]`       |

### Search

| Commands                                                              | Notes      |
| --------------------------------------------------------------------- | ---------- |
| Search forward for pattern                                            | `/pattern` |
| Search backward for pattern                                           | `?pattern` |
| Repeat last search                                                    | `n`        |
| Repeat last search in opposite direction                              | `N`        |
| Search forward for word under cursor                                  | `*`        |
| Search barkward word under cursor                                     | `#`        |
| Search forward for word under cursor. Can be embedded in other words  | `g*`       |
| Search backward for word under cursor. Can be embedded in other words | `g#`       |
| Move to next occurence of `x` in current line                         | `fx`       |
| Move to previous occurence of `x` in current line                     | `Fx`       |
| Move to next occurence of `x` in current line                         | `tx`       |
| Move to previous occurence of `x` in current line                     | `Tx`       |
| Repeat previous find command in same direction                        | `;`        |
| Repeat previous find command in opposite direction                    | `,`        |

### Screen Movements

| Command                                | Notes       |
| -------------------------------------- | ----------- |
| Scroll forwared one screen             | `^f`        |
| Scroll backward one screen             | `^b`        |
| Scroll forward half a screen           | `^d`        |
| Scroll backward half a screen          | `^u`        |
| Scroll forward one line                | `^e`        |
| Scroll backward one line               | `^y`        |
| Scroll to top of the screen            | `z [enter]` |
| Reposition cursor middle of the screen | `z.`        |
| Reposition cursor bottom of the screen | `z-`        |

### Code specific Movements

| Movement                               | Commands       | Notes                                                                                                                                                                                                                   |
| -------------------------------------- | -------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Move to opening bracket                | `%`            | `(`, `[` and `{` are considered opening brackets. This moves to the next opening bracket of the same line. If you the cursor is on the opening or closing bracket, then it will jump to its opening or closing bracket. |
| Move to definition                     | `gd`           | Jump to a definition. *VS Code specific*                                                                                                                                                                                |
| Move to reference                      | `gr`           | Jump to a reference. *VS Code specific*                                                                                                                                                                                 |
| Move to implementation                 | `gi`           | Jump to an implementation. *VS Code specific*                                                                                                                                                                           |
| Move to type definition                | `gt`           | Jump to a type definition. *VS Code specific*                                                                                                                                                                           |
| Jump to previous cursor                | `Ctrl-o`       | Jump to the previous cursor position in the _jump tree_. Unlike `''` it goes back to several previous positions.                                                                                                        |
| Go back to subsequent cursor positions | `Ctrl-i`       | Go back to  subsequent cursor position. You can move back and forth with `Ctrl-o` and `Ctrl-i`.                                                                                                                         |
| Display jumps list                     | `:jumps`       | Display the complete list of all the cursor jumps                                                                                                                                                                       |
| Go to a specific jump                  | `:ju <number>` | Go to  specific jump number in the jumps list. The number can be negative.                                                                                                                                              |

| Examples  | Notes                        |
| --------- | ---------------------------- |
| `2Ctrl-o` | Go back 2 previous positions |
| `:ju -2`  | Go back 2 previous positions |
| `3Ctrl-i` | Move forward 3 positions     |
| `:ju 3`   | Move forward 3 positions     |

### Marks

| Commands | Notes                                                                 |
| -------- | --------------------------------------------------------------------- |
| `m`      | Set a mark at the current cursor position.                            |
| `'x`     | Go to the first character of the line of mark `x`                     |
| `` `x `` | Go to the to the exact character of `x`                               |
| ` `` `   | Return to the exact position of the previous mark or context          |
| `''`     | Return to the beginning of the line of the previous mark or context   |
| `'"`     | Move to the position when last editing the file                       |
| `` `. `` | Move to last change in the file                                       |
| `'.`     | Move to the beginning of the line of the last change of the file      |
| `''`     | Return to the exact position before the last jump                     |
| `''`     | Return to the beginning of the line before the last jump              |
| `'.`     | Return to the exact position of the last change in the current buffer |
| `` `[ `` | Move to the beginning of the previous text operation                  |
| `` `] `` | Move to the end of the previous text operation                        |
| `'[`     | Move to the beginning of the line of the previous text operation      |

Marks are particularly useful to delete specific chunk of text. I would jump to the of the chunck I want to delete, set a mark with `ma`, then jump to the beginning of the chunk I want to delete and delete it with `` d`a ``.

### Windows Management

| Commands        | Notes                                 |
| --------------- | ------------------------------------- |
| `[Control-W] s` | Split the current window horizontally |
| `[Control-W] v` | Split the current window vertically   |
| `[Control-W] w` | Switch between windows                |
| `[Control-W] q` | Quit the current window               |
| `[Control-W] o` | Close all windows except the current  |
| `[Control-W] c` | Close the current window              |
| `[Control-W] h` | Move to the window on the left        |
| `[Control-W] j` | Move to the window below              |
| `[Control-W] k` | Move to the window above              |
| `[Control-W] l` | Move to the window on the right       |
| `:e <file>`     | Open <file>                           |
| `:ene`          | Open new empty file                   |
| `:bn`           | Jump to next file                     |
| `:bp`           | Jump to previous file                 |
| `:bd`           | Remove file from the buffer list      |

## Visual mode

### Selection

| Commands | Notes                                            |
| -------- | ------------------------------------------------ |
| `v`      | Start a character-wise visual selection          |
| `V`      | Start a line-wise visual selection               |
| `^v`     | Start a block-wise visual selection              |
| `gv`     | Reselect the last visual selection               |
| `o`      | Move to the other end of the selection           |
| `aw`     | Select a word and the trailing space             |
| `iw`     | Select a word without the training space         |
| `ab`     | Select a block with parenthesis                  |
| `aB`     | Select a block with curly braces                 |
| `ib`     | Select a block without parenthesis               |
| `iB`     | Select a block without curly braces              |
| `as`     | Select a sentence                                |
| `is`     | Select a sentence without trailing spaces        |
| `ap`     | Select a paragraph                               |
| `ip`     | Select a paragraph without trailing spaces       |
| `at`     | Select a tag block                               |
| `it`     | Select a tag block without trailing spaces       |
| `a"`     | Select a double quoted string                    |
| `i"`     | Select a double quoted string without the quotes |
| `a'`     | Select a single quoted string                    |
| `i'`     | Select a single quoted string without the quotes |
| `` a` `` | Select a backtick quoted string                  |
| `` i` `` | Select a backtick quoted string without the `    |
| `a(`     | Select a block with parenthesis                  |
| `i(`     | Select a block without parenthesis               |
| `a)`     | Select a block with parenthesis                  |
| `i)`     | Select a block without parenthesis               |
| `a[`     | Select a block with square brackets              |
| `i[`     | Select a block without square brackets           |
| `a]`     | Select a block with square brackets              |
| `i]`     | Select a block without square brackets           |
| `a{`     | Select a block with curly braces                 |
| `i{`     | Select a block without curly braces              |
| `a}`     | Select a block with curly braces                 |
| `i}`     | Select a block without curly braces              |
| `a<`     | Select a block with angle brackets               |
| `i<`     | Select a block without angle brackets            |
| `a>`     | Select a block with angle brackets               |
| `i>`     | Select a block without angle brackets            |

### Code specific editing

| Text Object | Command | Notes                                                                                                                                                                                                            |
| ----------- | ------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Selection   | `gq`    | On a visual selection reflow and wordwrap blocks of text, preserving commenting style. Great for formatting documentation comments. *VS Code specific*                                                           |
| Selection   | `af`    | Visual mode command which selects increasingly large blocks of text. Work well between parenthesis, otherwise it depends on the language and its structure (not much for Python for example). *VS Code specific* |


## References

 - Learning the vi & Vim Editors 8th Edition by Arnold Robbins & Elbert Hannah
 - [Vim Cheat Sheet](https://i.imgur.com/YLInLlY.png)