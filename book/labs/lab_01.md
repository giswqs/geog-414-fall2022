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

# Lab 1

**Firstname Lastname**

```{code-cell} ipython3
from datetime import datetime

now = datetime.now()
print(f"Submitted time: {now}")
```

## Question 1

**Simple Message:** Assign a message to a variable, and then print that message.

```{code-cell} ipython3

```

## Question 2

**Simple Messages:** Assign a message to a variable, and print that message. Then change the value of the variable to a new message, and print the new message.

```{code-cell} ipython3

```

## Question 3

**Personal Message:** Use a variable to represent a person’s name, and print a message to that person. Your message should be simple, such as, “Hello Eric, would you like to learn some Python today?”

```{code-cell} ipython3

```

## Question 4

**Name Cases:** Use a variable to represent a person’s name, and then print that person’s name in lowercase, uppercase, and title case.

```{code-cell} ipython3

```

## Question 5

**Famous Quote:** Find a quote from a famous person you admire. Print the quote and the name of its author. Your output should look something like the following, including the quotation marks:

```text
Albert Einstein once said, “A person who never made a mistake never tried anything new.”
```

```{code-cell} ipython3

```

## Question 6

**Famous Quote 2:** Repeat Exercise 2-5, but this time, represent the famous person’s name using a variable called famous_person. Then compose your message and represent it with a new variable called message. Print your
message.

```{code-cell} ipython3

```

## Question 7

**Stripping Names:** Use a variable to represent a person’s name, and include some whitespace characters at the beginning and end of the name. Make sure you use each character combination, "\t" and "\n", at least once.
Print the name once, so the whitespace around the name is displayed. Then print the name using each of the three stripping functions, lstrip(), rstrip(), and strip().

```{code-cell} ipython3

```

## Question 8

**Number Eight:** Write addition, subtraction, multiplication, and division operations that each result in the number 8. Be sure to enclose your operations in print() calls to see the results. You should create four lines that look like this:

```text
print(5 + 3)
```

Your output should simply be four lines with the number 8 appearing once on each line.

```{code-cell} ipython3

```

## Question 9

**Favorite Number:** Use a variable to represent your favorite number. Then, using that variable, create a message that reveals your favorite number. Print that message.

```{code-cell} ipython3

```

## Question 10

**Adding Comments:** Choose two of the programs you’ve written, and add at least one comment to each. If you don’t have anything specific to write because your programs are too simple at this point, just add your name and
the current date at the top of each program file. Then write one sentence describing what the program does.

```{code-cell} ipython3

```

## Question 11

**Names:** Store the names of a few of your friends in a list called names. Print
each person’s name by accessing each element in the list, one at a time.

```{code-cell} ipython3

```

## Question 12

**Greetings:** Start with the list you used in Question 11, but instead of just printing each person’s name, print a message to them. The text of each message should be the same, but each message should be personalized with the person’s name.

```{code-cell} ipython3

```

## Question 13

**Your Own List:** Think of your favorite mode of transportation, such as a motorcycle or a car, and make a list that stores several examples. Use your list to print a series of statements about these items, such as “I would like to own a Honda motorcycle.”

```{code-cell} ipython3

```

## Question 14

**Guest List:** If you could invite anyone, living or deceased, to dinner, who would you invite? Make a list that includes at least three people you’d like to invite to dinner. Then use your list to print a message to each person, inviting them to dinner.

```{code-cell} ipython3

```

## Question 15

**Changing Guest List:** You just heard that one of your guests can’t make the dinner, so you need to send out a new set of invitations. You’ll have to think of someone else to invite.

+++

Start with your program from Question 14. Add a print() call at the end of your program stating the name of the guest who can’t make it.

```{code-cell} ipython3

```

Modify your list, replacing the name of the guest who can’t make it with the name of the new person you are inviting.

```{code-cell} ipython3

```

Print a second set of invitation messages, one for each person who is still in your list.

```{code-cell} ipython3

```

## Question 16

**More Guests:** You just found a bigger dinner table, so now more space is available. Think of three more guests to invite to dinner.

+++

Start with your program from Question 14 or Question 15. Add a print() call to the end of your program informing people that you found a bigger dinner table.

```{code-cell} ipython3

```

Use insert() to add one new guest to the beginning of your list.

```{code-cell} ipython3

```

Use insert() to add one new guest to the middle of your list.

```{code-cell} ipython3

```

Use append() to add one new guest to the end of your list.

```{code-cell} ipython3

```

Print a new set of invitation messages, one for each person in your list.

```{code-cell} ipython3

```

## Question 17

**Shrinking Guest List:** You just found out that your new dinner table won’t arrive in time for the dinner, and you have space for only two guests.

Start with your program from Question 16. Add a new line that prints a message saying that you can invite only two people for dinner.

```{code-cell} ipython3

```

Use pop() to remove guests from your list one at a time until only two names remain in your list. Each time you pop a name from your list, print a message to that person letting them know you’re sorry you can’t invite them to dinner.

```{code-cell} ipython3

```

Print a message to each of the two people still on your list, letting them know they’re still invited.

```{code-cell} ipython3

```

Use del to remove the last two names from your list, so you have an empty list. Print your list to make sure you actually have an empty list at the end of your program.

```{code-cell} ipython3

```

## Question 18

**Seeing the World:** Think of at least five places in the world you’d like to visit.

Store the locations in a list. Make sure the list is not in alphabetical order.

```{code-cell} ipython3

```

Print your list in its original order. Don’t worry about printing the list neatly, just print it as a raw Python list.

```{code-cell} ipython3

```

Use sorted() to print your list in alphabetical order without modifying the actual list.

```{code-cell} ipython3

```

Show that your list is still in its original order by printing it.

```{code-cell} ipython3

```

Use sorted() to print your list in reverse alphabetical order without changing the order of the original list.

```{code-cell} ipython3

```

Show that your list is still in its original order by printing it again.

```{code-cell} ipython3

```

Use reverse() to change the order of your list. Print the list to show that its order has changed.

```{code-cell} ipython3

```

Use reverse() to change the order of your list again. Print the list to show it’s back to its original order.

```{code-cell} ipython3

```

Use sort() to change your list so it’s stored in alphabetical order. Print the list to show that its order has been changed.

```{code-cell} ipython3

```

Use sort() to change your list so it’s stored in reverse alphabetical order. Print the list to show that its order has changed.

```{code-cell} ipython3

```

## Question 19

**Dinner Guests:** Working with one of the programs from Question 14 through Question 17, use len() to print a message indicating the number of people you are inviting to dinner.

```{code-cell} ipython3

```

## Question 20

**Every Function:** Think of something you could store in a list. For example, you could make a list of mountains, rivers, countries, cities, languages, or anything else you’d like. Write a program that creates a list containing these items and then uses each function introduced in this chapter at least once.

```{code-cell} ipython3

```
