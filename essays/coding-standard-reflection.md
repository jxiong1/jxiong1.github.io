---
layout: essay
type: essay
title: "Reflecting on Coding Standards"
# All dates must be YYYY-MM-DD format!
date: 2026-09-23
published: true
labels:
  - Software Engineer
  - TypeScript
  - Software developement
---

## Importance of Coding Standards

Coding standards are an essential part of software engineering and programming as a whole. They are a set of rules, best practices, and programming conventions that programmers follow to write standardized, readable code. Consider the following key components of coding standards:

- **Formatting and Layout:** These are rules for indentation, whitespace usage, line length, and brace placement. Every language may have its own rules, but they generally follow a format like this: 

```js
function calculateTotal(price, tax) {
  const total = price + tax;

  if (total > 100) {
    return total * 0.9;
  }

  return total;
}
```

This allows code to look uniform across all programmers, enabling others to easily maintain and collaborate on the same codebase.

- **Naming Conventions:** Standardized ways to name variables, functions, and classes with meaningful names (e.g., camelCase, PascalCase, or UPPERCASE). Doing so provides instant context, as the name can suggest its purpose, use cases, and distinction between language constructs.

- **Commenting and Documentation:** The purpose of this standard is to describe intent over a section of code. Instead of explaining what each line of code does, the programmer should explain why the section of code was implemented. For example:

```ts
/*
Retry connection up to 3 times because the third-party API
experiences frequent network drops during peak hours
*/
if (retry_count < 3){
  attempt_reconnection()
}
```

This serves as a note to the programmer and their collaborators on both what this code does and why it's needed, helping avoid misunderstandings.

- **Error Handling:** Using consistent methods to catch exceptions, errors, and crashes. This is especially useful for troubleshooting, as it gives developers a better idea of what caused the error than the default compiler output. An example of a good error handling method is using try-catch statements to catch and log errors instead of letting the application crash:

```ts
try {
  data = loadFile('config.json');
} catch (error) {
  if (error instanceof Error && error.name === 'FileNotFoundError') {
    logger.error(`Configuration file missing: ${error.message}`);
  } else {
    logger.error(`Failed to load configuration: ${error}`);
  }
  data = loadDefaultConfig(); // Falls back to safe settings
}
```

- **Code Complexity Limits:** This practice requires developers to set strict rules on how large a method or function can be. It essentially prevents "Spaghetti Code" and "God Objects"—the oversaturation of tasks assigned to a single section of code—thereby preventing bloated code and upholding the single-responsibility principle. By forcing developers to break their code into smaller chunks, it allows components to be reused and easily tested for bugs.

## My Experience with Coding Standards

Out of the many rules mentioned, I complied with those that I perceived as the bare minimum a developer should follow. I often followed appropriate formatting rules by properly spacing my code and following indentation guidelines. I also followed proper naming conventions and named my variables based on their context and purpose. Perhaps the most important standard I followed was limiting complexity; I have a good habit of dividing my code into distinct functions that complete a single task and are easily reusable. This often speeds up the time I spend working on a project, as I can easily navigate my code and find potential errors or bugs.

That being said, I was also guilty of ignoring some of the coding standards listed. For example, I rarely added comments to my code because I felt it was time-consuming and assumed I could understand it based on the standards I already followed, such as naming conventions and proper formatting. I also ignored error handling, relying heavily on compiler output and linters for debugging in an effort to make my code flawless. However, as I started collaborating with others and taking on bigger projects, I realized it is absolutely necessary to add comments and error handling. Comments remind my collaborators and me why each section of code is necessary, while error handling catches numerous edge cases and logs errors for debugging.

## My Current Attempts at "Coding in Standards"

My goal in the near future is to utilize these coding standards to their fullest extent so that I can become a better developer. I have already started by commenting code that is complicated, allowing my future self and others to understand it better. I have also started using tools such as ESLint for TypeScript to catch formatting inconsistencies, ensuring my code is standardized and uniform. Finally, I have begun using "if" statements to catch potential edge cases and implementing logs as flags to trace execution flow and catch logical bugs. I hope keeping these habits up will make me a better developer when working on larger projects and collaborating with others.

<small>AI Used for Grammar Corrections</small>