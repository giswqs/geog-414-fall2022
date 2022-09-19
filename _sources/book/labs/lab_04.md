---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.11.5
kernelspec:
  display_name: Python 3
  language: python
  name: python3
---

# Lab 4

**Firstname Lastname**

```{code-cell} ipython3
from datetime import datetime

now = datetime.now()
print(f"Submitted time: {now}")
```

## Question 1

**Learning Python:** Open a blank file in your text editor and write a few lines summarizing what you’ve learned about Python so far. Start each line with the phrase _In Python you can. . .._ Save the file as _learning_python.txt_ in the same directory as your exercises from this chapter. Write a program that reads the file and prints what you wrote three times. Print the contents once by reading in the entire file, once by looping over the file object, and once by storing the lines in a list and then working with them outside the _with_ block.

```{code-cell} ipython3

```

## Question 2

**Learning C:** You can use the replace() method to replace any word in a string with a different word. Here’s a quick example showing how to replace 'dog' with 'cat' in a sentence:

```text
message = "I really like dogs."
message.replace('dog', 'cat')
'I really like cats.'
```

Read in each line from the file you just created, _learning_python.txt_, and replace the word _Python_ with the name of another language, such as _C_. Print each modified line to the screen.

```{code-cell} ipython3

```

## Question 3

**Guest:** Write a program that prompts the user for their name. When they respond, write their name to a file called guest.txt.

```{code-cell} ipython3

```

## Question 4

**Guest Book:** Write a while loop that prompts users for their name. When they enter their name, print a greeting to the screen and add a line recording their visit in a file called guest_book.txt. Make sure each entry appears on a new line in the file.

```{code-cell} ipython3

```

## Question 5

**Programming Poll:** Write a while loop that asks people why they like programming. Each time someone enters a reason, add their reason to a file that stores all the responses.

```{code-cell} ipython3

```

## Question 6

**Addition:** One common problem when prompting for numerical input occurs when people provide text instead of numbers. When you try to convert the input to an int, you’ll get a ValueError. Write a program that prompts for two numbers. Add them together and print the result. Catch the ValueError if either input value is not a number, and print a friendly error message. Test your program by entering two numbers and then by entering some text instead of a number.

```{code-cell} ipython3

```

## Question 7

**Addition Calculator:** Wrap your code from Question 6 in a while loop so the user can continue entering numbers even if they make a mistake and enter text instead of a number.

```{code-cell} ipython3

```

## Question 8

**Cats and Dogs:** Make two files, _cats.txt_ and _dogs.txt_. Store at least three names of cats in the first file and three names of dogs in the second file. Write a program that tries to read these files and print the contents of the file to the screen. Wrap your code in a `try-except` block to catch the `FileNotFound` error, and print a friendly message if a file is missing. Move one of the files to a different location on your system, and make sure the code in the `except` block executes properly.

```{code-cell} ipython3

```

## Question 9

**Silent Cats and Dogs:** Modify your except block in Question 8 to fail silently if either file is missing.

```{code-cell} ipython3

```

## Question 10

**Common Words:** Visit Project Gutenberg (<https://gutenberg.org/>) and find a few texts you’d like to analyze. Download the text files for these works, or copy the raw text from your browser into a text file on your computer. You can use the `count()` method to find out how many times a word or phrase appears in a string. For example, the following code counts the number of times 'row' appears in a string:

```{code-cell} ipython3
line = "Row, row, row your boat"
line.count('row')
```

```{code-cell} ipython3
line.lower().count('row')
```

Notice that converting the string to lowercase using lower() catches all appearances of the word you’re looking for, regardless of how it’s formatted.

Write a program that reads the files you found at Project Gutenberg and determines how many times the word `the` appears in each text. This will be an approximation because it will also count words such as `then` and `there`. Try counting `the`, with a space in the string, and see how much lower your count is.

```{code-cell} ipython3

```
