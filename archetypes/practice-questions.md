---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
date: {{ .Date }}
weight: 1
tags: ["Programming", "Practice", "MCQ"]
author: ["Haziq Rohaizan"]
description: "Practice questions with MCQ format and dropdown answers"
showToc: true
TocOpen: true
draft: true
hidemeta: false
hideSummary: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>" # image path/url
    alt: "Programming Practice Questions" # alt text
    caption: "Practice Questions with Hidden Answers" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page
---

## Introduction

This is a template for creating programming practice questions with multiple-choice questions (MCQ) format. Each question has a dropdown where the answer is hidden until clicked.

## How to Use This Template

1. Replace the questions below with your own questions
2. Add options (A, B, C, D) for each question
3. Update the answer in the dropdown section
4. Add explanation if needed

---

## Practice Questions

### Question 1: [Replace with Your Question Title]

**Question:** What is the output of the following code?

```python
# Replace this with your code snippet
x = 5
y = 10
print(x + y)
```

**Options:**
- A) 5
- B) 10
- C) 15
- D) Error

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** C) 15

**Explanation:** The code adds x (5) and y (10) together, resulting in 15. Replace this explanation with your own.

</details>

---

### Question 2: [Replace with Your Question Title]

**Question:** Which of the following is NOT a valid data type in Python?

**Options:**
- A) int
- B) float
- C) char
- D) str

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** C) char

**Explanation:** Python does not have a 'char' data type. Single characters are represented as strings of length 1. Replace this explanation with your own.

</details>

---

### Question 3: [Replace with Your Question Title]

**Question:** What does the following function return?

```javascript
// Replace this with your code snippet
function example() {
    return 2 + 2;
}
```

**Options:**
- A) "4"
- B) 4
- C) 22
- D) undefined

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** B) 4

**Explanation:** The function performs addition of two numbers (2 + 2) and returns the result as a number (4), not a string. Replace this explanation with your own.

</details>

---

### Question 4: [Replace with Your Question Title]

**Question:** [Replace with your question text]

**Options:**
- A) [Option A]
- B) [Option B]
- C) [Option C]
- D) [Option D]

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** [Correct Option]

**Explanation:** [Explain why this is the correct answer and why other options are incorrect]

</details>

---

### Question 5: [Replace with Your Question Title]

**Question:** [Replace with your question text]

**Options:**
- A) [Option A]
- B) [Option B]
- C) [Option C]
- D) [Option D]

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** [Correct Option]

**Explanation:** [Explain why this is the correct answer and why other options are incorrect]

</details>

---

## Additional Notes

- You can add as many questions as you need by copying the question template
- The `<details>` and `<summary>` HTML tags create the dropdown functionality
- Style the questions as needed for your subject matter
- Add code snippets using markdown code blocks with language syntax highlighting

## Tips for Creating Good MCQ Questions

1. Make sure options are mutually exclusive
2. Avoid "All of the above" or "None of the above" when possible
3. Ensure distractors (wrong answers) are plausible
4. Keep explanations clear and concise
5. Test your questions before publishing

---

**Template created by:** Haziq Rohaizan
