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

A Python project which scrapes a website containing daily income information for a store and generates a spreadsheet using the information collected.

<hr>

### How It's Done

The project utilized a library called `selenium` to open and input information into a website like a real user would. Then, it would collect and store the information from the HTML elements shown. Another library called `openpyxl` was used to generate an Excel spreadsheet using the information stored with `selenium`.

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

My greatest takeaway from this project is the ability to organize a large amount of code. By building custom libraries and classes, I was able to modularize my code, making it easier for me and others to understand, maintain, and troubleshoot.

<hr>