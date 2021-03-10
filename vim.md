
:tabe <filename>: to open file in a new tab

ctrl = ^
insert mode: 
> ^+r > a: to write from register a
> ^+a: to repeat last change
> ^p: to find previous simple word completion
> ^n: to find next match to autocomplete

> /text: search for text string
> :n: move to nth line
> :ZZ: save and close a tab/file

> d: cut
> dw: cut word
> d}: cut up to next paragraph
> D: cut/Delete remainder of line
> u: undo last change
> .: repeat last change
> G: move to last line
> p: paste
> y: yank
> ^x >
>  ^]: completion from tag
>   ^o/^i: jump back
> ^t: pop back from tag
> ^f: complete file
> ^L: complete line + context aware ^X^L
> ^O: complete function

insert mode
- ^pageup: next tab
- ^pagedown: previous tab
 
edit mode
- gt: next tab
- gT: previous tab
- ZZ: save and close a tab/file

> ^W s/v: split vertically
> :sp/vs: split
> cgn: change next object
> /text: search for text
> /text\c: ignore case
> n: to go to next find in search
> N: to go to previous find in search
> fX:  go to next X in line,
> ;: repeat in same direction
> ,: repeat in previous direction 
> ?text: search in opposite direction
> ^o: to go to backward
> ^i: to go forward
> %: move to the matching bracked
> :s/old/new: to change first occurrence of old
> :s/old/new/g: to change all occurrences in the line
> :#,#s/old/new/g: to change all occurrences in the given lines
> :%s/old/new/g: to replace all 
> :%s/old/new/gc: to replace all with a promt
> :%s/old/new/gcI: to replace case sensitive all with a promt

> :!command: to run command in the terminal
> :w <filename>: write buffer to the filename
> v: to select the text
> :r <filename>: retrieve and insert the content of file
> o: to open a new line below and put in insert mode
> O: to open a new line above and put in insert mode
> a: insert text after the cursor
> r<char>: replace the character
> R: replace more than one character
> e: to go to the end of word
> yw: yank one word
> :set ignorecase:
> :set hlsearch: highlight search
> :set incsearch: show partial matches
* :no : prepend no to switch and option off
> :set nohlsearch

* vim -p <filename> <filename>: to open multiple file in tabs

* :b filename or unique part of filename to open
> :b <filename>/file: to search from buffer
> A: to append after the line
> dw: to remove word to the end including space
> dd: to remove complete line
> u: undo previous changes
> U: to undo all previous changes on line
> ^r: redo previous change
> 0: to move to start of line
> p: put the deleted text after the cursor
> ^g: show current location and file
> <number>G: move to the line number
> :n move to line n
> G: move to the bottom of file
> gg: move to the start of file
> cw: change the word
> c$: change to the end of line
> autocomplete
> ^x^n: just the file
> ^x^f: for filenames
> ^n: for anything
> ^n/^p: for next and previous
> viwp: replaces the word from clipboard
> ci": change inside quotes "" (){}[]<>''
> :noh: clear highlight until next search
> zg: add word under cursor to dictionary
> Ctrl-^: go to last file
> ^i: jump to next cursor position
> ^o: jump to last cursor location
> ^Y: move current pane up
> ^E: move current pane down
> \*: next whole word under search
> \#: previous whole word under search
> :browse oldfiles: To browse old opened files, :num to open the file
* grep and search in all js files and folders
> :vimgrep /foo/g \*\*.js
* search in all text files in current folder
> :vimgrep /foo/g \*.js
* search in all tracked files
> :vimgrep /foo/g git ls-files
* store in argument list and use for multiple searches
> :args {FILES}
> :vimgrep /foo/g ##
* use current search pattern among other files
> :vimgrep //g
* navigating quickfix list
> :copen : open quickfix list
> :close : close quickfix list
> :cnext/:cprev: to go to next and previous fix
> :cfirst/:clast: go to first and last
> :cnfile/:cpfile: go to the first and last of the file
> :cc n: goes to the nth match
* you can move through last 10 quickfix list
> :colder/:cnewer or :5colder
```
> "*p: paste form clipboard
> "+p: paste from clipboard
```
> ^+W N: go to normal mode in vim :term
> i or a: to go back to terminal mode
[VimSource](https://gist.github.com/m3nd3s/3959966)
> ^+w T: Make cuurent window full screen
* Suspend vim, use terminal  and then resume back
> ^+z: suspend vim
> fg: resume vim
* save session and resume
> :mksession ~/session.vim
> :source ~/session.vim
or
> vim -S ~/session.vim
[Youtube video
vim](https://www.youtube.com/watch?v=XA2WjJbmmoM&ab_channel=thoughtbot)
* Tags
:MakeTags: to create tags
> ^]: go to the tag
> g^]: if multiple tags, go to ambiguous tags
> ^t: to go back up the stackk
* Autocomplete
```
^x^n: complete form this file
^x^f: complete file name
^x^]: comlete from tags
^n: complete anything
then ^n, ^p to go forward and back in the list
```
* netrw browser
```
v: open in new vertical split
t: open in tab
s: open in horizontal split
```
* Spell
```
z=: current word under cursor from dictionary
]s: go to next misspelled word.
[s: go to previous misspelled word.
zg: add word to dictionary.
```
* windows horizontal resize
> :resize +/-N
* resize vetically windows - N
> :vertical resize +/-N
* resize to N characters
> :resize N
* increase/decrease horizontally by 20 size
> ^W +/-
* vertically
> ^W >/<
* equalize width and height
> ^W =
* :ls + show buffer has unsaved changes

