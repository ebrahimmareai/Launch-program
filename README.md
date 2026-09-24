# Automated Group Launcher & Smart Productivity Toolbox

A powerful, multi-functional desktop productivity application built with Python. This tool combines automated file/URL group launching, a smart background clipboard manager, and an instant translation hotkey to streamline your workflow without ever losing focus on your documents.

## Features

### Goal 1: Automated Group Launcher
- **Smart Discovery**: Easily select local files (`.exe`, `.pdf`, `.docx`, `.lnk`) or web URLs.
- **Group Management**: Create, edit, rename, and delete custom groups of items.
- **One-Click Launch**: Launch all programs, documents, and websites in a saved group simultaneously with a single click.

### Goal 2: Smart Clipboard & Database
- **Background Word Paste**: Paste copied text directly into Microsoft Word in the background without stealing focus from your PDF or browser.
- **Clipboard History**: Save copied text to a local SQLite database permanently.
- **History Viewer**: Browse, search, paste, or delete previously saved clipboard items.
- **Persistent Floating Toolbox**: An always-on-top mini-window for instant Quick Copy, Quick Paste, Database saving, and History viewing. *(Cleverly hides for a fraction of a second during actions to let your background app keep focus!)*

### Goal 3: Instant Translator Hotkey
- **Seamless Translation**: Select any text in a PDF or Word document, press a global hotkey (default: `Win + Ctrl + Z`), and instantly paste it into an already-open Google Translate Chrome tab.
- **Auto-Switch Back**: The app automatically switches focus back to your original document in milliseconds, so you never lose your place.
- **Customizable Hotkey**: Easily change the trigger key combination via the UI.

---

## Tech Stack

- **Language**: Python 3.x
- **GUI Framework**: `tkinter` (with `ttk` for modern styling)
- **Windows Automation**: `pywin32` (`win32gui`, `win32con`, `win32clipboard`, `win32com.client`)
- **Global Hotkeys**: `keyboard`
- **Database**: `sqlite3` (Local, persistent storage)
- **Architecture**: Modular 3-layer design (Business Logic, User Interface, Main Glue) using Jupyter Notebooks (`.ipynb`)

---

## Project Structure

The project is organized into modular Jupyter Notebooks for clean separation of concerns:

```text
├── business_logic.ipynb       # Core logic: File handling, group management, launching
├── business_logic_2.ipynb     # Goal 2 logic: Clipboard, SQLite database, Word automation
├── business_logic_3.ipynb     # Goal 3 logic: Global hotkeys, Chrome window management
├── user_interface.ipynb       # Tkinter UI design, button layouts, and popup windows
└── main.ipynb                 # The "Glue" cell: Imports all modules and starts the app
