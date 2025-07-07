# kilo.c – Terminal Text Editor in C

**A lightweight, educational terminal-based text editor built entirely in C, inspired by [antirez's kilo](https://viewsourcecode.org/snaptoken/kilo/). This project demonstrates low-level Unix system programming techniques, focusing on direct terminal manipulation, raw input handling, and efficient screen rendering.**

---

## ✅ Project Status: Completed

All core features have been fully implemented:

- ✅ Cursor movement
- ✅ Screen redraw with minimal flicker
- ✅ Raw input mode handling
- ✅ File loading and saving
- ✅ Syntax highlighting

---

## 🔧 Technical Features

- **Cross-platform Terminal Application**: Compatible with Linux and macOS terminals.
- **Raw Mode Input**: Disables canonical mode and echoing, directly reading keystrokes without buffering using `termios.h`.
- **Cursor Navigation**: Arrow keys navigation via manual interpretation of ANSI escape sequences.
- **Efficient Screen Rendering**: Screen refresh using VT100/ANSI escape sequences, preventing flickering by manual buffering.
- **File I/O**: Open, edit, and save plain text files.
- **Syntax Highlighting**: Basic syntax colorization for supported file types.
- **Interactive Welcome Screen**: User-friendly entry point with centered dynamic messaging.

---

## 📂 Repository Structure

- `kilo.c`: Primary, monolithic source code file.
- `README.md`: Project overview and technical summary.
- *(upcoming)* `src/`: Planned modular implementation separating headers and sources for improved maintainability.

---

## 📖 Technical Concepts Explored

- Unix terminal manipulation using `termios.h`
- Direct manipulation of standard input/output streams
- Rendering control with ANSI escape sequences
- Non-canonical input handling and buffering
- File I/O using low-level syscalls
- Basic syntax parsing and highlighting
- Manual memory management strategies in C

---

## 🛠️ Build & Run Instructions

Ensure you have a Unix-like environment and `gcc` installed:

```bash
gcc -o kilo kilo.c
./kilo filename.txt
```

---

## 🚩 Technical Challenges

Key challenges encountered during development:

- **Raw Input Handling**: Transitioning from canonical to raw input required careful manipulation of terminal settings.
- **Efficient Screen Refreshing**: Minimizing screen flicker involved detailed use of escape sequences and a dynamic screen buffer.
- **Manual Syntax Highlighting**: Designing a lightweight syntax parser without relying on external libraries.
- **Cross-Platform Compatibility**: Ensuring consistent behavior across Linux and macOS posed challenges due to subtle system differences.
- **Graceful Exit and Cleanup**: Making sure terminal settings are restored correctly after exiting.

(For an in-depth breakdown, see [`TECHNICAL_CHALLENGES.md`](TECHNICAL_CHALLENGES.md))

---

## 📚 Inspiration & References

Inspired by the original [kilo editor](https://viewsourcecode.org/snaptoken/kilo/) by antirez. This implementation was created as an educational exercise to explore Unix internals, system programming in C, and terminal behavior.

---

## 📜 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for details.
