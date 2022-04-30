author: Jan Kirenz
summary:
id: webscraping
tags:
categories:
environments: Web
status: Published
feedback link: https://github.com/kirenz/codelabs/blob/master/markdown/webscraping

# Web Scraping in Python

<!-- ------------------------ -->
## Overview

Duration: 0:05:00

### What we cover

In this tutorial we cover the basics of web scraping (also called web harvesting, or web data extraction) with Python to extract data from websites.

We will cover:

<aside class="positive">

- Basics of HTML elements
- CSS Syntax
- CSS selectors and SelectorGadget
- Python libraries

</aside>


*The content about HTML and CSS selesctors is mainly based on Dmytro Perepolkin's ["Introduction to HTML elements"](https://rvest.tidyverse.org/articles/harvesting-the-web.html)*

<!-- ------------------------ -->
## Prerequisites

Duration: 0:01:00

To start this tutorial, you need:

- The open source data science platform [Anaconda](https://kirenz.github.io/python-basics/docs/programming-toolkit.html#anaconda)

- A [Google Chrome Web-Browser](https://www.google.com/intl/de_de/chrome/)


<!-- ------------------------ -->
## HTML Elements 

Duration: 0:10:00


- HTML stands for "Hyper Text Markup Language". 

- A **HTML page** consists of a series of *elements* which browsers use to interpret how to display the content. Below is a visualization of a simple HTML page structure:

<img src="img/html-page.png" alt="HTML page" width="200">

- **HTML tags** are names of the *elements* surrounded by angle brackets `< >` For example, the `<h1>` tag defines the most important heading:  `<h1> This is my most important heading </h1>`


 
- Most HTML tags come in pairs and consist of opening and a closing tag, known as **start tag** and **end tag**, where the end tag name is preceded by the forward slash `/`.


- It is also possible to define **HTML attributes** inside HTML tags. They provide additional information about HTML elements, such as   
  - hyperlinks for text, 
  - width and height for images


- Attributes are always defined in the start tag and come in name="value" pairs


<aside class="positive">
For example, The `<a>` tag defines a hyperlink, which is used to link from one page to another. The most important attribute of the `<a>` element is the href attribute, which indicates the link's destination: 

`<a href="https://www.example.com">  Here is my anchor text </a>`
</aside>

Watch this short video from w3schools which covers the basics of HTML: 


<video id="ewZ_YWbIWXI"></video>


*You can learn more about HTML tags and attributes from online resources, such as [W3schools](https://www.w3schools.com/html/default.asp)*


<!-- ------------------------ -->
## CSS Syntax

Duration: 0:05:00

- CSS stands for Cascading Style Sheets

- It is the language we use to style an HTML document

- CSS describes how HTML elements should be displayed


Watch this short video tutorial from the CSS Syntax chapter of the CSS tutorial on w3schools.com:

<video id="QqmCs2UTS8s"></video>


<!-- ------------------------ -->
## CSS Selectors

Duration: 0:05:00

- CSS selectors represent patterns for locating HTML elements 

- They can be used not only for styling, but also for extracting the content of these elements

<aside class="negative">
Try to solve the first 4 tasks in this CSS selector game:  https://flukeout.github.io/
</aside>


- **Selector Gadget** is an open source tool which allows CSS selector generation and discovery

<video id=52055686></video>

- Install the [SelectorGadget](https://chrome.google.com/webstore/detail/selectorgadget/mhjhnkcfbdhnjickkkdbjoemdmbfginb) extension in Google Chrome

- Lets have a look at the [quotes to scrape](http://quotes.toscrape.com/) and inspect the content of the page

- You can now use the extension (click at the magnifying glass symbol at the top right side of your Google Chrome browser) to inspect the site


*To learn more about CSS Selectors, review w3schools [CSS Selector Reference](https://www.w3schools.com/cssref/css_selectors.asp)*



<!-- ------------------------ -->
## Txt

Duration: 0:05:00

Txt

<!-- ------------------------ -->
## What's next?

Duration: 0:02:00

Congratulations! You have completed the tutorial and learned how to:

✅ Install  
✅ Use  
✅ Implement  

Next, you may want to proceed with this tutorial:

- 💻[](https://kirenz.github.io/codelabs/codelabs/webscraping


<img src="img/Jan.png" alt="Jan Kirenz" width="100">

Thank you for participating in this tutorial. If you found any issues along the way I'd appreciate it if you'd raise them by clicking the "Report a mistake" button at the bottom left of this site.

*Copyright: Jan Kirenz (2021) | [kirenz.com](https://www.kirenz.com) | [CC BY-NC 2.0 License](https://creativecommons.org/licenses/by-nc/2.0/)*