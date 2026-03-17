## Dummy Chatbot

```python
from transformers import pipeline

# Create chatbot pipeline
chatbot = pipeline("text-generation", model="microsoft/DialoGPT-small")

print("Chatbot: Hi! Type 'bye' to exit.")

while True:


    user_input = input("You: ")

    if user_input.lower() == "bye":
        print("Chatbot: Goodbye!")
        break

    response = chatbot(user_input, max_length=50, num_return_sequences=1)

    print("Bot:", response[0]["generated_text"])
```

## Simple Chatbot Using Gemini API KEY

```python

import getpass
import os
from langchain_google_genai import ChatGoogleGenerativeAI
if not os.environ.get("GOOGLE_API_KEY"):
    os.environ["GOOGLE_API_KEY"] = getpass.getpass("Enter API key for Google Gemini: ")
model = ChatGoogleGenerativeAI(model="gemini-2.5-flash")
print("Chat started. Type 'exit' to stop.\n")
while True:
    user_input = input("You: ")
    if user_input.lower() in ["exit", "quit"]:
        print("Goodbye!")
        break
    response = model.invoke(user_input)
    print("Model:", response.content + "\n")



```
