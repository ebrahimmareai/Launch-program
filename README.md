# Automated Group Launcher & Productivity Toolbox

A multi-functional desktop productivity application built with Python. This tool combines automated file/URL group launching, a background clipboard manager, and an instant translation hotkey to streamline workflow.

## Features

### Goal 1: Automated Group Launcher
- **Discovery**: Easily select local files (`.exe`, `.pdf`, `.docx`, `.lnk`) or web URLs.
- **Group Management**: Create, edit, rename, and delete custom groups of items.
- **One-Click Launch**: Launch all programs, documents, and websites in a saved group.

### Goal 2: Clipboard & Database
- **Background Word Paste**: Paste copied text directly into Microsoft Word in the background without losing focus from PDF or browser.
- **Clipboard History**: Save copied text to a local SQLite database.
- **History Viewer**: Browse, search, paste, or delete previously saved clipboard items.
- **Persistent Floating Toolbox**: An on-top mini-window for Copy, Paste, Database saving, and History viewing.

### Goal 3: Translator Hotkey
- **Translation**: Select any text in a PDF or Word document, press a global hotkey (default: `Win + Ctrl + Z`), and paste it into an already-open Google Translate Chrome tab.
- **Auto-Switch Back**: The app automatically switches focus back to your original document, so user don't lose focus.
- **Customizable Hotkey**: Easily change the trigger key combination via the UI.

---

## Tech Stack

- **Language**: Python 3
- **GUI Framework**: `tkinter` (with `ttk` for modern styling)
- **Windows Automation**: `pywin32` (`win32gui`, `win32con`, `win32clipboard`, `win32com.client`)
- **Database**: `sqlite3` (Local)
- **Architecture**: Modular 3-layer design (Business Logic, User Interface, Main Glue) using Jupyter Notebooks (`.ipynb`)

---

## Project Structure

The project is organized into modular Jupyter Notebooks:

```text
├── business_logic.ipynb       # Goal 1 logic: File handling, group management, launching
├── business_logic_2.ipynb     # Goal 2 logic: Clipboard, SQLite database, Word automation
├── business_logic_3.ipynb     # Goal 3 logic: Global hotkeys, Chrome window management
├── user_interface.ipynb       # Tkinter UI design, button layouts, and popup windows
└── main.ipynb                 # The "Glue" cell: Imports all modules and starts the app
