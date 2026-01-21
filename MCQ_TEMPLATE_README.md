# MCQ Practice Questions Template

This template allows you to create blog posts with Multiple Choice Questions (MCQ) that have hidden answers in dropdown format.

## Features

- ✅ Clean MCQ format with dropdown answers
- ✅ Syntax highlighting for code snippets
- ✅ Responsive design that works on all devices
- ✅ Dark mode support
- ✅ No JavaScript required - uses native HTML5 `<details>` and `<summary>` tags
- ✅ Custom CSS styling for better visual presentation

## Files Included

1. **Template Post**: `/content/posts/programming-practice-questions-template.md`
   - A complete example post with 5 sample MCQ questions
   - Shows different question formats (with and without code)
   - Includes instructions and tips

2. **Custom CSS**: `/static/css/mcq-style.css`
   - Styles for dropdown answers
   - Hover effects and transitions
   - Dark mode support

3. **Theme Integration**: `/layouts/partials/extend_head.html`
   - Links the custom CSS to all pages

## How to Use

### Step 1: Copy the Template

1. Navigate to `/content/posts/programming-practice-questions-template.md`
2. Copy the entire file to create your own post
3. Rename it to something like `my-subject-practice-questions.md`

### Step 2: Update the Frontmatter

Edit the YAML frontmatter at the top of your file:

```yaml
---
title: "Your Subject Practice Questions"
date: 2024-01-20T22:26:00Z
weight: 1
tags: ["YourSubject", "Practice", "MCQ"]
author: ["Your Name"]
description: "Practice questions for [Your Subject]"
showToc: true
TocOpen: true
draft: false
---
```

### Step 3: Add Your Questions

Replace the sample questions with your own. Each question follows this format:

```markdown
### Question 1: [Your Question Title]

**Question:** What is the output of the following code?

```python
# Your code here
x = 5
print(x)
```

**Options:**
- A) Option A
- B) Option B  
- C) Option C
- D) Option D

<details>
<summary><strong>Click to reveal answer</strong></summary>

**Answer:** C) Option C

**Explanation:** Explain why this is the correct answer.

</details>
```

### Step 4: Preview and Publish

1. Run `hugo server` to preview your post locally
2. When satisfied, commit and push to publish

## Customization

### Change Answer Button Text

Edit the `<summary>` tag:
```html
<summary><strong>Click to see solution</strong></summary>
```

### Modify Colors

Edit `/static/css/mcq-style.css` to change:
- Border colors
- Background colors
- Hover effects
- Dark mode appearance

### Add More Question Types

You can add:
- True/False questions
- Fill in the blank
- Code debugging questions
- Diagram-based questions

Just maintain the same dropdown structure for answers.

## Tips for Creating Good MCQs

1. **Make options mutually exclusive** - Each option should be clearly different
2. **Avoid obvious answers** - All options should seem plausible
3. **Include explanations** - Help students learn from wrong answers
4. **Use code examples** - Make questions practical and relevant
5. **Test your questions** - Review them before publishing

## Technical Details

- **HTML5 Details Element**: The dropdown uses native `<details>` and `<summary>` tags
- **No JavaScript Required**: Works without any JavaScript dependencies
- **Accessible**: Screen reader friendly and keyboard navigable
- **Markdown Compatible**: Works seamlessly with Hugo's markdown processing

## Example Post Location

The template is available at:
- File: `/content/posts/programming-practice-questions-template.md`
- URL: `https://yourdomain.com/posts/programming-practice-questions-template/`

## Support

For issues or questions about this template, please refer to the Hugo and PaperMod documentation.

---

**Created by:** Haziq Rohaizan  
**Last Updated:** 2024-01-20
