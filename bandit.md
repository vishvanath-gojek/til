source : https://overthewire.org/wargames/bandit/bandit4.html
level 0 

* used cat 
* pw ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

level 1

dashedfilename, since few functionalies take - for upcoming input streams, it is not possible to directly open it.
use ./<file name>

pw : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Level 2

to view file with spaces "a file with spaces"
use backslash "\" before the space, so command becomes"cat a\ file\ with\ spaces".

pw MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Level 3

hidden files, view them ussing `-a` cmd in `ls`

pwd 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

level 4

to get the type of file (ASCII, and ELF etc) we can run the command `file <file name>`)

file ./*

pwd 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

level 5


for checking the type of files in multiple level of folder, we can use file ./*/* and then do cat to get the actual folder where our key may lie

pwd Q2z7VXYuHnMJ11Ks9drvakV3s0pADkcPDQl1TlRMMdSzzHJQzX

level 6

not this 
./inhere/maybehere12/-file2
./inhere/maybehere18/-file2
