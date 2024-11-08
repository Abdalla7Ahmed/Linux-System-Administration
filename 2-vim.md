

there are three modes in vim 
1.command mode 
2.insert mode
3.execution mode

when opening file the default mode is command mode 
to switch to insert mode just enter :
to switch to command mode again just write esc




## moving 
:\<n> --> go to the line <n?
gg --> go the the first line
G --> go to the last line
\<n>gg --> go to line \<n>
\<n>G --> go to line \<n>
$ --> go to the end of the current line


## assigne 
:r \<path to file> --> past all the content of this file here



## replacing 
:%s/\<old word>/\<new word>/ --> replac the first result
:%s/\<old word>/\<new word>/g --> replac the all matched

in insert mode 
i--> insert mode in the curent cursor location
o--> insert mode in line after the cursor 
O--> insert mode in line before cursor 



in command mode 
## search 
command mode we can search on word by using /\<word> then press enter
n--> next result 
N--> previous result
also we can use ?\<word>
n--> previous result
N--> next result


u -->undo 
. -->redo --> execute the last command
## delete
dw --> delete from the cursor to the end of word
dl --> delete letter
d$ --> delete from the cursor to the end of the  line
d0 --> delete from the cursor to the begining of the line
:7,10d --> delete from 7 to 10
:.,$d --> delete from the cursor location to the end of file
:\<n>,$d --> delete from line n to the end of file




l--> move cursor left
h--> move for write
j--> move cursor down
k--> move cursor up
v --> select

in exec mode 
w--> write (save)
q--> quit
wq--> write and quit
q! -->quit without saving 
w \<file name> --> save this content with name \<file name>
w >> \<file name> --> save this content with name \<file name>
\<n> --> go to n line
set number --> set the numbers
set nonumber --> remove the numbers
:!\<command> --> execute the specific command inside vim
:.!\<command> --> execute the specific command and the output will written in the cursor location
:$!<command> --> execute the specific command and the output will written in end of this file
:\<n>!<command> --> execute the specific command inside vim and the output will written in line \<n>



## copy
yy(yank)--> copy current single line 
p--> past
yw --> copy word
\<n>yy --> copy n lines 
:n1,n2y --> copy from line n1 to line n2 
:.,$y --> copy from the cursor location to the end of file
:\<n>,$d --> copy from line n to the end of file
y$ --> copy from the current cursor location to the end of the line
y0 --> cut from the current cursor location to the begining of the line

## cut 
dd --> cut the current single line
p --> past
dw --> cut word
\<n>dd --> cut n lines
:\<n1>,\<n2>d --> cut from line n1 to line n2 
:.,$d --> cut from the cursor location to the end of file
:\<n>,$d --> cut from line n to the end of file
d$ --> cut from the current cursor location to the end of the line
d0 --> copy from the current cursor location to the begining of the line

