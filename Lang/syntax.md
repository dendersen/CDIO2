## file structure
To add a new language into the program a .lang file is to be used, these files must start with the language name (as written in `src/lang/Lang.java`) and end in .lang<br>
nothing lese is to be added in the file name.<br>
this file must then be placed in the folder `Lang/`<br>
this is the same location as this file is found.
<br><br>
## Language
- `declarator syntax` first you must declare your declarator, as the lang file allows for the writer/user to choose the symbols that denominate different parts of the program, of course defaults are written in. <br>To use defaults either leave a line blank to ignore all configuration on all options on that line or leave a part blank to use default for that option.<br>if only the first  option is to be used all spaces must still be written!

  - `tile`<br>
  default = '<span style="color:lightgreen">@</span>'<br>
  described on line 1 word 1<br>
  default = '11'<br>
  number of tiles (as number) line 1 word 2
  - `User interface`<br>
  default = '<span style="color:lightgreen">&</span>'<br>
  described on line 1 word 3
  - `error message`<br>
  described on line 2<br>
  default = '<span style="color:lightgreen">[</span>'<br>
  char 1 = start<br><br>
  default = '<span style="color:lightgreen">]</span>'<br>
  char 2 = end

- `tiles` all tiles must be written from line 3.
  - the first char of a new tile must be the correct declarator
  - each tile must have it's associated number written right after the declarator
  - then a space followed by the flavour text given to that tile, any use of the declarator will be replaced by the value of the given tile
- `User interface` all interface parts must be written right after the last tile
  - each line of the interface must start with the declarator
  - then the color of the text, note that no space should be used between declarator and color, to use the consoles default color leave this blank  and instead add a space.
  - after the color add a space, this will then bbe written to the screen exactly as you see it note that each line in the file does not give a new line in the program
  - after the declarator any text written will be outputted exactly as written, with a few exceptions
    - all unicode characters between U+E000 and U+EFFF are reserved.
    - the discriminator will not be treated like a new line, instead it allows for use of tags withs are described in the table bellow. 
    - all spaces before or after tags will be removed, to place a space around them use two spaces<br>
  - | tags                        | actions |
    |-----------------------------|---------|
    | new line                    | &&      |
    | current player number       | &player |<#TODO all actions should be in `this`>
    | value of the first die      | &die1   |
    | value of the second die     | &die2   |
    | sum of dice                 | &sum    |
    | current player's total gold | &gold   |
    | player 1's total gold       | &gold1  |
    | player 2's total gold       | &gold2  |
    | turn number                 | &turn   |
    | current tile text           | &tileT  |
    | current tile nr             | &tileNR |
    | change text color red       | &red    |
    | change text color green     | &green  |
    | change text color blue      | &blue   |
    | change text color cyan      | &cyan   |
    | change text color yellow    | &yellow |
    | change text color purple    | &purple |
    | use default color           | &reset  |
- `error messages`
  - these are not strictly necessary and are only meant for debugging and should not (unless something goes wrong) be printed, they are only meant to allow further development using your translated error messages
  - each line must start with the start descriptor
  - without adding a space the error name must be written
  - then the end descriptor followed by a space
  - the get the stacktrace write the end and start descriptor without anything in the middle.

<br>
#TODO file name / save gold