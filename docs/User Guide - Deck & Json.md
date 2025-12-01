📘 Deck Creation Guide for Quizzer Pro
Quizzer Pro allows you to load your own MCQ decks using simple .json files.
Follow this guide to create your own deck quickly and correctly.
________________________________________
✅ 1. Basic Deck Structure
Every deck must be a JSON array containing multiple questions:
[
  { ... },
  { ... },
  { ... }
]
Each item in the array is one MCQ question.
________________________________________
✅ 2. Required Format for Each Question
Each MCQ must follow this exact structure:
{
  "question": "Your question text here?",
  "options": ["Option A", "Option B", "Option C", "Option D"],
  "answer": "Option A",
  "explanations": {
    "Option A": "Explanation for Option A",
    "Option B": "Explanation for Option B",
    "Option C": "Explanation for Option C",
    "Option D": "Explanation for Option D"
  }
}
Field rules
•	"question" → A string (the question text)
•	"options" → Exactly 4 options, in a list
•	"answer" → Must exactly match one of the options (case-sensitive)
•	"explanations" → Each option must appear again as a key with its explanation
________________________________________
⚠ Important Notes
To avoid errors:
1. Options must match exactly
If you write:
"Option A"
then the explanations must also use:
"Option A"
Case, spaces, punctuation must match.
2. Don’t add extra fields
Stick exactly to:
•	question
•	options
•	answer
•	explanations
3. Make sure your JSON is valid
Use a validator such as:
https://jsonlint.com/
________________________________________
📄 3. Example Deck with Two Questions
[
  {
    "question": "What is the main function of hemoglobin?",
    "options": ["Transport oxygen", "Digest proteins", "Store fat", "Produce antibodies"],
    "answer": "Transport oxygen",
    "explanations": {
      "Transport oxygen": "Hemoglobin binds and carries oxygen in red blood cells.",
      "Digest proteins": "Proteins are digested by enzymes, not hemoglobin.",
      "Store fat": "Fat is stored in adipose tissue.",
      "Produce antibodies": "Antibodies are made by B-cells, not RBCs."
    }
  },
  {
    "question": "Which organ produces insulin?",
    "options": ["Liver", "Pancreas", "Kidney", "Heart"],
    "answer": "Pancreas",
    "explanations": {
      "Liver": "The liver does not produce insulin.",
      "Pancreas": "Insulin is produced by beta cells in the pancreas.",
      "Kidney": "The kidneys filter blood but do not produce insulin.",
      "Heart": "The heart pumps blood, not insulin."
    }
  }
]
________________________________________
💾 4. Saving Your Deck
1.	Create a new text file
2.	Paste your JSON deck
3.	Save as:
mydeck.json
4.	Place it anywhere you like — the app can open it using Load Deck.
________________________________________
🚀 5. Tips for Better MCQs
•	Write options that are plausible but incorrect
•	Keep explanations short, clear, and focused
•	Avoid repeating the same explanation across many options
•	Make the correct answer unambiguous

