# Security & Privacy Overview

*Last updated: July 14, 2026 (browser v1.15, Windows app v1.13)*

## How Your Files Are Protected

### Browser Tool
The web version processes files entirely inside your browser using JavaScript and WebAssembly. No file content is ever uploaded to a server — the PDF stays on your machine from start to finish. Every capability, including OCR of scanned pages and the optional AI-drafted image descriptions, runs locally in the browser tab. There is no account, no login, and no document data is stored or transmitted anywhere. Closing the tab discards everything.

**What the page downloads (inbound only, never document data):**
- The app itself, its fonts (self-hosted — no Google Fonts requests), and the English OCR engine, all served from the site's own host.
- If you enable AI descriptions: the Florence-2 vision model (~220 MB, one time, cached by the browser) from the Hugging Face open-source model library. The model is downloaded **to** your device; your images and documents are never sent anywhere.
- OCR language packs for Spanish, French, or German are fetched from a public library on first use; English is bundled with the site.

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
The browser tool is written in JavaScript/TypeScript and runs entirely client-side.

| Library | Purpose | License |
|---|---|---|
| [pdf-lib](https://github.com/Hopding/pdf-lib) | PDF creation and modification | MIT |
| [pdfjs-dist](https://github.com/mozilla/pdf.js) | PDF parsing and rendering | Apache 2.0 (Mozilla) |
| [tesseract.js](https://github.com/naptha/tesseract.js) | OCR for scanned pages (WebAssembly, in-browser) | Apache 2.0 |
| [transformers.js](https://github.com/huggingface/transformers.js) | Runs the optional on-device AI model | Apache 2.0 |
| [Florence-2-base](https://huggingface.co/onnx-community/Florence-2-base-ft) | Vision model for AI-drafted alt text (optional) | MIT |
| [franc-min](https://github.com/wooorm/franc) | Document language detection | MIT |
| [React](https://github.com/facebook/react) | UI framework | MIT |

### About the optional AI feature
The AI image-description feature is strictly opt-in and runs the model on your own device (GPU via WebGPU when available, CPU otherwise). It performs exactly one kind of network request: downloading the open-source model files from Hugging Face, once, like downloading any other part of the app. No image, text, or document data is ever transmitted. If you never click the AI button, nothing related to it is downloaded at all.

---

## Code-Signing Notice

The desktop app is not code-signed. Windows will show a **"Windows protected your PC"** dialog on first run. Click **More info → Run anyway** to proceed.

This is a distribution cost limitation (code-signing certificates require an annual purchase), not a security defect. The app does not perform any action that would trigger antivirus detection. If your organization requires signed executables, please contact Page Durham (LearnAIID) to discuss deployment options.
