### Text TO speech

```python
pip install gtts
```

```python
from gtts import gTTS
from IPython.display import Audio
text = input("Enter the text to convert to speech: ")
tts = gTTS(text=text,lang='ta',tld='co.in',slow = True)
tts.save("output.mp3")
Audio("output.mp3", autoplay=True)

```

```python
!pip install pytesseract #for google lens like ocr
```
### image TO Text

```python
from PIL import Image
import pytesseract
img = Image.open('/content/Gemini_Generated_Image_2f6ckc2f6ckc2f6c.png')
text = pytesseract.image_to_string(img)
print(text)
```


```

```
