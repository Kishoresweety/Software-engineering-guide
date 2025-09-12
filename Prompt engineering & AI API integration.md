# 🤖 Prompt Engineering & AI API Integration

🔹 1. What is Prompt Engineering?

Prompt engineering is the art of designing instructions (prompts) to get the best output from AI models like GPT, Claude, Gemini.

👉 Instead of coding everything manually, you tell the AI what to do.
Example:

Bad Prompt → “Write code.”

Good Prompt → “Write Python code that reads a CSV file of student marks, calculates the average, and prints pass/fail for each student.”



---

🔹 2. Prompt Types

1. Zero-shot → Just ask directly.

“Translate this text into French.”



2. Few-shot → Give examples first.

“Translate the following: Hello → Bonjour, Thank you → Merci. Now translate: Good night → ?”



3. Chain-of-thought → Ask AI to show reasoning step-by-step.


4. Role-based → Tell AI who it is.

“You are a cybersecurity expert. Explain firewall basics simply.”





---

🔹 3. AI API Integration

Common AI APIs:

OpenAI API (ChatGPT models)

Google Gemini API

Anthropic Claude API

Hugging Face Transformers API


These let you use AI inside your apps.


---

Example: Python + OpenAI API

import openai

openai.api_key = "YOUR_API_KEY"

response = openai.ChatCompletion.create(
    model="gpt-4o-mini",
    messages=[
        {"role": "system", "content": "You are a helpful coding assistant."},
        {"role": "user", "content": "Write Python code to check if a number is prime."}
    ]
)

print(response["choices"][0]["message"]["content"])

👉 This will return AI-generated Python code for prime number check.


---

Example: C++ app calling AI API (via curl)

#include <cstdlib>
#include <iostream>
using namespace std;

int main() {
    system("curl https://api.openai.com/v1/chat/completions "
           "-H \"Content-Type: application/json\" "
           "-H \"Authorization: Bearer YOUR_API_KEY\" "
           "-d '{\"model\": \"gpt-4o-mini\", "
           "\"messages\": [{\"role\": \"user\", \"content\": \"Explain binary search\"}]}'");
    return 0;
}

👉 This C++ program calls AI API using curl.


---

Example: Simple English Use Case

🛒 E-commerce chatbot:

Prompt → “You are a shopping assistant. Help customers choose a laptop under ₹50,000.”

AI API → Returns best recommendations.


⚡ Advantage: Instead of coding decision logic, you delegate to AI.


---

🔹 4. Best Practices for Prompt Engineering

Be specific → Detailed prompts give better results.

Set role → Define AI’s behavior.

Provide context → Give background info.

Iterate → Refine prompts until results are correct.



---

🔹 5. Real-World Examples

SOC Analyst Assistant → AI analyzes logs & detects threats.

Resume Optimizer → Upload JD + resume → AI tailors it.

Language Tutor → “Teach me English step by step with exercises.”

Healthcare Bot → Patient symptoms → AI suggests next steps.



---

✅ Summary:

Prompt Engineering = how you talk to AI.

AI API Integration = how you use AI in apps.

Together → Build smart apps faster.



---
