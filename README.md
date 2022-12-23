from PIL import Image, ImageDraw, ImageFont
import pyqrcode

# Erstelle den QR-Code
url = "https://www.example.com"
qr = pyqrcode.create(url)
qr_size = 400  # Größe des QR-Codes in Pixeln
qr_image = qr.make_image(fill_color="black", back_color="white", size=qr_size)

# Öffne das Hintergrundbild
bg_image = Image.open("hintergrund.jpg")

# Setze den QR-Code auf den Hintergrund
bg_image.paste(qr_image, (100, 100))  # Platziere den QR-Code an den Koordinaten (100, 100)

# Erstelle eine Meldeanzeige für den QR-Code
draw = ImageDraw.Draw(bg_image)
font = ImageFont.truetype("arial.ttf", 36)
label = "Scan me!"
label_width, label_height = draw.textsize(label, font=font)
draw.text(((bg_image.width - label_width) / 2, qr_size + 150), label, font=font, fill=(0, 0, 0))

# Speichere das Bild mit dem QR-Code, Hintergrund und Meldeanzeige
bg_image.save("qr_code_with_bg_and_label.jpg")
<!-- Erstelle ein DIV-Element, in dem die Werbung angezeigt wird -->
<div id="ad-container">
  <!-- Füge das Google AdSense-Skript ein -->
  <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
  <script>
    (adsbygoogle = window.adsbygoogle || []).push({
      google_ad_client: "ca-pub-1234567890",  // Ersetze dies durch Ihre eigene AdSense-Publisher-ID
      enable_page_level_ads: true
    });
  </script>
</div>
