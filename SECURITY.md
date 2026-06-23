# Security & Privacy Overview

## How Your Files Are Protected

### Browser Tool
The web version processes files entirely inside your browser using JavaScript. No file content is ever uploaded to a server — the PDF stays on your machine from start to finish. There is no account, no login, and no data is stored or transmitted anywhere.

### Desktop App (.exe)
The Windows desktop app runs fully offline. It reads your files, writes fixed copies to an output folder you choose, and produces an HTML report — all locally. It does not connect to the internet, does not send telemetry, and requires no account or API key. Your original files are never modified; the app only writes new copies.

### Both versions:
- Never transmit document content outside the user's device
- Require no account, login, or credentials
- Leave originals untouched
- Do not log or retain any file contents

---

## Open-Source Components

All components are widely used, publicly auditable open-source projects with no proprietary or closed elements.

### Desktop App
The desktop app is written in Python and packaged as a standalone Windows `.exe` using PyInstaller.

| Library | Purpose | License |
|---|---|---|
| [pikepdf](https://github.com/pikepdf/pikepdf) | PDF structure reading and writing | MIT |
| [pdfplumber](https://github.com/jsvine/pdfplumber) | PDF text and content extraction | MIT |
| [pypdfium2](https://github.com/pypdfium2-team/pypdfium2) | Rendering figure regions | Apache 2.0 |
| [pdf2docx](https://github.com/dothinking/pdf2docx) | PDF-to-Word conversion (untagged→tagged path) | MIT |
| [python-docx](https://github.com/python-openxml/python-docx) | Word document manipulation | MIT |
| [pywin32](https://github.com/mhammond/pywin32) | Windows COM automation for Office re-export | PSF |
| [ocrmypdf](https://github.com/ocrmypdf/OCRmyPDF) | OCR for scanned pages (optional) | MPL 2.0 |
| tkinter | GUI framework | Python PSF |
| [PyInstaller](https://github.com/pyinstaller/pyinstaller) | Packaging as standalone .exe | GPL + bootloader exception |

### Browser Tool
The browser tool is written in JavaScript and runs entirely client-side.

| Library | Purpose | License |
|---|---|---|
| [pdf-lib](https://github.com/Hopding/pdf-lib) | PDF creation and modification | MIT |
| [pdfjs-dist](https://github.com/mozilla/pdf.js) | PDF parsing and rendering | Apache 2.0 (Mozilla) |
| [React](https://github.com/facebook/react) | UI framework | MIT |

---

## Code-Signing Notice

The desktop app is not code-signed. Windows will show a **"Windows protected your PC"** dialog on first run. Click **More info → Run anyway** to proceed.

This is a distribution cost limitation (code-signing certificates require an annual purchase), not a security defect. The app does not perform any action that would trigger antivirus detection. If your organization requires signed executables, please contact Page Durham (LearnAIID) to discuss deployment options.
