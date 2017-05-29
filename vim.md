# vim - vi Improved


What about [Neovim](https://neovim.io/)? Also [VScode](./code)

[vimgifs](https://vimgifs.com/) looks a fun way to learn.

Start here: [How to learn vim](http://xn--h4hg.ws/2013/12/19/how-to-learn-vim/)

 * [vim Koans](https://sanctum.geek.nz/arabesque/vim-koans/)
 * [Switch to vim](https://10clouds.com/blog/switch-to-vim/) without ruining your workflow, *TODO*, Read this

## vi / vim cheatsheets

* [vim cheatsheet](http://adminhacks.com/vim-cheatsheet/)
* [Poster](http://vimcheatsheet.com/) - Kickstarter etc
* [Coming home to vim](http://stevelosh.com/blog/2010/09/coming-home-to-vim/)
* http://hackdesign.org/lessons/49
* [Duck Duck Go][duck]
* Vim [Anti-Patterns](https://sanctum.geek.nz/arabesque/vim-anti-patterns/)

## Cursor movement

	h	move cursor left
	j	move cursor down
	k	move cursor up
	l	move cursor right
	w	jump forwards to the start of a word
	W	jump forwards to the start of a word (words can contain punctuation)
	e	jump forwards to the end of a word
	E	jump forwards to the end of a word (words can contain punctuation)
	b	jump backwards to the start of a word
	B	jump backwards to the start of a word (words can contain punctuation)
	0	jump to the start of the line
	^	jump to the first non-blank character of the line
	$	jump to the end of the line
	G	go to the last line of the document
	5G	go to line 5

## Insert mode - inserting/appending text

	i	insert before the cursor
	I	insert at the beginning of the line
	a	insert (append) after the cursor
	A	insert (append) at the end of the line
	o	append (open) a new line below the current line
	O	append (open) a new line above the current line
	ea	insert (append) at the end of the word
	Esc	exit insert mode

## Editing

	r	replace a single character
	J	join line below to the current one
	cc	change (replace) entire line
	cw	change (replace) to the end of the word
	c$	change (replace) to the end of the line
	s	delete character and substitute text
	S	delete line and substitute text (same as cc)
	xp	transpose two letters (delete and paste)
	u	undo
	Ctrl+r	redo
	.	repeat last command

## Marking text (visual mode)

	v	start visual mode, mark lines, then do a command (like y-yank)
	V	start linewise visual mode
	o	move to other end of marked area
	Ctrl+v	start visual block mode
	O	move to other corner of block
	aw	mark a word
	ab	a block with ()
	aB	a block with {}
	ib	inner block with ()
	iB	inner block with {}
	Esc	exit visual mode

## Visual commands

	>	shift text right
	<	shift text left
	y	yank (copy) marked text
	d	delete marked text
	~	switch case

## Cut and paste
	yy	yank (copy) a line
	2yy	yank (copy) 2 lines
	yw	yank (copy) word
	y$	yank (copy) to end of line
	p	put (paste) the clipboard after cursor
	P	put (paste) before cursor
	dd	delete (cut) a line
	2dd	delete (cut) 2 lines
	dw	delete (cut) word
	D	delete (cut) to the end of the line
	d$	delete (cut) to the end of the line
	x	delete (cut) character
## Exiting
	:w	write (save) the file, but don't exit
	:wq	write (save) and quit
	:x	write (save) and quit
	:q	quit (fails if there are unsaved changes)
	:q!	quit and throw away unsaved changes
## Search and replace
	/pattern	search for pattern
	?pattern	search backward for pattern
	n	repeat search in same direction
	N	repeat search in opposite direction
	:%s/old/new/g	replace all old with new throughout file
	:%s/old/new/gc	replace all old with new throughout file with confirmations
## Working with multiple files
	:e filename	edit a file in a new buffer
	:bnext 
	:bn	go to the next buffer
	:bprev 
	:bp	go to the previous buffer
	:bd	delete a buffer (close a file)
	:sp filename	open a file in a new buffer and split window
	:vsp filename	open a file in a new buffer and vertically split window
	Ctrl+ws	split window
	Ctrl+ww	switch windows
	Ctrl+wq	quit a window
	Ctrl+wv	split window vertically
## Tabs
	:tabnew filename
	:tabn filename	open a file in a new tab
	Ctrl+wt	move the current split window into its own tab
	gt 
	:tabnext 
	:tabn	move to the next tab
	gT 
	:tabprev 
	:tabp	move to the previous tab
	#gt	move to tab number #
	:tabmove #	move current tab to the #th position (indexed from 0)
	:tabclose 
	:tabc	close the current tab and all its windows
	:tabonly 
	:tabo	close all tabs except for the current one

[duck]: https://duckduckgo.com/?q=vim+cheat+sheet

http://genotrance.wordpress.com/2008/02/04/my-vim-customization/

[The Grammar of Vim](http://rc3.org/2012/05/12/the-grammar-of-vim/)

Basically a clone of [vimmy](http://itunes.apple.com/us/app/id361221825) but for [[wp7]]

 * [vimdb](https://github.com/cldwalker/vimdb)
 * [vimdoc](http://vimdoc.sourceforge.net/htmldoc/motion.html)
 * [Zen](http://www.digizenstudio.com/blog/categories/vim/)
 * [Koans](http://blog.sanctum.geek.nz/vim-koans/)

## High Level Steps to Record and Play inside Vim

 * Start recording by pressing q, followed by a lower case character to name the macro
 * Perform any typical editing, actions inside Vim editor, which will be recorded
 * Stop recording by pressing q
 * Play the recorded macro by pressing @ followed by the macro name
 * To repeat macros multiple times, press : NN @ macro name. NN is a number


## .vimrc

[Almost Empty](http://vimuniversity.com/samples/your-first-vimrc-should-be-nearly-empty)

	:edit $MYVIMRC

	set incsearch
	set mouse=a
	set nowrap
	set incsearch
	set guioptions-=T " Get rid of toolbar"
	set guioptions+=b " Add Horizontal scrollbar"
	set gfn=ProggyCleanTT:h12:cANS
	set number
	set nuw=6
	" set nobackup
	" set nowritebackup
	set backupdir=~/vimtmp,.
	set directory=~/vimtmp,.

## Split screen

ctrl-wv		Vertically
:vert help	Help


## Find

	@,# then &lt;&lt; No idea what
	N Find previous
	n Find Next
	% Find Matching bracket
	* Search for word under cursor

## Movement

	0, $    Beginning / End of line
	N   Find previous
	n   Find next
	%   Find next matching bracket
	*   Search for word under cursor
	^u  Page up 1/2 page
	^d  Page down 1/2 page

## Visual Mode

	v   Start selection
	V   Selects whole line
	^v  Vertical block
	y   Yank (Copy)
	p   Paste after cursor
	P   Paste before cursor
	d   delete (cut)

## Tabs

	:set showtabline=2 " 0 turns off
	:tabs
	:tabnew
	:help tab-page-info

## Show hidden control characters

	:set invlist    " Toggles
	:set nolist " Off
	:set list   " On

	gf = get file
	% = current file
	^Wgf = get file in new tab
	^6 = toggle buffers
	^O = older file
	TAB or ^I = newer file


[Using gf](http://stackoverflow.com/questions/133626)

## Remove trailing ^M

	:%s/\r$//

## Resources

<a href="http://genotrance.wordpress.com/2008/02/04/my-vim-customization/">Vim Startup Customization</a>
<a href="http://invisibletheory.com/2011/01/27/one-with-vim/">One With Vim</a> 
<a href="https://github.com/carlhuda/janus#readme">Janus</a>
<a href="http://walking-without-crutches.heroku.com/#105">..without crutches</a>
<a href="http://www.lagmonster.org/docs/vi.html">Cheat Sheet 1</a>
<a href="http://www.lagmonster.org/docs/vi2.html">Cheet Sheet 2</a>

----
```
set nowrap
set guioptions+=b	"Add bottom scroll bar
set guioptions-=T	"Remove toolbar
set number
set nuw=6
set incsearch
set nobackup
set nowritebackup

set gfn=ProggyCleanTT:h12:cANSI

set nocompatible
source $VIMRUNTIME/vimrc_example.vim
source $VIMRUNTIME/mswin.vim
behave mswin

set nobackup
set nowritebackup

set diffexpr=MyDiff()
function MyDiff()
	let opt = '-a --binary '
	if &diffopt =~ 'icase' | let opt = opt . '-i ' | endif
	if &diffopt =~ 'iwhite' | let opt = opt . '-b ' | endif
	let arg1 = v:fname_in
	if arg1 =~ ' ' | let arg1 = '"' . arg1 . '"' | endif
	let arg2 = v:fname_new
	if arg2 =~ ' ' | let arg2 = '"' . arg2 . '"' | endif
	let arg3 = v:fname_out
	if arg3 =~ ' ' | let arg3 = '"' . arg3 . '"' | endif
	let eq = ''
	if $VIMRUNTIME =~ ' '
		if &sh =~ '\<cmd'
			let cmd = '""' . $VIMRUNTIME . '\diff"'
			let eq = '"'
		else
			let cmd = substitute($VIMRUNTIME, ' ', '" ', '') . '\diff"'
		endif
	else
		let cmd = $VIMRUNTIME . '\diff'
	endif
	silent execute '!' . cmd . ' ' . opt . arg1 . ' ' . arg2 . ' > ' . arg3 . eq
endfunction
```

-----

## Hex Editor

In vim You can type `:%!xxd` to turn it into a hexeditor. `:%!xxd -r` to go back to normal mode.
`xxd` is shipped in a vim installation.

----

# Vim & Vi

J - join two lines together

* [IDE](http://arstechnica.com/open-source/guides/2009/05/vim-made-easy-how-to-get-your-favorite-ide-features-in-vim.ars)

* [vim is hard work...](http://jeffkreeftmeijer.com/2011/vim-is-hard-i-just-want-to-click-around/)

## .vimrc

Edit with `:e $MYVIMRC`

```
set incsearch
set mouse=a
set nowrap
set incsearch
set guioptions-=T " Get rid of toolbar"
set guioptions+=b " Add Horizontal scrollbar"
set gfn=ProggyCleanTT:h12:cANS
set number
set nuw=6
set nobackup
set nowritebackup
```

## Find

```
@,# then << No idea what
N Find previous
n Find Next
% Find Matching bracket
* Search for word under cursor
```

## Movement

```
0, $	Beginning / End of line
N	Find previous
n	Find next
%	Find next matching bracket
*	Search for word under cursor
^u	Page up 1/2 page
^d	Page down 1/2 page

h	left
j	down
k	up
l	right
```

## Visual Mode

```
v	Start selection
V	Selects whole line
^v	Vertical block
y	Yank (Copy)
p	Paste after cursor
P	Paste before cursor
d	delete (cut)
```

## Tabs

```
:set showtabline=2 " 0 turns off
:tabs
:tabnew
:help tab-page-info
```

# Show hidden control characters

```
:set invlist	" Toggles
:set nolist	" Off
:set list	" On
```

# Including files

```
:read filname
:r foo.txt    Insert the file foo.txt below the cursor.
:0r foo.txt   Insert the file foo.txt before the first line.
:r !ls        Insert a directory listing below the cursor.
:$r !pwd      Insert the current working directory below the last line.
```

## Resources

[Vin Startup Customization](http://genotrance.wordpress.com/2008/02/04/my-vim-customization/)
[One With Vim](http://invisibletheory.com/2011/01/27/one-with-vim/)
[Janus](https://github.com/carlhuda/janus#readme)
[..without crutches](http://walking-without-crutches.heroku.com/#105)
[Cheat Sheet 1](http://www.lagmonster.org/docs/vi.html)
[Cheet Sheet 2](http://www.lagmonster.org/docs/vi2.html)
[Cut & Paste](http://vim.wikia.com/wiki/Cut/copy_and_paste_using_visual_selection)
[VIM Customosation](http://genotrance.wordpress.com/2008/02/04/my-vim-customization/)

