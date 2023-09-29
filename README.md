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

### Movements

| Movement                                | Commands   |
| --------------------------------------- | ---------- |
| Move Left                               | `h`        |
| Move Right                              | `l`        |
| Move Up                                 | `k`        |
| Move Down                               | `j`        |
| To first character of the line          | `+`        |
| To first character of the previous line | `-`        |
| To en of word                           | `e` or `E` |
| To beginning of word                    | `w` or `W` |
| To a particular line                    | `[x]G`     |
| To begining of the file                 | `gg`       |
| To the end of a file                    | `G`        |
|                                         |            |

### Code specific Movements

| Movement                | Commands | Notes                                                                                                                                                                                                                   |
| ----------------------- | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Move to opening bracket | `%`      | `(`, `[` and `{` are considered opening brackets. This moves to the next opening bracket of the same line. If you the cursor is on the opening or closing bracket, then it will jump to its opening or closing bracket. |

## Insert mode


## Visual mode


## Command-line mode


## Ex mode


## References

 - Learning the vi & Vim Editors 8th Edition by Arnold Robbins & Elbert Hannah
 - [Vim Cheat Sheet](https://i.imgur.com/YLInLlY.png)