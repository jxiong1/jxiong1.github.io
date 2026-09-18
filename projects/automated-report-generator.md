---
layout: project
type: project
image: img/webscraper/python_logo.jpg
title: "Automated Report Generator"
date: 2023
published: true
labels:
  - Macro
  - Webscraping
  - Python
summary: "A Python project which scrapes a website for information and generates a spreadsheet"
---
<img width="500px" class="img-fluid" src="../img/webscraper/python_logo.jpg">

A Python project which scrapes a Point of Sale (POS) portal for data and generates a spreadsheet using the information collected. The purpose of this project is to eliminate the manual and tedious entry of mass amount of data/sale records into a spreadsheet. This project is expected to run once a week to generate weekly report for the user.

<hr>

### How It's Done

The project utilized a library called `selenium` to open and input information into a website like a real user would. Then, it would collect and store the information from the HTML elements shown. Another library called `openpyxl` was used to generate an Excel spreadsheet using the information stored with `selenium`.

During the first implementation/stage of the project, the program ran by scraping the data on a POS portal and outputting the data result to the terminal. The user would use the output in the terminal to fill in a spreadsheet for their weekly report. This eliminated the need to manually scroll through the portal site for data, and is instead summarized to the user via terminal output. After initial feedback from the user, the second implementation of the project added the `openpyxl` to directly inject the data gathered into an Excel spreadsheet, completely eliminated the need for manual inputs from the user.

<pre><code>
             Website
                |
                v
          +-------------+
          |  Selenium   |
          +-------------+
                |
                v
        Scrape HTML Elements
                |
                v
       Collect Store Income
          Information
                |
                v
          +-------------+
          |  openpyxl   |
          +-------------+
                |
                v
          Generate Excel
            Spreadsheet
</code></pre>

<hr>

### What I Learned

My greatest takeaway from this project is the ability to organize a large amount of code. By building custom libraries and classes, I was able to modularize my code, making it easier for me and others to understand, maintain, and troubleshoot. This was also a great example of software engineering, since a problem was identified, solution was proposed, test solution was implemented, received user feedback, and the final deliverable was made to completely solved the problem.

<hr>