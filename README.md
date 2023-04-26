# PromptMaster: Improve-Code-Prompts-for-ChatGPT

This is a practical guide on how to optimize  ChatGPT prompts for programming. Here, I aimed to provide tips and techniques to help developers optimize their chatgpt prompts to avoid common problems and improve their code generation experience. .

## Table of Contents

1.  [Dealing with truncated code](#1-dealing-with-truncated-code)
2. [Ensuring generated code is in code block format](#2-ensuring-generated-code-is-in-code-block-format)
3. [Handling unfamiliar libraries and frameworks](#3-handling-unfamiliar-libraries-and-frameworks)
4. [Providing specific constraints and requirements](#4-providing-specific-constraints-and-requirements)
5. [Defensive programming prompt and error handling](#5-defensive-programming-prompt-and-error-handling)
6. [Providing project dictionary and prerequisite information](#6-providing-project-dictionary-and-prerequisite-information)
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
**Problem:** Sometimes, ChatGPT responds with code as plain text instead of within a code block. This might lead to indentation errors and syntax issues when the code is copied and pasted into a development environment. To avoid this, you can use the following prompt to explicitly request code within a code block.

**Perfect Prompt:**

```markdown
ChatGPT, please provide a solution to the problem in a properly formatted Python code block. The problem is:

<Insert problem description here>
```
By explicitly requesting a code block, you are more likely to receive the generated code in the correct format, reducing the chances of encountering indentation or syntax errors when copying the code.

## 3. Handling unfamiliar libraries and frameworks
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

## 4. Providing specific constraints and requirements
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

## 5. Defensive programming prompt and error handling
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

## 6. Providing project dictionary and prerequisite information
<a name="6-providing-project-dictionary-and-prerequisite-information"></a>

