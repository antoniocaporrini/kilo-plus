# Technical Challenges – kilo.c

This document outlines key technical challenges faced during the development of the kilo.c text editor and the strategies used to overcome them.

## 1. Raw Input Mode Handling

**Challenge**: Reading individual keystrokes without buffering required bypassing the terminal's canonical mode.

**Solution**: Implemented raw mode using `termios.h`, carefully saving and restoring terminal settings to prevent corrupted states after program exit.

## 2. Screen Flickering and Rendering

**Challenge**: Naïve screen clearing caused excessive flickering and cursor misalignment.

**Solution**: Created an in-memory buffer (append buffer) to store all screen output, which is flushed at once. Used ANSI escape sequences for precise control of cursor movement and screen clearing.

## 3. Arrow Key Interpretation

**Challenge**: Special keys (like arrows) send multiple characters (escape sequences) that must be parsed correctly.

**Solution**: Wrote a custom parser to interpret sequences such as `[A` for UP and mapped them to cursor actions.

## 4. File I/O

**Challenge**: Efficiently reading and writing files while maintaining buffer consistency.

**Solution**: Implemented basic file loading and saving using standard POSIX functions (`open`, `read`, `write`). Buffer is updated line-by-line and written back in raw format.

## 5. Syntax Highlighting

**Challenge**: Providing lightweight and extensible syntax highlighting without external libraries.

**Solution**: Wrote a basic parser for file extensions and keywords, using ANSI color codes. Kept it modular to support future language definitions.

## 6. Cross-Platform Behavior

**Challenge**: Ensuring consistent editor behavior on both macOS and Linux terminals.

**Solution**: Avoided platform-specific syscalls. Relied on POSIX-compliant terminal control APIs and avoided features not available on both systems.
