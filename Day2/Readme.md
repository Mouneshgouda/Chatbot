
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

## SIMPLE CHATBOT USING GEMINI API KEY

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


# RAG Chatbot Bussiness

```python

# Install dependencies (run once)
!pip install --upgrade google-generativeai pandas

import pandas as pd
import google.generativeai as genai
from getpass import getpass

api_key = getpass("Enter your Google API Key: ")

genai.configure(api_key=api_key)
model = genai.GenerativeModel("gemini-2.5-flash")

csv_path = "/content/business_data.csv"
df = pd.read_csv(csv_path)

context_text = ""
for _, row in df.iterrows():
    context_text += f"Q: {row['question']}\nA: {row['answer']}\n\n"

def ask_gemini(query):
    prompt = f"""
You are a Q&A assistant.

Answer ONLY using the context below.
If the answer is not present, say: No relevant Q&A found.

Context:
{context_text}

Question: {query}
"""
    response = model.generate_content(prompt)
    return response.text.strip()

print("Chatbot is running! Type 'exit' to quit.\n")
while True:
    user_input = input("You: ")
    if user_input.lower() == "exit":
        print("Goodbye!")
        break
    answer = ask_gemini(user_input)
    print(f"Bot: {answer}\n")
```


