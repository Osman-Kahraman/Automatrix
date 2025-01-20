# Automatrix - PDF Highlight Extraction and Automation

![automatrix](https://github.com/user-attachments/assets/4d975e07-1bfc-4b58-bdfb-628539ed4d37)

Automatrix is a Python script that extracts highlighted text from PDF documents and automates typing those extracted texts into other applications using PyAutoGUI. It identifies areas highlighted in yellow and processes them for automation tasks. The script is especially useful for automating data entry based on highlighted sections in PDFs.

### Features:
- **PDF Highlight Extraction**: Scans PDF pages for highlighted areas and extracts the corresponding text.
- **Automation**: Automatically types the extracted text into any open application using simulated keystrokes.
- **Customization**: The script allows users to input the PDF file name and processes it accordingly.

### Requirements:
- Python 3.x
- Libraries: `PyAutoGUI`, `PyMuPDF (fitz)`, `Pillow`, `NumPy`

### Usage:
1. Place your PDF in the same directory as the script.
2. Run the script:
```bash
python Automatrix.py
```
3. Provide the PDF name when prompted.
4. The script will start typing the extracted highlights into the target application after a countdown.
