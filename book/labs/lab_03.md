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

# Lab 3

**Firstname Lastname**

```{code-cell} ipython3
from datetime import datetime

now = datetime.now()
print(f"Submitted time: {now}")
```

# Question 1

**Person:** Use a dictionary to store information about a person you know. Store their first name, last name, age, and the city in which they live. You should have keys such as first_name, last_name, age, and city. Print each piece of information stored in your dictionary.

```{code-cell} ipython3

```

## Question 2

**Favorite Numbers:** Use a dictionary to store people’s favorite numbers. Think of five names, and use them as keys in your dictionary. Think of a favorite number for each person, and store each as a value in your dictionary. Print each person’s name and their favorite number. For even more fun, poll a few friends and get some actual data for your program.

```{code-cell} ipython3

```

## Question 3

**Glossary:** A Python dictionary can be used to model an actual dictionary. However, to avoid confusion, let’s call it a glossary.

- Think of five programming words you’ve learned about in the previous chapters. Use these words as the keys in your glossary, and store their meanings as values.
- Print each word and its meaning as neatly formatted output. You might print the word followed by a colon and then its meaning, or print the word on one line and then print its meaning indented on a second line. Use the newline character (\n) to insert a blank line between each word-meaning pair in your output.

```{code-cell} ipython3

```

## Question 4

**Glossary 2:** Now that you know how to loop through a dictionary, clean up the code from Question 3 by replacing your series of print() calls with a loop that runs through the dictionary’s keys and values. When you’re sure that your loop works, add five more Python terms to your glossary. When you run your program again, these new words and meanings should automatically be included in the output.

```{code-cell} ipython3

```

## Question 5

**Rivers:** Make a dictionary containing three major rivers and the country each river runs through. One key-value pair might be 'nile': 'egypt'.

- Use a loop to print a sentence about each river, such as _The Nile runs through Egypt._
- Use a loop to print the name of each river included in the dictionary.
- Use a loop to print the name of each country included in the dictionary.

```{code-cell} ipython3

```

## Question 6

**Cities:** Make a dictionary called `cities`. Use the names of three cities as keys in your dictionary. Create a dictionary of information about each city and include the country that the city is in, its approximate population, and one fact about that city. The keys for each city’s dictionary should be something like `country`, `population`, and `fact`. Print the name of each city and all of the information you have stored about it.

```{code-cell} ipython3

```

## Question 7

**Rental Car:** Write a program that asks the user what kind of rental car they would like. Print a message about that car, such as “Let me see if I can find you a Subaru.”

```{code-cell} ipython3

```

## Question 8

**Restaurant Seating:** Write a program that asks the user how many people are in their dinner group. If the answer is more than eight, print a message saying they’ll have to wait for a table. Otherwise, report that their table is ready.

```{code-cell} ipython3

```

## Question 9

**Multiples of Ten:** Ask the user for a number, and then report whether the number is a multiple of 10 or not.

```{code-cell} ipython3

```

## Question 10

**Pizza Toppings:** Write a loop that prompts the user to enter a series of pizza toppings until they enter a 'quit' value. As they enter each topping, print a message saying you’ll add that topping to their pizza.

```{code-cell} ipython3

```

## Question 11

**Message:** Write a function called `display_message()` that prints one sentence telling everyone what you are learning about in this chapter. Call the function, and make sure the message displays correctly.

```{code-cell} ipython3

```

## Question 12

**Favorite Book:** Write a function called `favorite_book()` that accepts one parameter, title. The function should print a message, such as `One of my favorite books is Alice in Wonderland`. Call the function, making sure to include a book title as an argument in the function call.

```{code-cell} ipython3

```

## Question 13

**T-Shirt:** Write a function called `make_shirt()` that accepts a size and the text of a message that should be printed on the shirt. The function should print a sentence summarizing the size of the shirt and the message printed on it.

Call the function once using positional arguments to make a shirt. Call the function a second time using keyword arguments.

```{code-cell} ipython3

```

## Question 14

**Large Shirts:** Modify the `make_shirt()` function so that shirts are large by default with a message that reads _I love Python_. Make a large shirt and a medium shirt with the default message, and a shirt of any size with a different message.

```{code-cell} ipython3

```

## Question 15

**Cities:** Write a function called `describe_city()` that accepts the name of a city and its country. The function should print a simple sentence, such as `Reykjavik is in Iceland`. Give the parameter for the country a default value. Call your function for three different cities, at least one of which is not in the default country.

```{code-cell} ipython3

```

## Question 16

**City Names:** Write a function called `city_country()` that takes in the name of a city and its country. The function should return a string formatted like this:

```text
Santiago, Chile
```

Call your function with at least three city-country pairs, and print the values that are returned.

```{code-cell} ipython3

```

## Question 17

**Album:** Write a function called `make_album()` that builds a dictionary describing a music album. The function should take in an artist name and an album title, and it should return a dictionary containing these two pieces of information. Use the function to make three dictionaries representing different albums. Print each return value to show that the dictionaries are storing the album information correctly.

Use None to add an optional parameter to make_album() that allows you to store the number of songs on an album. If the calling line includes a value for the number of songs, add that value to the album’s dictionary. Make at least one new function call that includes the number of songs on an album.

```{code-cell} ipython3

```

## Question 18

**User Albums:** Start with your program from Question 17. Write a `while` loop that allows users to enter an album’s artist and title. Once you have that information, call `make_album()` with the user’s input and print the dictionary that’s created. Be sure to include a quit value in the `while` loop.

```{code-cell} ipython3

```

## Question 19

**Messages:** Make a list containing a series of short text messages. Pass the list to a function called `show_messages()`, which prints each text message.

```{code-cell} ipython3

```

## Question 20

**Sending Messages:** Start with a copy of your program from Question 19. Write a function called `send_messages()` that prints each text message and moves each message to a new list called `sent_messages` as it’s printed. After calling the function, print both of your lists to make sure the messages were moved correctly.

```{code-cell} ipython3

```
