## Conversational AI And ChatBot


https://medium.com/@mouneshpatil001/what-is-conversational-ai-8fb546be64cd


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
## Text To Translate

```python
!pip install googletrans==4.0.0-rc1 #google translation
```

```python
#translation service googletrans
from googletrans import Translator
tran = Translator()
# Assign a sample text for translation to avoid the error
text_to_translate = "Hello, how are you?"
tran = tran.translate(text_to_translate,src='auto',dest='ka') #en
print(tran.text)
```

## Text To Image



```python

from transformers import pipeline
import torch
from diffusers import DiffusionPipeline

# Load the image generation pipeline using diffusers
generator = DiffusionPipeline.from_pretrained("CompVis/stable-diffusion-v1-
generator.to("cuda")

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

