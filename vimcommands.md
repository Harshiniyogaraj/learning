## 📂 File & Buffer Management

- `:e filename` – Open a file  
- `:w` – Save current file  
- `:q` – Quit Vim  
- `:wq` – Save and exit  
- `vim filename` – Open or create a file  
- `vim` – Launch Vim without a file  
- `:n` – Next buffer (cycle through open files)  
- `:N` – Previous buffer  
- `:b filename` – Switch to buffer by filename  
- `:ls` – List open buffers  

---

## 🧭 Navigation Keys

- `h` – Move left  
- `l` – Move right  
- `j` – Move down  
- `k` – Move up  
- `$` – Move to end of line  
- `gg` – Go to beginning of file  
- `G` – Go to end of file / specific line  
- `Ctrl-d` – Scroll half page down  
- `Ctrl-u` – Scroll half page up  

---

## ✍️ Insert Mode Shortcuts

- `i` – Insert before cursor  
- `I` – Insert at beginning of line  
- `a` – Insert after cursor  
- `A` – Insert at end of line  
- `o` – Open new line below  
- `O` – Open new line above  

---

## ✂️ Editing Essentials

- `dd` – Delete current line  
- `dw` – Delete word  
- `d0` – Delete to beginning of line  
- `d$` or `D` – Delete to end of line  
- `dG` – Delete to end of file  
- `dgg` – Delete to start of file  
- `d/word` – Delete until next occurrence of "word"  
- `:3,7d` – Delete lines 3 to 7  
- `:1,$d` – Delete all lines  

---

## 📋 Copy & Paste

- `yy` – Yank (copy) current line  
- `p` – Paste after cursor  

---

## 🔄 Undo & Redo

- `u` – Undo last change  
- `Ctrl-r` – Redo undone change  
- `.` – Repeat last change  

---

## 🔍 Search & Replace

- `/pattern` – Search forward  
- `?pattern` – Search backward  
- `n` – Repeat search forward  
- `N` – Repeat search backward  
- `:%s/old/new/g` – Replace all occurrences  
- `:%s/^/  /g` – Add spaces at start of each line  
- `:3,10s/^/  /g` – Add spaces to lines 3–10  
- `:%s/^/hello/g` – Add "hello" at start of each line  
- `:%s/^hai/hello/g` – Replace "hai" with "hello" at line start  

---

## 👀 Visual Mode & Case Toggle

- `Ctrl+v` – Enter visual block mode  
- `Shift + ~` – Toggle case (uppercase/lowercase)  

---

## 🔢 Line Numbers

- `:se nu` or `:set number` – Show line numbers  
- `:se nonu` or `:set nonumber` – Hide line numbers  

---

## 🧹 Character Deletion

- `x` – Delete character under cursor  
- `X` – Delete character before cursor  

---

## 🛠️ Miscellaneous

- `esc` – Return to normal mode

