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
!pip install googletrans==4.0.0-rc1 #google translation```
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


