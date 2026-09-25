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

Coding standards are an essential part of software engineering and programming as a whole. They are a set of rules, best practices, and programming conventions that developers follow to write standardized, readable code. Consider the following key components of coding standards:

- **Formatting and Layout:** These rules govern indentation, whitespace usage, line length, and brace placement. While every programming language may have its own specifics, a common standard looks like this:

    ```js
    function calculateTotal(price, tax) {
      const total = price + tax;

      if (total > 100) {
        return total * 0.9;
      }

      return total;
    }
    ```

    This formatting ensures that code looks uniform across a team, enabling developers to easily maintain and collaborate on the same codebase.

- **Naming Conventions:** Standardized ways to name variables, functions, and classes with meaningful names (e.g., camelCase, PascalCase, or UPPERCASE). Following consistent conventions provides instant context, as the name itself suggests its purpose, use case, and structure.

- **Commenting and Documentation:** The purpose of this standard is to describe the intent behind a section of code. Instead of explaining what every single line does, the programmer should explain *why* the code was implemented in a specific way. For example:

    ```ts
    /*
    Retry connection up to 3 times because the third-party API
    experiences frequent network drops during peak hours
    */
    if (retry_count < 3) {
      attempt_reconnection();
    }
    ```

    This serves as a note to both the original author and future collaborators regarding what the code does and why it is needed, helping avoid misunderstandings.

- **Error Handling:** Using consistent methods to catch exceptions, errors, and runtime crashes. This is especially useful for troubleshooting, as it provides developers with clearer context than standard compiler errors. A good error handling method uses `try-catch` statements to handle and log errors gracefully instead of allowing the application to crash:

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

- **Code Complexity Limits:** This practice establishes strict guidelines on how large a function or method can be. It prevents "Spaghetti Code" and "God Objects"—where a single section of code handles too many responsibilities—thereby keeping the codebase clean and adhering to the single-responsibility principle. Forcing developers to break code into smaller chunks makes components easier to reuse and unit test.

## My Experience with Coding Standards

Out of the rules mentioned above, I previously complied only with those I perceived as the bare minimum. I regularly followed basic formatting rules by using proper spacing and indentation. I also followed naming conventions, naming my variables based on context and purpose. Perhaps the best standard I adopted was limiting complexity; I formed a good habit of dividing my code into distinct functions that handle single, reusable tasks. This sped up my development time, as I could easily navigate my codebase and locate potential bugs.

That being said, I was also guilty of neglecting other important standards. For example, I rarely commented on my code because I found it time-consuming and assumed my formatting and variable names made the code self-explanatory. I also ignored explicit error handling, relying heavily on compiler output and linters to catch bugs during development. However, as I began collaborating with others and taking on larger projects, I realized that comments and error handling are indispensable: comments remind my team and me why code exists, while error handling catches edge cases and logs critical debug information.

## My Current Practice with Coding Standards

My goal for the near future is to utilize these coding standards to their fullest extent to become a more well-rounded developer. I have already started documenting complex logic with comments, allowing my future self and teammates to understand the codebase faster. I have also adopted tools such as ESLint for TypeScript to catch formatting inconsistencies, ensuring my code remains uniform. Finally, I have begun adding explicit `if` statements to handle edge cases and implementing loggers to track execution flow. Maintaining these practices will make me a much more effective developer when building complex systems and collaborating with others.