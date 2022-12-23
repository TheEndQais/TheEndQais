from PIL import Image, ImageDraw, ImageFont
import os

# Erstelle eine Liste mit den Pfaden zu den Bilddateien, die du konvertieren möchtest
image_paths = ["bild1.jpg", "bild2.jpg", "bild3.png"]

# Erstelle ein neues PDF-Dokument
pdf_path = "bilder.pdf"
pdf_pages = []

# Konvertiere jedes Bild in eine PDF-Seite und füge sie dem PDF-Dokument hinzu
for path in image_paths:
    img = Image.open(path)

    # Erstelle ein Textlabel für jede PDF-Seite
    draw = ImageDraw.Draw(img)
    font = ImageFont.truetype("arial.ttf", 36)
    label = os.path.splitext(os.path.basename(path))[0]
    label_width, label_height = draw.textsize(label, font=font)
    draw.text(((img.width - label_width) / 2, 10), label, font=font, fill=(0, 0, 0))

    # Füge das Bild zum PDF-Dokument hinzu
    pdf_pages.append(img.convert("RGB"))

# Speichere das PDF-Dokument
pdf_pages[0].save(
    pdf_path, "PDF" ,resolution=100.0, save_all=True, append_images=pdf_pages[1:]
)
