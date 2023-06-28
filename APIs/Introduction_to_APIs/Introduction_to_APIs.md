# Introduction to APIs

API stands for application programming interface. It defines how two pieces of
software communicate with each other. 

## Dara tyres and strucrured data

Data types:

- Numbers (integer and decimal)
- Text
- True/false values (Boolean)
- Custom types

JSON has three types:

- Number, string and Boolean

XML has one type:

- String

Strings:

- The word "string" is a technical term meaning "text." 
- It's essentially a group of text characters that are strung together. 
- Usually, strings are enclosed in quotation marks, either with double or single
  quotes. 
- They can have letters, numbers, punctuation, math symbols, and so on. 
- They can have spaces. 

Exemples:

- "Peter"
- "3554-22-14"
- "I take the car"

Collections:

- In addition to data types, structured data can have groups of data
- There are two common types
- Arrays (lists)
- Dictionaries (lookup table)

Arrays:

- An array is a list of data values
- Arrays have:
    - A size (how many are in the list)
    - An order (which object comes first)

For example, you could have a list of numbers, or you could have a list of strings.
You can even have lists of lists. 

Dictionaries:

- Dictionary is a collection of data keys and values
- You use the key to look up the value
- Just like in a dictionary, you use the word to look up the meaning

Exemples: In front of the colon is the key, a string in quotes, and after the colon
is the value.

Structured data

Structured data combines data types in collections. Collections can consist of other
collections. 

- You can have:
    - dictionaries of lists, a list of dictionaries, a dictionary of dictionaries

As many levels as you need. 

- This is what structured data is; it can be a very complex three of data where
  each collection is a branch and the end of each branch is a data value.

Structured data and APIs

APIs have requests and responses. 
The **responses** almost always returned information from the server in the form
of structured data, and sometimes the **requests** use structured data to pass
information to the server.

### Tools for writing the JSON and XML

Basic text editors:

- JSON and XML are text formats
- You can use the text editors that come with your operating system

For example, for Windows, you can use Notepad. For Mac OS, you can use TextEdit.

Sophisticated text editors:

- More sophisticated text editors that validate and format nicely:

For Windows, Notepad++ is an easy to use, powerful editor that is free. For both
Mac and Windows, Sublime Text is a very good tool, and I'll use it in this course.
It's not free, but there is a free trial version that you can use.

JSON and XML editors

- JSON and XML editors are available that are designed specifically for these formats.
- You can do a web search on 'JSON editor' or 'XML editor'
- Some are online

### Markdown

- As part of this course, you'll be asked to write documentation
- Markdown is a very popular format for API documentation
- So we will use Markdown for the hands-on exercises

What is Markdown? 

- It's a markup language like HTML is, but it's much simpler.
- It's very easy to learn
- it's much easier to read than HTML
- Used in many content tools such as Sphynx, Jekyll, GitHub, and ReadMe.io

Markdown detailes

- Special tools read in Markdown and convert it to HTML
- Markdown has no style information
- There are different Markdown flavors
- If you can't do something in Markdown, you can just add some HTML to do it right
  in the Markdown content

Paragraphes

- Usually, lines together are considered part of the same paragraph
- So if you want a new paragraph, put an empty line between the lines of the different
  paragraphs

Headings
- Start a line with one or more hash (#) marks to indicate headings.
- The number of hash marks indicates the heading level.

Bold and Italics

- Enclose text in single asterisks for italic.
- Enclose text in double asterisks for bold.

This is *Italics*
This is **Bold**

Monospace

- Monospace fonts are good for showing code concepts
- Enclose text in backticks (`)

This is `code`

Links

- Links takes this format: [text](link)
  The square brackets contain the text to be displayed, and the parentheses contain
  the URL for the link

Images

- Image takes this format: ![text](picture-url)
- The text is the image's alternate text

Unordered list (Bullet Points)

- Just start with an asterisk or a dash for each item in the list

Ordered Lists (Numbers)

- Start each item with a number followed by a period
- Note: The actual numbers don't matter.

Tables

- Use pipes (|) for colomns
- Use dashes (-) to separate the header row
- The pipes don't have to line up

Variations

- There are several different ways to do different formatting
- For example, here is an alternate way to do headings

For example, you can also create headings for level one by putting a line of equal
signs under the heading and then put dashes under a heading for level two.

Editors

- You can write Markdown in any text editor. 
- The easiest way to see what your Markdown looks like is to use an online Markdown
  editor.
- Search online Markdown editor.
    - We will use StackEdit in this course.

Markdown reference

Basic Markdown: Search "Markdown Daring Fireball"

- It doesn't include tables

Stackedit.io

