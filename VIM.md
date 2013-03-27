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

    cw  - Change current word to a new word
    r   - Replace one character at the cursor position
    R   - Begin overstrike or replace mode – use ESC key to exit
    o   - Open a new line below and insert.
    O	- Open a new line above and insert.
    C   - Change the rest of the current line.
    
### Visual mode commands

    v   - Start highlighting characters. Use the normal movement keys and commands to select text for highlighting.
    V   - Start highlighting lines.
    
    # Below commands work in visual mode
    
    >   - Shift right (indent).
    <   - Shift left (de-indent).
    c  	- Change the highlighted text.
    y 	- Yank the highlighted text. In Windows terms, "copy the selected text to clipboard."
    d 	- Delete the highlighted text. In Windows terms, "cut the selected text to clipboard."
    
### Search & CommandT

    :/  - pattern Search forward for the pattern
    :?  - pattern Search backward for the pattern
    \t  - CommandT file navigation

### Yank (has most of the options of delete)-- VI's copy commmand

    yy   - yank current line
    y$   - yank to end of current line from cursor
    y$   - yank to start of current line from cursor
    yw   - yank from cursor to end of current word
    5yy  - yank, for example, 5 lines

### Paste (used after delete or yank to recover lines.)
    
    p    - paste below cursor
    P    - paste above cursor
    u    - Undo last change
    U    - Restore line
    J    - Join next line down to the end of the current line

### File Manipulation Commands

    :w   - Write workspace to original file
    :w   - file Write workspace to named file
    :e   - file Start editing a new file
    :r   - file Read contents of a file to the workspace
