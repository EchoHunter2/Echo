## Hi there 👋

<!--
**EchoHunter2/EchoHunter2** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
pip install openai
import openai
{
  "public": "d16fbddec956190255f61fd38c56d04b027ac5e3f14ad9e974cd45ed9645ef91",
  "private": "a2068a7b163e5d76dc7d0f27f2205329ad14f762e4f10f2fab879311e15f8c2e"
}
openai.api_key = 'your-api-key-here'

def generate_response(prompt):
    response = openai.Completion.create(
        engine="text-davinci-003",  # หรือโมเดลที่คุณต้องการใช้
        prompt=prompt,
        max_tokens=150,
        n=1,
        stop=None,
        temperature=0.9,
    )
    message = response.choices[0].text.strip()
    return message

def chat():
    print("Chatbot: สวัสดี! ฉันคือแชทบอท มีอะไรให้ช่วยไหม?")
    while True:
        user_input = input("You: ")
        if user_input.lower() in ["ออก", "จบ", "บ๊ายบาย"]:
            print("Chatbot: ลาก่อน!")
            break
        response = generate_response(user_input)
        print(f"Chatbot: {response}")

if __name__ == "__main__":
    chat()
