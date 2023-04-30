# PromptMaster: Improve-Code-Prompts-for-ChatGPT

This is a practical guide on how to optimize  ChatGPT prompts for programming. Here, I aimed to provide tips and techniques to help developers optimize their chatgpt prompts to avoid common problems and improve their code generation experience. This guide is particulary for those using chat.openai.com, allowing them to optimize their 25 message per 3 hours for gpt4. 

---

## 📚 Table of Contents
- [Introduction](#introduction)
- [Best practices for using ChatGPT in code generation](#best-practices-for-using-chatgpt-in-code-generation)
  - [2.1. Best practices for using ChatGPT in code generation](#21-best-practices-for-using-chatgpt-in-code-generation)
  - [2.2. Leveraging the model's capabilities](#22-leveraging-the-models-capabilities)
  - [2.3. Avoiding pitfalls and biases](#23-avoiding-pitfalls-and-biases)
- [Prompt-Master: Master Code Prompts for ChatGPT](#prompt-master-master-code-prompts-for-chatgpt)
  - [3.1. Dealing with truncated code](#31-dealing-with-truncated-code)
  - [3.2. Ensuring generated code is in code block format](#32-ensuring-generated-code-is-in-code-block-format)
  - [3.3. Handling unfamiliar libraries and frameworks](#33-handling-unfamiliar-libraries-and-frameworks)
  - [3.4. Providing specific constraints and requirements](#34-providing-specific-constraints-and-requirements)
  - [3.5. Defensive programming prompt and error handling](#35-defensive-programming-prompt-and-error-handling)
  - [3.6. Providing project dictionary and prerequisite information](#36-providing-project-dictionary-and-prerequisite-information)
  - [3.7. Omitting imports in generated code](#37-omitting-imports-in-generated-code)
  - [3.8. Writing only suggested changes in code](#38-writing-only-suggested-changes-in-code)
  - [3.9. Redacting similar parts of code while keeping key headers and functions](#39-redacting-similar-parts-of-code-while-keeping-key-headers-and-functions)
  - [3.10. Adding comments in code to refer to specific parts](#310-adding-comments-in-code-to-refer-to-specific-parts)
  - [3.11. Prompting ChatGPT to acclimate to updated libraries and documentation](#311-prompting-chatgpt-to-acclimate-to-updated-libraries-and-documentation)
  - [3.12. Handling custom functions and methods](#312-handling-custom-functions-and-methods)
  - [3.13. Writing efficient and concise code](#313-writing-efficient-and-concise-code)
  - [3.14. Providing snippet of database or dataset structure](#314-providing-snippet-of-database-or-dataset-structure)
  - [3.15. Encouraging diverse solutions](#315-encouraging-diverse-solutions)
  - [3.16. Sharing long code or multiple files and asking it to keep track and note](#316-sharing-long-code-or-multiple-files-and-asking-it-to-keep-track-and-note)
- [Using ChatGPT with popular development tools](#using-chatgpt-with-popular-development-tools)  
  - [4.1. IDEs](#41-ides)
       - Visual Studio Code 
       - PyCharm  
       - Sublime Text 
       - Atom 
       - IntelliJ IDEA  
       - Eclipse  
  - [4.2. Version control systems](#42-version-control-systems)
       - Git  
       - Mercurial  
       - Subversion 
  - [4.3. Continuous Integration and Deployment (CI/CD) systems](#43-continuous-integration-and-deployment-ci/cd-systems)
       - Jenkins  
       - GitLab CI/CD 
       - GitHub Actions 
       - CircleCI 
       - Travis CI  
- [Staying up-to-date with ChatGPT](#staying-up-to-date-with-chatgpt)
  - [5.1. Monitoring updates and new releases](#51-monitoring-updates-and-new-releases)
  - [5.2. Adjusting to changes in the AI model](#52-adjusting-to-changes-in-the-ai-model)
- [Conclusion: feel free to send pull requests](#conclusion-feel-free-to-send-pull-requests)
---

# 1. Introduction

Welcome to the **PromptMaster** repository! The purpose of this repo is to provide developers with practical guidance on optimizing ChatGPT prompts for programming tasks. We aim to share tips, techniques, and best practices to help you avoid common pitfalls and improve your code generation experience with ChatGPT. This repository will also cover using ChatGPT with popular development tools and staying up-to-date with the AI model. We encourage collaboration and contributions from the developer community to make this resource as comprehensive and useful as possible.

---

# 2. Best practices for using ChatGPT in code generation

## 2.1. Best practices for using ChatGPT in code generation
Properly formatting prompts
To get the best results from ChatGPT, it's essential to format your prompts correctly. Ensure that your prompts are clear, concise, and specific. You can also use formatting techniques like putting instructions in a separate line or using bullet points to improve clarity.

## 2.2. Leveraging the model's capabilities
ChatGPT is a powerful AI model with a vast knowledge base. Make sure you leverage its capabilities to your advantage. You can provide context or ask the model to generate code for a specific programming language, library, or framework. Additionally, you can ask the model to think step-by-step or generate pseudocode before generating the actual code.

## 2.3. Avoiding pitfalls and biases
Be aware that ChatGPT, like all AI models, is not perfect and might generate code with potential pitfalls or biases. To avoid these issues, you can:

-Be explicit about your requirements in the prompt
-Request multiple code samples and compare them to find the best solution
-Make use of the temperature and max_tokens settings to control the randomness and length of the generated code
-Remember to review the generated code for any potential issues or biases before using it in your project.

---

# 3. Prompt-Master: Master Code Prompts for ChatGPT

## 3.1. Dealing with Truncated Code
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

## 3.2. Ensuring generated code is in code block format
<a name="2-ensuring-generated-code-is-in-code-block-format"></a>
**Problem:** Sometimes, ChatGPT responds with code as plain text instead of within a code block. This might lead to indentation errors and syntax issues when the code is copied and pasted into a development environment. To avoid this, you can use the following prompt to explicitly request code within a code block.

**Perfect Prompt:**

```markdown
ChatGPT, please provide a solution to the problem in a properly formatted Python code block. The problem is:

<Insert problem description here>
```
By explicitly requesting a code block, you are more likely to receive the generated code in the correct format, reducing the chances of encountering indentation or syntax errors when copying the code.

## 3.3. Handling unfamiliar libraries and frameworks
<a name="3-handling-unfamiliar-libraries-and-frameworks"></a>

**Problem:** Since ChatGPT has a knowledge cutoff date of 2021, it may not have access to updated libraries or frameworks or changes made in them. Therefore, it might encounter unfamiliar libraries and frameworks.

**Proposed Solution:** To better help ChatGPT understand and adapt to unfamiliar libraries and frameworks, you can:

-Provide the name of the library or framework.
-Describe the purpose of the library or framework.
-Give an example of how the library or framework is used.
-Mention any specific functions or methods you need to use.
-Include any latest relevant documentation or resources.

**Perfect Prompt:**

```markdown
ChatGPT, I need help with a problem using the <library/framework> version <version_number>, which is a <brief description of the library/framework>. Here is a code snippet or documentation that demonstrates its usage:

<Insert code snippet or documentation link here>

Please provide a solution to the following problem, taking into account the updated version and any changes in the library/framework:

<Insert problem description here>
 ```
By providing context and relevant information, you can increase the chances of ChatGPT generating a useful solution that considers the updated library or framework.

**Example Prompt:**

```markdown
ChatGPT, I am working on a project that requires the use of the Dask library in Python. Dask is a library for parallel and distributed computing that allows processing of large datasets and provides support for computations on multi-dimensional arrays, data frames, and machine learning tasks. I need to perform parallel computation on large datasets efficiently. Specifically, I need to use Dask's DataFrame API to perform a groupby operation followed by aggregation. Here are snippets of the latest documentation and resources:

- Dask documentation: https://docs.dask.org/en/latest/ <provide the snippets that has been updated and chatgpt might not be familair with>

Please provide a Python script that uses the Dask library to achieve the following tasks:

1. Load a large dataset with millions of rows and columns.
2. Perform a groupby operation based on a specific column.
3. Aggregate the results using a sum operation.
4. Output the resulting dataset.
```

## 3.4. Providing specific constraints and requirements
<a name="4-providing-specific-constraints-and-requirements"></a>

**Problem:** To optimize the output of ChatGPT, it can be helpful to provide specific constraints or requirements for the generated code. For example, if speed or memory usage is a concern, you can include this information in your prompt to help ChatGPT optimize its output.

To optimize the output of ChatGPT, provide specific constraints or requirements for the generated code. This could include information about the programming language, data types, speed or memory usage, sorting order, or any other relevant constraints.

**Perfect Prompt:**
```markdown
ChatGPT, I need help generating code that meets the following constraints and requirements:
- <Insert constraint or requirement>
- <Insert constraint or requirement>
- <Insert constraint or requirement>
- <Insert constraint or requirement>
- <Insert constraint or requirement>
Can you help me generate code that meets these requirements?
 ```

**Example Prompt:**
```markdown
"ChatGPT, I need to generate a C++ program that sorts a large array of integers, but the program needs to meet the following constraints:
- The program needs to be optimized for speed and should be able to handle large arrays efficiently.
- The program should be memory-efficient and should use a sorting algorithm that minimizes memory usage.
- The program should be able to handle both ascending and descending sorts and should allow the user to specify the sorting order.
- The program should be able to handle arrays with duplicate values and should sort them in a stable manner.
- The program should be easy to read and maintain, with clear variable names and comments.
Can you help me write a C++ program that meets these requirements?"
```

## 3.5. Defensive programming prompt and error handling
<a name="5-defensive-programming-prompt-and-error-handling"></a>


**Problem:** ChatGPT is a valuable sidekick but not the perfect developer. When asking ChatGPT to generate code or help with your code, it's essential to ensure there's ample error handling and defensive programming, making it easier to see and address any errors. To generate code that includes defensive programming techniques and error handling, you can provide context and information about the potential errors or edge cases that need to be handled in your prompt. To make it easier to identify errors during later debugging, you can ask ChatGPT to add print statements that output any errors that occur, along with defensive programming constructs like input validation, try-except blocks, and logging.

**Perfect Prompt:**
```markdown
ChatGPT, I need a Python script that <describes the task>. Please ensure that the code is robust and implements defensive programming techniques, such as input validation, error handling, and appropriate exception handling with print statements to output any errors that occur. The script should:

<list the specific tasks or requirements of the script>
```

**Example Before and After Using the Perfect Prompt:**

***Before:***

```markdown
def process_data(data):
    result = data_processing_function(data)
    return result

data = input("Enter the data: ")
result = process_data(data)
print("The processed data is:", result)
```

***After using the perfect prompt:***

```markdown
ChatGPT, I need a Python script that takes user input for data, processes it using a custom 'data_processing_function', and prints the result. Please ensure that the code is robust and implements defensive programming techniques, such as input validation, error handling, and appropriate exception handling with print statements to output any errors that occur.
```

***Generated code:***

```markdown
def validate_input(data):
    # Implement validation logic according to your requirements
    return True

def process_data(data):
    try:
        if not validate_input(data):
            raise ValueError("Invalid input data")

        result = data_processing_function(data)
        return result
    except ValueError as ve:
        print("Error: Invalid input data:", ve)
        return None
    except Exception as e:
        print("Error:", e)
        return None

data = input("Enter the data: ")
result = process_data(data)

if result is not None:
    print("The processed data is:", result)
else:
    print("An error occurred during data processing.")
```

By using the perfect prompt, ChatGPT generates code that includes error handling and defensive programming, making it easier to debug and maintain.

## 3.6. Providing project dictionary and prerequisite information
<a name="6-providing-project-dictionary-and-prerequisite-information"></a>

**Probem:** When working with ChatGPT on a project, it's essential to let it know that you have already installed the requirements and have the relevant APIs set up. This helps ChatGPT avoid explaining in its response what you have already done and tailor the output to your specific needs. To optimize the output of ChatGPT, you can provide a project dictionary and relevant APIs in your prompt. This can help ChatGPT understand the context and purpose of the code you need generated.

**Perfect Prompt:**

```markdown
ChatGPT, I am working on a project that involves <project description>. 
 I have already set up the required libraries, APIs, and dependencies. My project's structure looks like this:

<Describe your project structure here>

Please help me with the following task, taking into consideration the existing setup:

<Insert task description here>
```
**Example Before and After Using the Perfect Prompt:**

***Before:***

```markdown
ChatGPT, I want to create a Telegram bot to track ERC20 tokens.
```
***ChatGPT Response (Before):***

To create a Telegram bot to track ERC20 tokens, you need to:

Set up a new bot on Telegram by talking to the BotFather.
Get your bot API token.
Install the python-telegram-bot library.
Configure the bot to communicate with the Ethereum blockchain....

***Using the perfect prompt:***

```markdown
ChatGPT, I am working on a project that involves creating a Telegram bot to track ERC20 tokens. I have already set up the required libraries (python-telegram-bot), created a bot on Telegram, and obtained an API token. My project's structure looks like this:

- main.py <share code>
- config.py (API token stored here)
- erc20_tracker.py <share code>

Please help me with the following task, taking into consideration the existing setup:

Implement the functionality in the erc20_tracker.py file to track ERC20 tokens.
```
***Generated code (After):***

```markdown
import requests
from config import TELEGRAM_API_TOKEN

def get_erc20_balance(address, contract_address):
    # Implement the function to get the balance of ERC20 tokens for a given address

def track_erc20_tokens(update, context):
    # Implement the function to track ERC20 tokens using the Telegram bot

if __name__ == "__main__":
    from telegram.ext import Updater, CommandHandler

    updater = Updater(token=TELEGRAM_API_TOKEN, use_context=True)
    dispatcher = updater.dispatcher

    dispatcher.add_handler(CommandHandler("track", track_erc20_tokens))
    
    updater.start_polling()
    updater.idle()
```
By providing the project dictionary and prerequisite information, ChatGPT generates code tailored to your specific needs, taking into account the existing setup.

## 3.7. Omitting imports in generated code
<a name="7-omitting-imports-in-generated-code"></a>

**Problem:** Sometimes, when generating code, ChatGPT may include redundant or unnecessary imports that you already have in your project, leading to clutter and repetition in the generated code. To prevent this, you can instruct ChatGPT to omit import statements in the generated code and focus on the specific functionality you need.

**Perfect Prompt:**

```markdown
ChatGPT, I am working on a project that involves <project description>. I have already imported all the required libraries and dependencies in my project. Please help me with the following task, but do not include any import statements in the generated code:

<Insert task description here>
 ```

## 3.8. Writing only suggested changes in code
<a name="8-writing-only-suggested-changes-in-code"></a>

**Problem:** When asking ChatGPT for help with your code, sometimes you may only want to receive suggested changes or improvements for specific parts of your code, rather than having the entire code rewritten. To achieve this, you can:

-Specify the exact parts of the code that need improvement or modification.
-Ask ChatGPT to provide a high-level description of the changes instead of rewriting the entire code.

**Perfect Prompt:**

```markdown
ChatGPT, I have a piece of code that I think can be improved or modified in some way. I would like you to provide suggestions for changes or improvements to only the following specific part(s) of the code:

<Insert the specific part(s) of your code here>

Please provide a high-level description of the changes you suggest, without rewriting the whole code from the beginning. 
```

## 3.9. Redacting similar parts of code while keeping key headers and functions
<a name="9-redacting-similar-parts-of-code-while-keeping-key-headers-and-functions"></a>


## 3.10. Adding comments in code to refer to specific parts
<a name="10-adding-comments-in-code-to-refer-to-specific-parts"></a>

## 3.11. Prompting ChatGPT to acclimate to updated libraries and documentation
<a name="11-prompting-chatgpt-to-acclimate-to-updated-libraries-and-documentation"></a>

## 3.12. Handling custom functions and methods
<a name="12-handling-custom-functions-and-methods"></a>

## 3.13. Writing efficient and concise code
<a name="13-writing-efficient-and-concise-code"></a>
