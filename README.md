# PromptMaster: Improve-Code-Prompts-for-ChatGPT

This is a practical guide on how to optimize  ChatGPT prompts for programming. Here, I aimed to provide tips and techniques to help developers optimize their chatgpt prompts to avoid common problems and improve their code generation experience. This guide is particulary for those using chat.openai.com subscription, allowing them to optimize their 25 message per 3 hours for gpt4. 

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
  - [3.16. Sharing long code or multiple files and asking it to keep track and note](#316-sharing-long-code-or-multiple-files-and-asking-chatgpt-to-keep-track-and-note)
- [Using ChatGPT with popular development tools](#using-chatgpt-with-popular-development-tools)  
  - VSCode
  - Jupyter notebook
  - Sublime text
  - intellij IDEA
- [Conclusion: ](#conclusion)
---

# 1. Introduction

Welcome to the **PromptMaster** repository! The purpose of this repo is to provide developers with practical guidance on optimizing ChatGPT prompts for programming tasks. We aim to share tips, techniques, and best practices to help you avoid common pitfalls and improve your code generation experience with ChatGPT. This repository will also cover using ChatGPT with popular development tools and staying up-to-date with the AI model. We encourage collaboration and contributions from the developer community to make this resource as comprehensive and useful as possible.

---

# 2. Best practices for using ChatGPT in code generation

## 2.1. Best practices for using ChatGPT in code generation
To get the best results from ChatGPT, it's essential to format your prompts correctly. Ensure that your prompts are clear, concise, and specific. You can also use formatting techniques like putting instructions in a separate line or using bullet points to improve clarity.

## 2.2. Leveraging the model's capabilities
ChatGPT is a powerful AI model with a vast knowledge base. Make sure you leverage its capabilities to your advantage. You can provide context or ask the model to generate code for a specific programming language, library, or framework. Additionally, you can ask the model to think step-by-step or generate pseudocode before generating the actual code.

## 2.3. Avoiding pitfalls and biases
Be aware that ChatGPT, like all AI models, is not perfect and might generate code with potential pitfalls or biases. To avoid these issues, you can:

- Be explicit about your requirements in the prompt
- Request multiple code samples and compare them to find the best solution 
- Make use of the temperature and max_tokens settings to control the randomness and length of the generated code 
- Remember to review the generated code for any potential issues or biases before using it in your project 

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
ChatGPT, your answer got truncated. Please continue the previously generated code without repeating any part of it.
The last part of the previous code snippet was:

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
ChatGPT, I need help with a problem using the <library/framework> version <version_number>, which is a <brief description of the library/framework>.
Here is a code snippet or documentation that demonstrates its usage:

<Insert code snippet or documentation link here>

Please provide a solution to the following problem, taking into account the updated version and any changes in the library/framework:

<Insert problem description here>
 ```
By providing context and relevant information, you can increase the chances of ChatGPT generating a useful solution that considers the updated library or framework.

**Example Prompt:**

```markdown
ChatGPT, I am working on a project that requires the use of the Dask library in Python. 
Dask is a library for parallel and distributed computing that allows processing of large datasets,
and provides support for computations on multi-dimensional arrays, data frames, and machine learning tasks. 
I need to perform parallel computation on large datasets efficiently. 
Specifically, I need to use Dask's DataFrame API to perform a groupby operation followed by aggregation. 

Here are snippets of the latest documentation and resources:

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
ChatGPT, I need a Python script that <describes the task>. 
Please ensure that the code is robust and implements defensive programming techniques, such as input validation, error handling,
and appropriate exception handling with print statements to output any errors that occur. 

The script should:

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
ChatGPT, I need a Python script that takes user input for data, processes it using a custom 'data_processing_function', and prints the result.
Please ensure that the code is robust and implements defensive programming techniques, 
such as input validation, error handling, and appropriate exception handling with print statements to output any errors that occur.
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
ChatGPT, I am working on a project that involves creating a Telegram bot to track ERC20 tokens.
I have already set up the required libraries (python-telegram-bot), created a bot on Telegram, and obtained an API token. 
My project's structure looks like this:

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
ChatGPT, I am working on a project that involves <project description>. 
I have already imported all the required libraries and dependencies in my project. 
Please help me with the following task, but do not include any import statements in the generated code:

<Insert task description here>
 ```

## 3.8. Writing only suggested changes in code
<a name="8-writing-only-suggested-changes-in-code"></a>

**Problem:** When asking ChatGPT for help with your code, sometimes you may only want to receive suggested changes or improvements for specific parts of your code, rather than having the entire code rewritten. To achieve this, you can:

-Specify the exact parts of the code that need improvement or modification.
-Ask ChatGPT to provide a high-level description of the changes instead of rewriting the entire code.

**Perfect Prompt:**

```markdown
ChatGPT, I have a piece of code that I think can be improved or modified in some way. 
I would like you to provide suggestions for changes or improvements to only the following specific part(s) of the code:

<Insert the specific part(s) of your code here>

Please provide a high-level description of the changes you suggest, without rewriting the whole code from the beginning. 
```

## 3.9. Redacting similar parts of code while keeping key headers and functions
<a name="9-redacting-similar-parts-of-code-while-keeping-key-headers-and-functions"></a>

**Problem:** When asking ChatGPT for help with your code, you may want the generated code to include only the edited or improved sections while keeping the original headers and functions intact. Additionally, you might want ChatGPT to show the placement of the edited sections in your code (after which line and before which line). To achieve this, you can provide clear instructions to ChatGPT about the specific sections that need editing and the desired placement of those edits.

**Perfect Prompt:**

```markdown
ChatGPT, I have a piece of code that I think can be improved or modified in some way. 
I would like you to provide suggestions for changes or improvements to only the following specific part(s) of the code:

<Insert the specific part(s) of your code here>

Please generate only the edited sections of the code while keeping the original headers and functions intact. 
Also, indicate the placement of the edited sections by specifying after which line and before which line the changes should be inserted in the existing code.
```

**Example (before):**
```markdown
def load_data(file_path):
# Load data from a file
pass

def process_data(data):
# Process the data
pass

def save_data(data, file_path):
# Save the processed data to a file
pass
```

***Using the perfect prompt:***

```markdown
ChatGPT, I have a piece of code that I think can be improved or modified in some way. 
I would like you to provide suggestions for changes or improvements to only the following specific part(s) of the code:

def process_data(data):
# Process the data
pass

Please generate only the edited sections of the code while keeping the original headers and functions intact. 
Also, indicate the placement of the edited sections by specifying after which line and before which line the changes should be inserted in the existing code.
```
***Generated code (After):***

```markdown
Edited section:
Replace the pass statement in the process_data function with the following lines
Place after line: 5
Place before line: 6
data = data.upper()
result = data.strip()
```

By using the perfect prompt, ChatGPT generates only the edited sections of the code and provides clear instructions on where to place the changes within the existing code.

## 3.10. Adding comments in code to refer to specific parts
<a name="10-adding-comments-in-code-to-refer-to-specific-parts"></a>

**Problem:** When working with long and complex code, it can be difficult to quickly locate and refer to specific sections. Adding comments and dividing the code into sections can help improve navigation and make it easier to refer to certain parts when asking ChatGPT for assistance.

-Use comments to divide your code into sections, labeling each part with a descriptive identifier (e.g., #Part 1, #Part 2, etc.)
-When asking ChatGPT for help, you can directly refer to the specific part by its label, making it easier for both you and ChatGPT to focus on the relevant section.

**Perfect Prompt:**

```markdown
ChatGPT, I have a piece of code that is divided into sections using comments. Here is a brief overview of the sections:

#Part 1: <Description of Part 1>
#Part 2: <Description of Part 2>
...
#Part N: <Description of Part N>
I would like you to provide suggestions or assistance for the following part(s) of the code:

<Specify which part(s) you want ChatGPT to focus on>

Please provide your suggestions or assistance with reference to the specified part(s) without rewriting the whole code from the beginning.
```

## 3.11. Prompting ChatGPT to acclimate to updated libraries and documentation
<a name="11-prompting-chatgpt-to-acclimate-to-updated-libraries-and-documentation"></a>

**Problem:** ChatGPT's knowledge is limited to information up to September 2021, which means it may not be aware of updates or changes to libraries that have occurred since then. When seeking help with a new library or an updated version, it's important to inform ChatGPT of the situation and provide relevant code and documentation snippets.

-Clearly state that you are using a library or a specific version that has been updated beyond ChatGPT's knowledge cutoff. 
-Share your code and include pertinent documentation snippets to updated resources to help ChatGPT understand the context and provide more accurate assistance.

**Perfect Prompt:**

```markdown
ChatGPT, I am working with a library (or a specific version of a library) that has been updated since your knowledge cutoff in September 2021. 
I understand that you may not be aware of the changes, so I will provide you with the relevant code and some documentation snippets to help you assist me.

Here's my code:

<Your code here>
Here are the documentation snippets related to the library or the specific version I am using:

<Documentation snippet>
Considering the provided code and documentation, could you please help me with the following issue(s) or question(s):

<Specify your issue(s) or question(s)>
```

## 3.12. Handling custom functions and methods
<a name="12-handling-custom-functions-and-methods"></a>

**Problem:** ChatGPT may not be familiar with user-defined functions or methods, making it difficult to understand the context when discussing code.

-Provide details about the custom functions or methods, such as their purpose, inputs, outputs, and any relevant implementation details. This will help ChatGPT provide better assistance and recommendations.

**Perfect Prompt:**

```markdown
I have a custom function called function_name(arguments), which performs a specific task. 
The function takes these arguments: arg1 (type), arg2 (type), and so on. It returns the result of the operation as a specific type. 
Can you suggest improvements or potential issues with this function?
```

## 3.13. Writing efficient and concise code
<a name="13-writing-efficient-and-concise-code"></a>

**Problem**  Users may want help optimizing their code or making it more concise.

-Ask ChatGPT for suggestions on how to improve the efficiency or conciseness of your code, and provide any specific concerns or constraints you have.

**Perfect Prompt:**

```markdown
I have a piece of code that performs a specific task, but I'd like to make it more efficient or concise. 
Here's my current implementation:

def function_name(arguments):
    < Your code here >
Can you suggest an alternative way to implement this functionality?
```

## 3.14. Providing snippet of database or dataset structure
<a name="14-providing-snippet-of-database-or-dataset-structure"></a>

**Problem:** ChatGPT may not have access to your specific database or dataset structure, which can hinder its ability to provide relevant guidance.

-Share a snippet of your database or dataset structure, including information on tables, columns, data types, and relationships between tables or data points, to help ChatGPT better understand your query and provide appropriate guidance. 
-Use the generic prompt example as a starting point and tailor it to your specific situation.

**Perfect Prompt:** 

```markdown
I'm working with a database or dataset that has the following structure: 
(provide information on tables, columns, data types, and relationships). 
Can you help me with a query or data manipulation task related to this structure?

heres the first 10 rows in my dataset_1.csv 
... paste here
```
**Example:**

```markdown
I'm working with a database that has the following structure:

Table orders: order_id (integer), customer_id (integer), order_date (date), total_amount (float)
Table customers: customer_id (integer), customer_name (varchar), email (varchar)
The tables are related by the customer_id field.

Sample data (first 10 lines):
orders:
1, 1, 2023-01-01, 100.00
2, 2, 2023-01-02, 150.00
3, 3, 2023-01-02, 200.00

customers:
1, Alice, alice@example.com
2, Bob, bob@example.com
3, Carol, carol@example.com

I want to retrieve a list of all orders with the customer's name and email. 
Can you help me write a SQL query for this task?
```

## 3.15. Encouraging diverse solutions
<a name="15-encouraging-diverse-solutions"></a>

**Problem:** sometimes chatgpt provides code answer that wont work and gets stuck and fixated on it. in this case ask chatgpt for an alternative solution or list of approaches to solve the  problem, allowing you to choose the best option based on your specific needs and constraints.

**Perfect Prompt:** 

```markdown
I need help solving a specific problem in my code, but I'm looking for multiple alternative solutions or approaches. 
Can you provide a list of different ways to solve this problem, considering my specific needs and constraints?
Here's my code:

<Your code here>
```

## 3.16. Sharing long code or multiple files and asking ChatGPT to keep track and note
<a name="16-sharing-long-code-or-multiple-files-and-asking-chatgpt-to-keep-track-and-note"></a>

**Problem:** Users may need assistance with long code snippets or multiple files, which can be challenging to manage in a conversational format.

-Inform chatgpt that you will share multiple files or long files that will be sent across of more than 1 message. 
-Ask chatgpt to understand, keep note, and track all of the messages and state that you will inform it when you finish sharing and then ask your questions. 
-Ask it to respond back that it understands. share the code or files with ChatGPT and provide chatgpt with as many details on which files you are sharing and which parts. 

**Perfect Prompt:** 

```markdown
I will be sharing multiple files or long files that span across more than one message. 
Please understand, keep note of, and track all the messages. 
I will inform you when I finish sharing the files, and then I will ask my questions. 
Please respond back that you understand.

<Share the code or files with ChatGPT sequentially or as needed, providing as many details as possible about which files you are sharing and which parts they pertain to.>
```
---
 # 4. Using ChatGPT with popular development tools 
 <a name="using-chatgpt-with-popular-development-tools"></a>
 
| IDE / Tool                                                                            | Extension / Plugin Name                                                                                             | Description                                                                                                                                                                  |
|---------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <img src="https://camo.githubusercontent.com/3913c59c7057f9c9a7f79d63c9753930e69790c8f90fbb375a78686e96165d29/68747470733a2f2f6564656e742e6769746875622e696f2f537570657254696e7949636f6e732f696d616765732f7376672f76697375616c73747564696f636f64652e737667" width="30" height="30"> Visual Studio Code | [ChatGPT Extension for VSCode](https://github.com/mpociot/chatgpt-vscode)                             | Allows you to use the unofficial ChatGPT API to generate natural language responses from OpenAI's ChatGPT within the editor.                                                 |
| <img src="https://camo.githubusercontent.com/3913c59c7057f9c9a7f79d63c9753930e69790c8f90fbb375a78686e96165d29/68747470733a2f2f6564656e742e6769746875622e696f2f537570657254696e7949636f6e732f696d616765732f7376672f76697375616c73747564696f636f64652e737667" width="30" height="30"> Visual Studio Code | [AI Genie](https://marketplace.visualstudio.com/items?itemName=genieai.chatgpt-vscode)                                                             | Prompt OpenAI's GPT-4, GPT-3.5, GPT-3, and Codex models within Visual Studio Code.                                                                                            |
| <img src="https://camo.githubusercontent.com/3913c59c7057f9c9a7f79d63c9753930e69790c8f90fbb375a78686e96165d29/68747470733a2f2f6564656e742e6769746875622e696f2f537570657254696e7949636f6e732f696d616765732f7376672f76697375616c73747564696f636f64652e737667" width="30" height="30"> Visual Studio Code  | [TabNine](https://www.tabnine.com/)                                                                                | Although not ChatGPT, TabNine is a powerful AI-powered code completion tool.                                                                                                 |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/jupyter/jupyter-original.svg" width="30" height="30"> Jupyter Notebook   | [Chat-GPT Jupyter Extension](https://github.com/jflam/chat-gpt-jupyter-extension)                                 | Integrates ChatGPT into Jupyter Notebook for code generation and suggestions.                                                                                                |
| <img src="https://raw.githubusercontent.com/github/explore/80688e429a7d4ef2fca1e82350fe8e3517d3494d/topics/sublime-text/sublime-text.png" width="30" height="30"> Sublime Text | [Sublime Text ChatGPT](https://github.com/eusonlito/Sublime-Text-ChatGPT)                                          | A plugin that connects Sublime Text to ChatGPT for code generation and assistance.                                                                                           |
| <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/intellij/intellij-plain.svg" width="30" height="30"> IntelliJ IDEA   | [ChatGPT IntelliJ Plugin](https://plugins.jetbrains.com/plugin/20603-chatgpt)                                      | Integrates ChatGPT into IntelliJ IDEA for code generation, autocompletion, and assistance.                                                                                   |

---

# 5. Conclusion: 
<a name="conclusion"></a>


I hope this guide has been helpful in improving your experience with ChatGPT for code generation. 
As ChatGPT evolves, so will the best practices for using it. 
If you have any suggestions, contribution you want to add or feedback, feel free to send a pull request to this guide's GitHub repository. Happy coding and prompting! <3

---
