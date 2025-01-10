--- 
title: Introduction to GitHub Copilot
---

## Introduction to GitHub Copilot

GitHub Copilot is an AI-powered code assistant. It works in many different code editors, including VS Code and [RStudio](https://docs.posit.co/ide/user/ide/guide/tools/copilot.html), suggesting whole lines or blocks of code to help you code faster and learn as you go.

## Benefits

**Boost Productivity and Reduce Friction:**

- **Faster Coding:** Studies show developers can code up to 55% faster with Copilot, freeing up time for more complex tasks and innovation.
- **Less Context Switching:** Get relevant code suggestions in real-time, reducing the need to search for boilerplate code, documentation, or Stack Overflow answers.
- **Reduce Mental Fatigue:** Automate repetitive tasks like writing basic functions, tests, and comments, minimizing cognitive load and burnout.

**Improve Code Quality and Consistency:**

- **Fewer Bugs:** Catch potential errors and vulnerabilities with Copilot's built-in safety checks, promoting cleaner and more secure code.
- **Better Style Adherence:** Maintain consistent code style throughout your project with Copilot's understanding of your codebase's conventions.
- **Experimentation:** Explore different approaches with Copilot's diverse suggestions, leading to potentially better solutions.

**Enhance Team Collaboration and Knowledge Sharing:**

- **Shared Language:** Copilot helps onboard new team members by suggesting code familiar to experienced developers, speeding up integration.
- **Collective Learning:** Developers learn from each other's Copilot interactions, promoting knowledge sharing and best practices.
- **Focus on Collaboration:** Free up time for discussing complex problems and solutions instead of getting bogged down in basic coding tasks.

**Considerations for a small team:**

- **Cost:** While Business plans offer centralized management and security features, the Individual plan might be cost-effective for 12 developers.
- **Security:** Assess your security needs and how Copilot aligns with them. Individual plans block public code suggestions, but Business plans might add further protection.
- **Workflow Integration:** Discuss how your team will integrate Copilot into their existing workflow and ensure everyone benefits from its assistance.

## Features

- **Line and block suggestions**: GitHub Copilot suggests whole lines or blocks of code as you type.
- **Inline Commands**: Highlight certain blocks of code and ask Copilot to perform certain actions on it.

[![copilot_1_1.gif](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-1-1.gif)](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-1-1.gif)
    
- **Code refactor**: Add/edit/refactors existing code based on command

[![copilot_2.gif](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-2.gif)](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-2.gif)
    

- **Comment to code generation:** Write pseudo-code in comments and ask Copilot to generate code based off of that.
    
[![Untitled.gif](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/untitled.gif)](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/untitled.gif)
    
- **Code fix:** Proposes fixes to code
- **Test-writing**: GitHub Copilot can create units tests for your code
    

- **Code Explanation**: GitHub Copilot can take a block of code and explain what is going on.
    
[![copilot_explain.gif](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-explain.gif)](https://flowwest-bookstack-storage.s3.amazonaws.com/uploads/images/gallery/2024-05/copilot-explain.gif)
    
```jsx

**Copilot Response:**
    
This TypeScript React code is part of a larger application, specifically a function that is used to edit a monitoring location. The function is wrapped in makeDomainFunction, which is likely a higher-order function that provides some additional functionality or context.
    
The function takes an object values as an argument, which contains properties such as latitude, longitude, locationType, monitoringLocationCode, and name. These properties are destructured from the values object for easier access.
    
A cookie is retrieved from the request headers. This is likely used for user authentication or session management.
    
The function then attempts to authorize the user and make a PUT request to the server to update the monitoring location with the new values. The URL for the request is constructed using the SERVER_URL environment variable and the monitoringLocationId.
    
The response from the server is expected to be a JSON object representing the updated monitoring location. This is parsed and stored in editedMonitoringLocation.
    
The function then checks if the projects array has more than one item. If it does, it transforms the projects string into an array of WaterMonitoringProject objects, and retrieves the IDs of the new projects.
    
The function then makes a series of DELETE requests to remove the initial projects from the monitoring location, and a series of POST requests to add the new projects to the monitoring location. These requests are made in a loop using the for await...of syntax, which allows for asynchronous iteration.
    
If any errors occur during this process, they are caught and re-thrown. If the error is an instance of the Error class, the error message is thrown. Otherwise, a generic 'Unknown Error' message is thrown. This error handling ensures that any issues with the request or the data are properly communicated.
```
    
- **Code Documentation**: Copilot will generate documentation comments for selected code
- **GitHub Copilot Chat**: A more conversational way to interact with Copilot. Commands in chat include `@workspace` which allows you to ask questions about your entire workspace or `@terminal` where you can ask how to run certain terminal commands.

## How we use it?

- Have Copilot explain code blocks/functions when coming into coming into projects, reducing the time it takes before we can start developing.
- Eliminate the need for utility libraries by abstracting common programming tasks such as manipulating arrays, objects, and other types of data.
- Generating code that that follows a pattern of other code recently written. This is great for completing boilerplate code such as handling api requests, manipulating form data, adding commonly used properties for UI components.
- Finding card-to-catch syntax errors in written code streamlining parts of the debugging process, for example.
    

> [!NOTE] Prompt
> What is wrong with this SQL statement: 
>     
> `SELECT name FROM dish WHERE name = 'Prawn Salad'` 
>
> `ORDER BY name GROUP BY name HAVING count(*) = 1`


> [!INFO] Copilot Response
>  The issue with your SQL statement is the order of the clauses. The GROUP BY clause should come before the ORDER BY clause. Also, the HAVING clause is typically used with the GROUP BY clause to filter the results of the grouping. In your case, since you're grouping by name and then filtering where the count is 1, it seems unnecessary because each group will have a count of  1. Here is the corrected SQL statement:
>
>  ```
> SELECT name
> FROM dish
> WHERE name = 'Prawn Salad'
> GROUP BY name
> HAVING count(*) = 1
> ORDER BY name
> ```
> 
> However, if you're just trying to find the dish named 'Prawn Salad' and there are no duplicate names, you don't need the GROUP BY and HAVING clauses at all:
>
> ```
> SELECT name
> FROM dish
> WHERE name = 'Prawn Salad'
> ORDER BY name
> ```
    
- Generating placeholder data to test functions and UI components. [[codesandbox demo]](https://codesandbox.io/p/sandbox/winter-sun-3sv3gj?file=%2Fsrc%2FApp.js%3A24%2C19)

## Limitations

While GitHub Copilot can generate code for a wide variety of applications and use cases, it's not perfect. GitHub Copilot has difficulty coming up with more complex solutions without the help of a human developer. For example, Copilot can misinterpret the context of the prompt resulting in code suggestions that don’t align with the developer’s intentions. Other times it can make valid suggestions, but the code itself is unoptimized, inefficient or even insecure. 

GitHub Copilot is only as good as the data it's trained on. So while GitHub Copilot is great at generating code based on existing patterns and best practices, it might not be as good at coming up with truly innovative solutions. This could limit the creative potential of developers who rely too heavily on the tool.

**TLDR; We are still needed :)** 

## Copilot Plan Comparison

**Prompt:** For a small team of 12 developers is co-pilot individual or business the best option?

**Response: (Written with Google Gemini)**

“For a small team of 12 developers, the best option between GitHub Copilot Individual and Business depends on your specific needs and priorities. Here's a breakdown of the pros and cons of each option for your team size:

**Individual:**

**Pros:**

- **Lower cost:** At $10/month per user, it's significantly cheaper than the Business plan for small teams.
- **Easy setup:** Each developer can sign up individually with their own personal account.
- **No central management:** If you don't have strict security or compliance requirements, individual subscriptions let developers manage their usage autonomously.

**Cons:**

- **No central management:** Difficult to track usage, enforce policies, or monitor security risks across the team.
- **No file exclusion:** Developers can't exclude specific sensitive files from Copilot suggestions.
- **Limited security features:** Lacks additional enterprise-level security options offered by Business plans.

**Business:**

**Pros:**

- **Central management:** You can easily manage access, set policies, and monitor team usage.
- **File exclusion:** Exclude sensitive files or directories from Copilot suggestions for all users.
- **Enhanced security:** Benefit from additional enterprise-level security features available in your GitHub Enterprise Cloud configuration.
- **Audit logs:** Track usage and identify potential security risks.

**Cons:**

- **Higher cost:** At $19/user/month, it's significantly more expensive than Individual plans for small teams.
- **Setup required:** Requires setting up a team subscription and managing user access.

**In your case:**

Considering your team size of 12 developers, the cost difference between Individual and Business is significant ($120/month vs. $228/month). If budget is a top priority and your security needs are relatively basic, **Individual might be a good option.** However, if you value central management, security, and compliance features, then **Business is worth considering.**

Here are some additional factors to consider:

- **Security and compliance requirements:** Does your team handle sensitive data or have strict security policies?
- **Team workflow:** Do you prefer centralized management or individual autonomy?
- **Budget flexibility:** Can you accommodate the higher cost of a Business plan?

Ultimately, the best option depends on your specific needs and priorities. Consider weighing the pros and cons of each plan carefully before making a decision.”

## Summary

Overall, GitHub Copilot has the potential to significantly improve your team's development speed, code quality, and collaboration. It still requires review and testing from the user to ensure the generated code works correctly and as intended. Weigh the benefits and considerations carefully to decide if it's the right fit for your specific needs.

## Testing / Sandbox

- [https://github.com/github/copilot-codespaces-demo](https://github.com/github/copilot-codespaces-demo)

## Useful Links

Here are some useful links related to GitHub Copilot:

- [GitHub Copilot Official Website](https://copilot.github.com/)
- [GitHub Copilot FAQs](https://copilot.github.com/faq/)
- [GitHub Copilot Documentation](https://docs.github.com/en/github/copilot)
- [Getting Started with GitHub Copilot](https://docs.github.com/en/github/copilot/getting-started-with-github-copilot)
- [Ask Github Copilot About Your Workspace](https://www.youtube.com/watch?v=nd06vQuu8BQ)
- [GitHub Copilot for RStudio](https://docs.posit.co/ide/user/ide/guide/tools/copilot.html)
