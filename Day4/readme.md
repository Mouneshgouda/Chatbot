Deep Learning

https://skemato.com/nn-playground/

## Building Ollama Agent Step By Step Guidelines

### Step1

<img width="2621" height="1350" alt="image" src="https://github.com/user-attachments/assets/8b2548c1-5501-472f-89cc-859454dae76f" />


### step2

<img width="1878" height="1539" alt="image" src="https://github.com/user-attachments/assets/547a8037-a274-43b3-9ce0-3b768c029149" />


### step3

<img width="2667" height="1473" alt="image" src="https://github.com/user-attachments/assets/c22e614f-390e-4f9b-a86c-df64761a0f94" />


### step4

<img width="2661" height="1541" alt="image" src="https://github.com/user-attachments/assets/7fade06d-3701-4b33-83fe-07bfacd8e33c" />


### step5

<img width="2629" height="1518" alt="image" src="https://github.com/user-attachments/assets/6a64e5cd-d5ae-48b4-8264-afef834a97da" />


### step6

<img width="2706" height="1355" alt="image" src="https://github.com/user-attachments/assets/c20bd086-adf2-4c11-b4e3-d55d44f48416" />


### step7

<img width="2520" height="1273" alt="image" src="https://github.com/user-attachments/assets/3e1b89f4-fed0-4d7b-a48c-68a38fcce1c3" />


### step8

<img width="2140" height="1263" alt="image" src="https://github.com/user-attachments/assets/f1eb5e0d-da5e-494e-a354-2ba7c1bf2406" />


### step9


<img width="2483" height="1410" alt="image" src="https://github.com/user-attachments/assets/e360c4d3-3024-44a6-9e9c-a5dd0c1e611e" />


### step10


<img width="2558" height="1489" alt="image" src="https://github.com/user-attachments/assets/dabcd704-eead-4ada-80a4-cde9866c828c" />

### step11

<img width="2592" height="1501" alt="image" src="https://github.com/user-attachments/assets/86601b7e-4a2f-4ea5-bdf3-bba710317a1a" />


### Step12

<img width="2617" height="1490" alt="image" src="https://github.com/user-attachments/assets/45baa8fc-4bb5-464f-97b8-a9362949df5c" />


### step13


<img width="2493" height="1367" alt="image" src="https://github.com/user-attachments/assets/6452d0a4-1d6f-4564-914c-b9aea799d3cc" />


### step14


<img width="1844" height="1188" alt="image" src="https://github.com/user-attachments/assets/7b3ff065-1398-4047-a5c9-caed78788df7" />


### step15


<img width="2439" height="1440" alt="image" src="https://github.com/user-attachments/assets/9120a92a-ca08-476c-a1c2-5315f36751f8" />


### step16

<img width="2080" height="1422" alt="image" src="https://github.com/user-attachments/assets/58c1eae2-d941-4418-8270-88adff98fd58" />


### step17


<img width="2030" height="1434" alt="image" src="https://github.com/user-attachments/assets/a1cb6188-306c-4e6f-a550-2ac8e67bc5a1" />


### step18


<img width="2030" height="1370" alt="image" src="https://github.com/user-attachments/assets/d9366004-aa18-46d8-a989-8c6979cb0757" />


### step19


<img width="2183" height="1389" alt="image" src="https://github.com/user-attachments/assets/7d1fdd6d-8b3a-4217-ac1f-5e9f240fc451" />

```python

from agno.agent import Agent
from agno.models.ollama import Ollama

model = Ollama("llama3.2:1b")

agent = Agent(
    name="Diet Plan",
    model=model,
     instructions="""
You are a Personal diet coach.

Rules:
1. help me to make diet plan
2.whenever u see diet then  only response otherwise say:
plese say:it's not a diet plan.
"""
)

print("🐍 Python Interview Agent")
print("Type 'exit' to quit")
print("=" * 50)

while True:
    user_input = input("\nYou: ").strip()

    if user_input.lower() == "exit":
        print("Goodbye 👋")
        break

    response = agent.run(user_input)

    print("\n🤖 Agent:")
    print(response.content)
    print("=" * 50)

```


### step20

<img width="2071" height="1632" alt="image" src="https://github.com/user-attachments/assets/3507b018-9c17-4944-bb25-96e2dfe137fa" />
