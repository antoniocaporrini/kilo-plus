# kilo.c – Terminal Text Editor in C

A lightweight text editor for the terminal, written in C from scratch.  
Inspired by [kilo by antirez](https://viewsourcecode.org/snaptoken/kilo/), this is a step-by-step educational clone meant to explore terminal control, raw input mode, and screen rendering using low-level Unix system calls.

## 🚧 Status

✅ Cursor movement  
✅ Screen redraw  
✅ Raw input mode  
⏳ File loading/saving (WIP)  
⏳ Syntax highlighting (planned)

## 🔧 Features

- Cross-platform (Linux/macOS) terminal-based editor
- Raw mode input handling
- Arrow key navigation
- Centered welcome message
- Clean screen refresh via VT100 escape sequences

## 📁 File Structure

- `kilo.c`: Main application (monolithic, single-file version)
- `README.md`: You're here
- _(coming soon)_ `src/`: Split version with modular headers and source files

## Concepts Explored

- Unix terminal control with `termios.h`
- Manual screen buffer rendering
- Non-canonical input reading
- ANSI escape codes
- Minimal memory management

## Build & Run

```bash
gcc -o kilo kilo.c
./kilo
```
