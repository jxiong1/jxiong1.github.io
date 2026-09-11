---
layout: essay
type: essay
title: "Asking Smart Questions as a Software Engineer"
# All dates must be YYYY-MM-DD format!
date: 2026-09-10
published: true
labels:
  - Engineering
---

<img width="200px" class="rounded float-start pe-4" src="../img/difficulty/degree_difficulty.jpg">

## Introduction

The skill of asking a question is essential in the world of Software Engineering, whether if it was back when people used to ask technical inquiries on forums like Stack Overflow, or now when we look for answers by asking AI, we must compile these questions with enough context for other people or AI to give us an acccurate/satifying answer. Sometimes, doing researches on a specific problem can even resolve the original question and allows us to analyze the problem and solve it with ease or come up with a follw up more percise question that would leads to the solution.

In constrast, a vague with little information may lead to requests for clarification, non useful answers, or even downvotes on sites like Stack Overflow.

Therefore, it is important to ask "Smart" questions in order to get the most out of both the contributors of a forum or a chatbot of a AI model.

## What Makes a Question "Smart"?
In the essay "How To Ask Questions The Smart Way" by Eric Steven Raymond, he emphasized that in order to amke a Question "smart", a person should make a reasonable effort to solve a problem before asking others for help. This includes searching existing discussions, searching the web, reading documentation, experimenting with the problem, and examining error messages. When a question is eventually posted, the person should explain what they are trying to accomplish, what they have already tried, and what specifically went wrong.

Another important thing is to provide a reproducible example to give to the other developers/contributors/AI. This consists of the smallest amount of code and information necessary to reproduce the problem, preventing people from having to guess what the original developer's environment or intentions might be.

Raymond also emphasizes being explicit about the actual question. Instead of simply saying that something "doesn't work," a developer should explain the expected behavior, the actual behavior, and the difference between the two. This gives potential answers a clear direction.

These actions benefit both the person/AI asking the question and the people answering it. The person asking is forced to understand and investigate the problem more carefully, while the responder answering receives enough information to provide a useful solution.

## Example of a Smart Question

One example I found on Stack Overflow is the question **"Parse out date from filename and sort by date"**, which inquires about how to sort files based on dates contained within their filenames. [Stack Overflow: Parse out date from filename and sort by date](https://stackoverflow.com/questions/48529660/parse-out-date-from-filename-and-sort-by-date)

The question revolves around PowerShell and filenames containing dates and times. The developer was attempting to work with filenames formatted in a way that contained year, month, day, hour, and minute information. The question specifically focuses on how to interpret or sort the date information rather than asking a broad question such as "How do I sort files?"

**Question:** [Python date of the previous month](https://stackoverflow.com/questions/48529660/parse-out-date-from-filename-and-sort-by-date)

> **Q: python date of the previous month**
>
> I am trying to get the date of the previous month with Python. Here is what I've tried:
>
> ```python
> str(time.strftime('%Y')) + str(int(time.strftime('%m')) - 1)
> ```
>
> However, this way is bad for 2 reasons: First it returns `20122` for the
> February of 2012 (instead of `201202`) and secondly it will return `0`
> instead of `12` on January.
>
> I have solved this trouble in bash with:
>
> ```bash
> echo $(date -d"3 month ago" "+%G%m%d")
> ```
>
> I think that if bash has a built-in way for this purpose, then Python,
> much more equipped, should provide something better than forcing writing
> one's own script to achieve this goal.
>
> Of course I could do something like:
>
> ```python
> if int(time.strftime('%m')) == 1:
>     return '12'
> else:
>     if int(time.strftime('%m')) < 10:
>         return '0' + str(time.strftime('%m') - 1)
>     else:
>         return str(time.strftime('%m') - 1)
> ```
>
> I have not tested this code and I don't want to use it anyway (unless I
> can't find any other way).
>
> Thanks for your help!

The question also provides relevant context about the problem and identifies the tools being used. This allows the problem to be specific enough that another developer can understand what the developer is trying to accomplish without needing a large amount of unrelated information.

The response demonstrates why a well-formed question can lead to an efficient and effective solution. The answer given by other contributers points out that the date and time components of the filename are already arranged from the largest unit of time to the smallest. Because of this ordering, the filenames can be sorted as strings rather than requiring the developer to perform complicated date conversions. This solution addresses the underlying problem, since the responder recognizes the desired result can be achieved in a much simplier fasion.

### Answer

> **With this format:**
>
> `myFileYYYYMMddHHmm.file`
>
> The individual parts of the date and time are already arranged from largest
> (the year) to smallest (the minute) — this makes the string sortable!
>
> Only thing we need to do is grab the last 12 digits of the file name before
> the extension:
>
> ```powershell
> $SortedArray = Get-ChildItem *.file | Sort-Object { $_.BaseName -replace '^.*(\d{12})$', '$1' }
> ```
>
> The regex pattern used:
>
> ```text
> ^.*(\d{12})$
> ```
>
> Can be broken down as follows:
>
> ```text
> ^          # start of string
> .*         # any character, 0 or more times
> (          # capture group
>   \d{12}   # any digit, 12 times
> )          # end of capture group
> $          # end of string
> ```
>
> The regex engine will expand `$1` in the substitution string to "capture
> group #1", which is the 12 digits we picked up at the end.



## Example of a Question That Is Not Smart

For comparison, I examined the Stack Overflow question **"how to extract data with days ago and get specific time in python."** [Stack Overflow: How to extract data with days ago and get specific time in Python](https://stackoverflow.com/questions/73852334/how-to-extract-data-with-days-ago-and-get-specific-time-in-python)

**Question:** [How to extract data with days ago and get specific time in Python](https://stackoverflow.com/questions/73852334/how-to-extract-data-with-days-ago-and-get-specific-time-in-python)

> **Q: how to extract data with days ago and get specific time in python**
>
> i want to extract data from facebook marketplace using selenium , i want to get the date of the products for the past 2 days (ads listed 2 days ) then from the past n weeks ( ads listed n weeks ) starting from today , I think i can get it by thd function (find_elements_by...) but I don't know how to use it , thank you in adavance this prod for exemple Date = find_elements_byName('value').text  Date_prod = Current_Time - Date 

The developer explains that they are trying to extract information from Facebook Marketplace using Selenium. They want to determine when products were listed based on text such as "2 days ago" and then calculate the corresponding date. However, the question is difficult to understand because the description is unclear and contains very little organized information about the actual problem.

The developer gives a short piece of code resembling:

```python
Date = find_elements_byName('value').text
Date_prod = Current_Time - Date
```

However, the code does not provide enough information to reproduce the problem. It does not clearly establish what the input looks like, what the program currently produces, what the expected output is, or what specific error is occurring.

The responses demonstrate the consequences of asking a question without enough information. Instead of immediately providing a solution, responders ask the developer to provide a **minimal reproducible example** and explain what they have tried. One response simply asks what the developer has tried and requests a minimal reproducible example. Another response similarly points the developer toward Stack Overflow's guidance for creating one.

The problem is not necessarily that the underlying programming question is too difficult. Instead, the question does not provide enough information for someone else to efficiently diagnose the problem. The responders have to ask for additional information before they can meaningfully solve it.

This demonstrates one of the major problems with "not smart" questions: they can shift the work from solving the technical problem to figuring out what the person is actually asking.

## Comparing the Two Questions

The biggest difference between the two examples is the amount of useful information provided to the people answering.

The PowerShell question establishes a relatively clear goal and provides enough context for the answerer to recognize an important characteristic of the data. The answerer can immediately focus on solving the problem. As a result, the response is short but useful.

The Python question, on the other hand, leaves several important questions unanswered. It is difficult to determine exactly what the input looks like, what the Selenium code returns, what the expected output should be, and what is currently going wrong. Consequently, the first responses focus on obtaining additional information instead of solving the original problem.

This comparison also shows that a smart question does not necessarily need to be extremely long. A good technical question can be relatively short as long as it contains the information necessary to understand and reproduce the problem. The goal is not to write as much as possible; it is to provide the **right information**.

## Why Smart Questions Matter for Software Engineers

Learning how to ask smart questions is important because software engineering involves constant problem solving. No developer can know every programming language, framework, library, operating system, or development tool. Eventually, every developer will encounter a problem that requires outside knowledge.

When developers ask good questions, they make collaboration more efficient. A teammate or member of an online community can spend their time solving the actual problem instead of trying to determine what the problem is. This is especially important in professional software development, where other developers may have limited time available to help.

Smart questions also demonstrate preparation. Raymond argues that people are more likely to help when they can see that the person asking has already made an effort to understand and solve the problem. A developer who says, "I tried these two approaches, and here is the error produced by each one" gives an answerer something concrete to work with.

There is also a personal benefit. The process of preparing a good question can sometimes solve the problem before the question is even posted. Explaining the problem clearly requires the developer to think carefully about what the program is supposed to do, what it actually does, and where the two differ. This can reveal mistakes or incorrect assumptions.

Finally, smart questions create better documentation for future developers. A well-written Stack Overflow question and answer can become a useful resource for someone else experiencing the same problem. Raymond points out that good questions can help direct other people with similar problems toward a useful discussion and its resolution.

## Lessons Learned

The biggest lesson I gained from this experience is that asking for help is itself a technical skill. It is not enough to recognize that I am stuck. I also need to communicate the problem in a way that allows another person to understand it quickly.

Before asking a question, I should first search for existing solutions, read the relevant documentation, and experiment with the problem. If I still need help, I should provide a clear description of what I am trying to accomplish, include a minimal reproducible example when appropriate, explain what I expected to happen, explain what actually happened, and include relevant error messages.

I also learned that providing more information does not automatically make a question better. Unnecessary code, unrelated background information, and large amounts of output can make a question harder to understand. The goal should be to provide enough information to reproduce and understand the problem while removing everything that is not relevant.

The comparison between the two Stack Overflow examples made this difference particularly clear. The stronger question allowed the responder to quickly identify a simple solution. The weaker question caused responders to spend their initial effort asking the developer for more information. The difference was not necessarily the complexity of the programming problems, but the quality of the communication.

## Conclusion

Smart questions are an important part of becoming a smart software engineer. Programming is a collaborative discipline, and knowing how to communicate a technical problem is just as important as knowing how to write code. Raymond's guidelines emphasize preparation, clarity, specificity, and demonstrating effort before asking others for help.

The two Stack Overflow examples demonstrate the practical effects of these principles. The PowerShell question provided enough useful information for the responder to quickly identify an effective solution. The Python question did not provide enough information to reproduce the problem, causing responders to request clarification before they could provide meaningful assistance.

This experience showed me that asking a good question is not simply about getting someone else to solve a problem. A good question demonstrates that I have already tried to understand the problem and gives others the information they need to help me efficiently. Going forward, I will try to search for existing solutions first, clearly describe the problem, provide relevant evidence and code, and explain what I have already tried. These practices should make me a better communicator and, ultimately, a better software engineer.

## References

* [Eric S. Raymond — How to Ask Questions the Smart Way](https://www.catb.org/esr/faqs/smart-questions.html?utm_source=chatgpt.com)
* [Stack Overflow — Parse out date from filename and sort by date](https://stackoverflow.com/questions/48529660/parse-out-date-from-filename-and-sort-by-date?utm_source=chatgpt.com)
* [Stack Overflow — How to extract data with days ago and get specific time in Python](https://stackoverflow.com/questions/73852334/how-to-extract-data-with-days-ago-and-get-specific-time-in-python?utm_source=chatgpt.com)
