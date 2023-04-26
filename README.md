# PromptMaster: Collaborative-Efforts-to-Improve-Code-Prompts-with-ChatGPT

This is a practical guide on how to optimize  ChatGPT prompts for programming. Here, I aimed to provide tips and techniques to help developers optimize their chatgpt prompts to avoid common problems and improve their code generation experience. .

## Table of Contents

1.  [Dealing with truncated code](#1-dealing-with-truncated-code)
2. [Ensuring generated code is in code block format](#2-ensuring-generated-code-is-in-code-block-format)
3. Handling unfamiliar libraries and frameworks
4. Providing specific constraints and requirements
5. Defensive programming prompt and error handling
6. Providing project dictionary and prerequisite information
7. Omitting imports in generated code
8. Writing only suggested changes in code
9. Redacting similar parts of code while keeping key headers and functions
10. Adding comments in code to refer to specific parts
11. Prompting ChatGPT to acclimate to updated libraries and documentation
12. Handling custom functions and methods
13. Writing efficient and concise code
14. Providing snippet of database or dataset structure
15. Encouraging diverse solutions
16. Sharing long code or multiple files and asking it to keep track and note

## 1. Dealing with Truncated Code
<a name="1-dealing-with-truncated-code"></a>
**Problem:** The generated code is too long and gets cut off, and when asking ChatGPT to continue from where it stopped, it starts over instead of continuing the code. To prevent this, you can either:

- Break down the prompt into smaller, more focused tasks.
- Explicitly ask ChatGPT to provide a concise solution.
- Increase the max_tokens parameter, but be cautious about potential performance issues.

**Perfect Prompt:**

```markdown
ChatGPT, your answer got truncated. Please continue the previously generated code without repeating any part of it. The last part of the previous code snippet was:

<Insert the last few lines of the generated code here>

Continue generating the remaining code from this point onwards, ensuring that the solution picks up where it left off and does not start over.
```

## 2. Ensuring generated code is in code block format
<a name="2-ensuring-generated-code-is-in-code-block-format"></a>
