
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
