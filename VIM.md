##![VIM](https://s3.amazonaws.com/gogo-knows/Linux.png)

### Best command

    .    - Repeat last command

### Movement

    h    - left
    l    - right
    k    - up
    j    - down
    nG   - Cursor goes to the specified (n) line
    :n   - Cursor goes to the specified (n) line
    $    - End of line
    0    - Start of line
    w    - Forward one word
    b    - Backward one word
    
### Exit Commands

    :wq  - Write file to disk and quit the editor
    :q!  - Quit (no warning)
    :q   - Quit (a warning is printed if a modified file has not been saved)
    : 10,25 w temp - write lines 10 through 25 into file named temp.
    
### Text Deletion Commands

    x    - Delete character under the cursor.
    X    - Delete characters before the cursor.
    dw   - Delete word from cursor on
    db   - Delete word backward
    dd   - Delete line
    d$   - Delete to end of line
    d0   - Delete to beginning of line

### Text manipulation

    ciw - Change entire word to a new word
    cw  - Change current word to a new word from current cursor position
    r   - Replace one character at the cursor position
    R   - Begin overstrike or replace mode – use ESC key to exit
    o   - Open a new line below and insert.
    O	- Open a new line above and insert.
    C   - Change the rest of the current line.
    cc  - Change the current line.
    
### Scrolling & multi-windowing
    
    ^ = Ctrl
    
    ^E ^Y  - scroll line up, down
    ^D ^U  - scroll half a page up, down
    ^F ^B - scroll page up, down
    zt or z↵ - set current line at top of window
    zz or z. - set current line at center of window
    zb or z- - set current line at bottom of window
    zh zl    - scroll one character to the right, left
    zH zL	 - scroll half a screen to the right, left
    ^Ws 	 - split window in two
    ^Wn      - create new empty window
    ^Wo   	 - make current window one on screen
    ^Wj ^Wk	 - move to window below, above
    ^Ww ^W^W - move to window below, above (wrap)
    :sp[lit] file  - Splits the window horizontally.
    :vs[plit] file - Splits the window vertically.
    :5 :split README - show README in a window of 5 lines high.

### Moving windows

    ctrl-w r	rotate all windows
    ctrl-w x	exchange current window with its neighbour
    ctrl-w H	move current window to far left
    ctrl-w J	move current window to bottom
    ctrl-w K	move current window to top
    ctrl-w L	move current window to far right
    
### Visual mode commands

    v   - Start highlighting characters. Use the normal movement keys and commands to select text for highlighting.
    V   - Start highlighting lines.
    
    # Below commands work in visual mode
    
    >   - Shift right (indent).
    <   - Shift left (de-indent).
    c  	- Change the highlighted text.
    y 	- Yank the highlighted text. In Windows terms, "copy the selected text to clipboard."
    d 	- Delete the highlighted text. In Windows terms, "cut the selected text to clipboard."
    
### Search

    :/  - pattern Search forward for the pattern
    :?  - pattern Search backward for the pattern
    n   - Scan for next search match in the same direction.
    N    - Scan for next search match but opposite direction.

### CommandT

    \t  - CommandT file navigation
    Ctrl + j - move down in file selection menu
    Ctrl + k - move up in file selection menu
    Ctrl + s - Horizontally split file from selection menu
    Ctrl + v - Vertically split file from selection menu
    
    # Put this in ~\.bashrc file to enable Ctrl + S
    $ stty start undef stop undef

### Yank (has most of the options of delete)-- VI's copy commmand

    yy   - yank current line
    y$   - yank to end of current line from cursor
    y$   - yank to start of current line from cursor
    yw   - yank from cursor to end of current word
    5yy  - yank, for example, 5 lines

### Paste (used after delete or yank to recover lines.)
    
    p    - paste below cursor
    P    - paste above cursor
    J    - Join next line down to the end of the current line
    u    - Undo last change
    U    - Restore line
    Ctrl + r - redo

### File Manipulation Commands

    :w   - Write workspace to original file
    :w   - file Write workspace to named file
    :e   - file Start editing a new file
    :r   - file Read contents of a file to the workspace
