# PDF Accessibility Remediator — Desktop App (Windows)

A free double-click Windows program that fixes common PDF accessibility
problems toward **WCAG 2.1 AA** (the standard behind the DOJ Title II
requirements). Built for people who are **not** technical — no Python, no
command line, no account, no API key.

## ⬇️ Download

**[Download the app (.zip)](https://github.com/BelovedCoachP/pdf-remediator-app/releases/latest/download/PDF-Accessibility-Remediator-app.zip)**

Then:
1. Unzip it anywhere (right-click → **Extract All**). Keep the folder together.
2. Double-click **PDF Accessibility Remediator.exe**.
3. If Windows shows "Windows protected your PC", click **More info → Run
   anyway** (the app isn't code-signed; this is expected and safe).
4. Add PDFs, tick the fixes you want, click **Remediate PDFs**.

## What it does

Your **original files are never changed.** For each PDF it writes a fixed copy
plus an easy-to-read HTML report (what was fixed, what still needs a human) to
an output folder.

Automatic fixes: document title and language; heading structure and bookmarks;
real data-table headers with row/column scope; layout-table handling; empty
"blank paragraph" cleanup; link descriptions; form-field labels.

Optional (tick the box): convert untagged PDFs to tagged (**needs Microsoft
Word**), OCR scanned pages (**needs Tesseract + Ghostscript**), darken
low-contrast text. Options that need software you don't have grey out by
themselves.

It does **not** use AI alt text, so there's nothing to sign up for. Describe
images yourself using the review worksheet the app can produce.

## What your PC needs

- **Most fixes:** nothing — it's all built in.
- **Convert untagged PDFs:** Microsoft Word installed (most PCs have it).
- **OCR scanned pages:** optional free tools (Tesseract + Ghostscript).
- Windows 10 or 11.

## Questions

Contact Page Durham (LearnAIID).

---
*This repository hosts the downloadable app only. The source code lives in a
separate private repository.*
