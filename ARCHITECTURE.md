# Architecture – kilo.c

This document provides a high-level overview of the design and architecture of the kilo.c text editor.

## Design Philosophy

The project was intentionally kept minimal and monolithic to ensure clarity and full control over terminal I/O. It follows an educational-first structure, mirroring the incremental development style of the original tutorial.

## Current Structure

- **Single Source File**: All code resides in `kilo.c`, containing logic for:
  - Raw mode terminal setup
  - Input processing
  - Buffer management
  - Screen rendering
  - File I/O
  - Syntax highlighting

- **Core Data Structures**:
  - `EditorConfig`: Stores global editor state
  - `erow`: Represents a single line of text in the editor buffer

## Rendering Flow

1. **Read Input**: Character-by-character using raw mode
2. **Update State**: Cursor position, screen offset, buffer content
3. **Build Output**: Using an append buffer to concatenate output
4. **Flush to Terminal**: Output is rendered in a single write syscall

## Planned Modular Refactor (future scope)

Although the current version is complete and monolithic, a modular refactor is planned to separate concerns into distinct files:

- `input.c/h`: Keystroke processing
- `editor.c/h`: Editor logic and rendering
- `syntax.c/h`: Syntax highlight rules
- `fileio.c/h`: File read/write
- `main.c`: Program entry point

This separation would improve readability, maintainability, and testability of the codebase.
