# 📘 Deck Creation Guide for **Quizzer Pro**

Quizzer Pro allows you to load your own MCQ decks using simple `.json`
files.\
Follow this guide to create your deck quickly and correctly.

------------------------------------------------------------------------

## ✅ 1. Basic Deck Structure

Every deck must be a JSON array containing multiple questions:

``` json
[
  { ... },
  { ... },
  { ... }
]
```

Each item in the array is one MCQ question.

------------------------------------------------------------------------

## ✅ 2. Required Format for Each Question

Each MCQ must follow this exact structure:

``` json
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
```

### **Field Rules**

-   **`question`** → A string (the question text)\
-   **`options`** → Exactly **4** options, in a list\
-   **`answer`** → Must *match exactly* one of the options
    (case-sensitive)\
-   **`explanations`** → Must list all four options again as keys, each
    with an explanation

------------------------------------------------------------------------

## ⚠ Important Notes

To avoid errors:

### **1. Options must match exactly**

If you write:

    "Option A"

then the explanation must also use:

    "Option A"

Case, spaces, and punctuation must match.

### **2. Don't add extra fields**

Use only these fields:

-   `question`\
-   `options`\
-   `answer`\
-   `explanations`

### **3. Ensure your JSON is valid**

Use a validator like:\
https://jsonlint.com/

------------------------------------------------------------------------

## 📄 3. Example Deck with Two Questions

``` json
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
```

------------------------------------------------------------------------

## 💾 4. Saving Your Deck

1.  Create a new text file\
2.  Paste your JSON deck\
3.  Save it as:\
    **`mydeck.json`**\
4.  Load it in the app using **Load Deck**

------------------------------------------------------------------------

## 🚀 5. Tips for Better MCQs

-   Write options that are plausible but incorrect\
-   Keep explanations short, clear, and focused\
-   Avoid repeating the same explanation across many options\
-   Make the correct answer unambiguous
