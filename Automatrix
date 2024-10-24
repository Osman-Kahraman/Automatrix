import pyautogui as gui
import time
import fitz
from PIL import Image
import numpy as np

pdffile = input("PDF name?: ").replace('"', "")
if not pdffile.endswith(".pdf"):
    pdffile += ".pdf"
inputs = []

doc = fitz.open(pdffile)
for page_ in range(0, len(doc) - 1):
    page = doc.load_page(page_)
    pix = page.get_pixmap()

    img = Image.frombytes("RGB", [pix.width, pix.height], pix.samples)

    yellow = [255, 255, 0]
    img_array  = np.array(img)
    y, x = np.where(np.all(img_array == yellow, axis = 2))

    highlights = []
    if x.any():
        highlights.append([x[0], y[0]])
    for i, j, k, l in zip(x, y, x[1::], y[1::]):
        if (abs(i - k) > 8 and abs(j - l) > 1) or (abs(i - k) > 1 and abs(j - l) > 15):
            highlights.append([i, j])
            highlights.append([k, l])
    if x.any():
        highlights.append([x[-1], y[-1]])

    for i, j in zip(highlights[::2], highlights[1::2]):
        inputs.append(page.get_textbox(fitz.Rect([i[0], i[1] + 2, j[0], j[1] - 2])))
doc.close()

print("You should open the target!!!")
count_down = 9
while True:
    print("\r" + str(count_down), end = "")
    count_down -= 1
    time.sleep(1)
    
    if count_down <= 0:
        print("\n----Started----")
        break

for i in inputs:
    if i != "YELLOW" and len(i) <= 10:
        gui.typewrite(i + "\n")
