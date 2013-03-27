##![VIM](https://s3.amazonaws.com/gogo-knows/Linux.png)

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

    x    - Delete character
    dw   - Delete word from cursor on
    db   - Delete word backward
    dd   - Delete line
    d$   - Delete to end of line
    d0   - Delete to beginning of line

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
