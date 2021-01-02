The quick brown fo

:tabe <filename>: to open file in a new tab

insert mode
- ^pageup: next tab
- ^pagedown: previous tab
 
edit mode
- gt: next tab
- gT: previous tab
- ZZ: save and close a tab/file

:^W s/v: split veritcally
:sp/vs: split
:cgn: change next object
/text: search for text
n: to go to next find
N: to go to previous find
?text: search in opposite direction
^o: to go to backward
^i: to go forward
%: move to the matching brack
:s/old/new: to change first occurrence of old
:s/old/new/g: to change all occurrences in the line
:#,#s/old/new/g: to change all occurrences in the given lines
:%s/old/new/g: to replace all 
:%s/old/new/gc: to replace all with a promt
:!command: to run command in the terminal
:w <filename>: write buffer to the filename
:v: to select the text
:r <filename>: retrieve and insert the content of file
:o: to open a new line below and put in insert mode
:O: to open a new line above and put in insert mode
:a: insert text after the cursor
:R: replace more than one character
:e: to go to the end of word
:yw: yank one word
/text\c: ignore case
:no : prepend no to switch and option off
:ignorecase:
:hlsearch: highlight search
:incsearch: show partial matches

vim -p <filename> <filename>: to open multiple file in tabs

:b <filename>: to search from buffer
^]: jump to tag
g^]: for ambiguous tags
^t: to jump back up the tag stack
A: to append after the line
dw: to remove word to the end including space
dd: to remove complete line
u: undo previous changes
U: to undo all previous changes on line
^r: redo previous change
0: to move to start of line
p: put the deleted text after the cursor
^g: show current location and file
<number>G: move to the line number
G: move to the bottom of file
gg: move to the start of file
r<char>: replace the character
cw: change the word
c$: change to the end of line
autocomplete
^x^n: just the file
^x^f: for filenames
^n: for anything
^n/^p: for next and previous
viwp: replaces the word from clipboard
ci": change inside quotes "" (){}[]<>''
:noh: clear highlight until next search
zg: add word under cursor to dictionary
