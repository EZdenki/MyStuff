## Vim Cheatsheet
### Navigation
+ ```k``` Up
+ ```j``` Down
+ ```l``` Right
+ ```h``` Left
+ ```w / e``` Go to beginning/end of current/next word
+ ```b / B``` Go to previous word
+ ```{ / }``` Go to previous/next paragraph
+ ```H``` Go to [H]irst line of current screen
+ ```M``` Go to Middle line of current screen
+ ```L``` Go to Last line of current screen
+ ```<ctrl>+f``` Jump Forward one full screen
+ ```<ctrl>+b``` Jump Backwards one full screen
+ ```<ctrl>+d``` Jump Down a half screen
+ ```<ctrl>+u``` Jump Up a half screen

### Insert / Append / Combine Text
+ ```i``` Insert before the cursor
+ ```I``` Insert at the beginning of the line
+ ```a``` Insert (append) after the cursor
+ ```A``` Insert (append) at the end of the line
+ ```o``` Append (open) a new line below the current line
+ ```O``` Append (open) a new line above the current line
+ ```J``` Join the next line to the end of the current line
+ ```ea``` Insert (append) at the end of the word 
+ ```< / >``` Unindent/indent block


### Tools
+ ```:E``` File Explorer

### Misc
Edit VIM defaults:
+ Navigate to home directory and edit _vimrc
+ .home in Windows is c:\users\username\
+ Turn on spellcheck: ```:set spell```
+ Turn off spellcheck: ```:set nospell```
+ Get spellcheck suggestions: ```z=``` Then type in letter of suggestion for replacement

### VIM Settings:
+ Turn on Numbering: ```set number```
+ Turn on syntax highlighting: ```syntax on```
+ Set tabstop to 4: ```set tabstop=4```
+ Make tab do spaces instead of tabs: ```set expandtab```
+ Change back to using tabs instead of spaces: ```set noexpandtab```
+ Change colorscheme: ```colorscheme darkblue```
+ Add statusline: ```set statusline=2```
+ Add filename and cursor pos. to status line: ```set statusline=%F\ %l\:%c```
