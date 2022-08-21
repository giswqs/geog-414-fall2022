---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: markdown
      format_version: "1.3"
      jupytext_version: 1.11.5
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

# Conditional Statements

```{contents}
:local:
:depth: 2
```

Programming often involves examining a set of conditions and deciding which action to take based on those conditions. Python’s if statement allows you to examine the current state of a program and respond appropriately to that state.

In this lecture you’ll learn to write conditional tests, which allow you to check any condition of interest. You’ll learn to write simple if statements, and you’ll learn how to create a more complex series of if statements to identify when the exact conditions you want are present. You’ll then apply this concept to lists, so you’ll be able to write a for loop that handles most items in a list one way but handles certain items with specific values in a different way.

- [A SIMPLE EXAMPLE](#a-simple-example)
- [CONDITIONAL TESTS](#conditional-tests)
- [IF STATEMENTS](#if-statements)
- [USING IF STATEMENTS WITH LISTS](#using-if-statements-with-lists)
- [STYLING YOUR IF STATEMENTS](#styling-your-if-statements)
- [SUMMARY](#summary)

## A SIMPLE EXAMPLE <a class="anchor" id="a-simple-example"></a>

The following short example shows how if tests let you respond to special situations correctly. Imagine you have a list of cars and you want to print out the name of each car. Car names are proper names, so the names of most cars should be printed in title case. However, the value 'bmw' should be printed in all uppercase. The following code loops through a list of car names and looks for the value 'bmw'. Whenever the value is 'bmw', it’s printed in uppercase instead of title case:

```python
cars = ['audi', 'bmw', 'subaru', 'toyota']

for car in cars:
    if car == 'bmw':
        print(car.upper())
    else:
        print(car.title())
```

## CONDITIONAL TESTS <a class="anchor" id="conditional-tests"></a>

At the heart of every if statement is an expression that can be evaluated as True or False and is called a conditional test. Python uses the values True and False to decide whether the code in an if statement should be executed. If a conditional test evaluates to True, Python executes the code following the if statement. If the test evaluates to False, Python ignores the code following the if statement.

### Checking for Equality

Most conditional tests compare the current value of a variable to a specific value of interest. The simplest conditional test checks whether the value of a variable is equal to the value of interest:

```python
car = 'bmw'
car == 'bmw'
```

The line at ➊ sets the value of car to 'bmw' using a single equal sign, as you’ve seen many times already. The line at ➋ checks whether the value of car is 'bmw' using a double equal sign (==). This equality operator returns True if the values on the left and right side of the operator match, and False if they don’t match. The values in this example match, so Python returns True.

```python
car = 'audi'
car == 'bmw'
```

A single equal sign is really a statement; you might read the code at ➊ as “Set the value of car equal to 'audi'.” On the other hand, a double equal sign, like the one at ➋, asks a question: “Is the value of car equal to 'bmw'?” Most programming languages use equal signs in this way.

### Ignoring Case When Checking for Equality

Testing for equality is case sensitive in Python. For example, two values with different capitalization are not considered equal:

```python
car = 'Audi'
car == 'audi'
```

If case matters, this behavior is advantageous. But if case doesn’t matter and instead you just want to test the value of a variable, you can convert the variable’s value to lowercase before doing the comparison:

```python
car = 'Audi'
car.lower() == 'audi'
```

This test would return True no matter how the value 'Audi' is formatted because the test is now case insensitive. The lower() function doesn’t change the value that was originally stored in car, so you can do this kind of comparison without affecting the original variable:

```python
car = 'Audi'
car.lower() == 'audi'
```

```python
print(car)
```

Websites enforce certain rules for the data that users enter in a manner similar to this. For example, a site might use a conditional test like this to ensure that every user has a truly unique username, not just a variation on the capitalization of another person’s username. When someone submits a new username, that new username is converted to lowercase and compared to the lowercase versions of all existing usernames. During this check, a username like 'John' will be rejected if any variation of 'john' is already in use.

### Checking for Inequality

When you want to determine whether two values are not equal, you can combine an exclamation point and an equal sign (!=). The exclamation point represents not, as it does in many programming languages.

Let’s use another if statement to examine how to use the inequality operator. We’ll store a requested pizza topping in a variable and then print a message if the person did not order anchovies:

```python
requested_topping = 'mushrooms'
if requested_topping != 'anchovies':
    print("Hold the anchovies!")
```

### Numerical Comparisons

Testing numerical values is pretty straightforward. For example, the following code checks whether a person is 18 years old:

```python
age = 18
age == 18
```

You can also test to see if two numbers are not equal. For example, the following code prints a message if the given answer is not correct:

```python
answer = 17
if answer != 42:
    print("That is not the correct answer. Please try again!")
```

You can include various mathematical comparisons in your conditional statements as well, such as less than, less than or equal to, greater than, and greater than or equal to:

```python
age = 19
age < 21
```

```python
age <= 21
```

```python
age > 21
```

```python
age >= 21
```

### Checking Multiple Conditions

You may want to check multiple conditions at the same time. For example, sometimes you might need two conditions to be True to take an action. Other times you might be satisfied with just one condition being True. The keywords and and or can help you in these situations.

#### Using and to Check Multiple Conditions

To check whether two conditions are both True simultaneously, use the keyword and to combine the two conditional tests; if each test passes, the overall expression evaluates to True. If either test fails or if both tests fail, the expression evaluates to False.

For example, you can check whether two people are both over 21 using the following test:

```python
age_0 = 22
age_1 = 18
age_0 >= 21 and age_1 >= 21
```

```python
age_1 = 22
age_0 >= 21 and age_1 >= 21
```

To improve readability, you can use parentheses around the individual tests, but they are not required. If you use parentheses, your test would look like this:

```python
(age_0 >= 21) and (age_1 >= 21)
```

### Using or to Check Multiple Conditions

The keyword or allows you to check multiple conditions as well, but it passes when either or both of the individual tests pass. An or expression fails only when both individual tests fail.

Let’s consider two ages again, but this time we’ll look for only one person to be over 21:

```python
age_0 = 22
age_1 = 18
age_0 >= 21 or age_1 >= 21
```

```python
age_0 = 18
age_0 >= 21 or age_1 >= 21
```

### Checking Whether a Value Is in a List

Sometimes it’s important to check whether a list contains a certain value before taking an action. For example, you might want to check whether a new username already exists in a list of current usernames before completing someone’s registration on a website. In a mapping project, you might want to check whether a submitted location already exists in a list of known locations.

To find out whether a particular value is already in a list, use the keyword in. Let’s consider some code you might write for a pizzeria. We’ll make a list of toppings a customer has requested for a pizza and then check whether certain toppings are in the list.

```python
requested_toppings = ['mushrooms', 'onions', 'pineapple']
'mushrooms' in requested_toppings
```

```python
'pepperoni' in requested_toppings
```

### Checking Whether a Value Is Not in a List

Other times, it’s important to know if a value does not appear in a list. You can use the keyword not in this situation. For example, consider a list of users who are banned from commenting in a forum. You can check whether a user has been banned before allowing that person to submit a comment:

```python
banned_users = ['andrew', 'carolina', 'david']
user = 'marie'

if user not in banned_users:
    print(f"{user.title()}, you can post a response if you wish.")
```

### Boolean Expressions

As you learn more about programming, you’ll hear the term Boolean expression at some point. A Boolean expression is just another name for a conditional test. A Boolean value is either True or False, just like the value of a conditional expression after it has been evaluated.

Boolean values are often used to keep track of certain conditions, such as whether a game is running or whether a user can edit certain content on a website:

```python
game_active = True
can_edit = False
```

## IF STATEMENTS <a class="anchor" id="if-statements"></a>

When you understand conditional tests, you can start writing if statements. Several different kinds of if statements exist, and your choice of which to use depends on the number of conditions you need to test. You saw several examples of if statements in the discussion about conditional tests, but now let’s dig deeper into the topic.

### Simple if Statements

The simplest kind of if statement has one test and one action:

```
if conditional_test:
    do something
```

You can put any conditional test in the first line and just about any action in the indented block following the test. If the conditional test evaluates to True, Python executes the code following the if statement. If the test evaluates to False, Python ignores the code following the if statement.

Let’s say we have a variable representing a person’s age, and we want to know if that person is old enough to vote. The following code tests whether the person can vote:

```python
age = 19
if age >= 18:
    print("You are old enough to vote!")
```

Indentation plays the same role in if statements as it did in for loops. All indented lines after an if statement will be executed if the test passes, and the entire block of indented lines will be ignored if the test does not pass.

You can have as many lines of code as you want in the block following the if statement. Let’s add another line of output if the person is old enough to vote, asking if the individual has registered to vote yet:

```python
age = 19
if age >= 18:
    print("You are old enough to vote!")
    print("Have you registered to vote yet?")
```

### if-else Statements

Often, you’ll want to take one action when a conditional test passes and a different action in all other cases. Python’s if-else syntax makes this possible. An if-else block is similar to a simple if statement, but the else statement allows you to define an action or set of actions that are executed when the conditional test fails.

We’ll display the same message we had previously if the person is old enough to vote, but this time we’ll add a message for anyone who is not old enough to vote:

```python
age = 17
if age >= 18:
    print("You are old enough to vote!")
    print("Have you registered to vote yet?")
else:
    print("Sorry, you are too young to vote.")
    print("Please register to vote as soon as you turn 18!")
```

### The if-elif-else Chain

Often, you’ll need to test more than two possible situations, and to evaluate these you can use Python’s if-elif-else syntax. Python executes only one block in an if-elif-else chain. It runs each conditional test in order until one passes. When a test passes, the code following that test is executed and Python skips the rest of the tests.

Many real-world situations involve more than two possible conditions. For example, consider an amusement park that charges different rates for different age groups:

- Admission for anyone under age 4 is free.
- Admission for anyone between the ages of 4 and 18 is \$25.
- Admission for anyone age 18 or older is \$40.

How can we use an if statement to determine a person’s admission rate? The following code tests for the age group of a person and then prints an admission price message:

```python
age = 12

if age < 4:
    price = 0
elif age < 18:
    price = 25
elif age < 65:
    price = 40
elif age >= 65:
    price = 20

print(f"Your admission cost is ${price}.")
```

### Using Multiple elif Blocks

You can use as many elif blocks in your code as you like. For example, if the amusement park were to implement a discount for seniors, you could add one more conditional test to the code to determine whether someone qualified for the senior discount. Let’s say that anyone 65 or older pays half the regular admission, or $20:

```python
age = 12

if age < 4:
    price = 0
elif age < 18:
    price = 25
elif age < 65:
    price = 40
else:
    price = 20

print(f"Your admission cost is ${price}.")
```

The else block is a catchall statement. It matches any condition that wasn’t matched by a specific if or elif test, and that can sometimes include invalid or even malicious data. If you have a specific final condition you are testing for, consider using a final elif block and omit the else block. As a result, you’ll gain extra confidence that your code will run only under the correct conditions.

### Testing Multiple Conditions

The if-elif-else chain is powerful, but it’s only appropriate to use when you just need one test to pass. As soon as Python finds one test that passes, it skips the rest of the tests. This behavior is beneficial, because it’s efficient and allows you to test for one specific condition.

However, sometimes it’s important to check all of the conditions of interest. In this case, you should use a series of simple if statements with no elif or else blocks. This technique makes sense when more than one condition could be True, and you want to act on every condition that is True.

Let’s reconsider the pizzeria example. If someone requests a two-topping pizza, you’ll need to be sure to include both toppings on their pizza:

```python
requested_toppings = ['mushrooms', 'extra cheese']

if 'mushrooms' in requested_toppings:
    print("Adding mushrooms.")
if 'pepperoni' in requested_toppings:
    print("Adding pepperoni.")
if 'extra cheese' in requested_toppings:
    print("Adding extra cheese.")

print("\nFinished making your pizza!")
```

This code would not work properly if we used an if-elif-else block, because the code would stop running after only one test passes. Here’s what that would look like:

```python
requested_toppings = ['mushrooms', 'extra cheese']

if 'mushrooms' in requested_toppings:
    print("Adding mushrooms.")
elif 'pepperoni' in requested_toppings:
    print("Adding pepperoni.")
elif 'extra cheese' in requested_toppings:
    print("Adding extra cheese.")

print("\nFinished making your pizza!")
```

In summary, if you want only one block of code to run, use an if-elif-else chain. If more than one block of code needs to run, use a series of independent if statements.

## USING IF STATEMENTS WITH LISTS <a class="anchor" id="using-if-statements-with-lists"></a>

You can do some interesting work when you combine lists and if statements. You can watch for special values that need to be treated differently than other values in the list. You can manage changing conditions efficiently, such as the availability of certain items in a restaurant throughout a shift. You can also begin to prove that your code works as you expect it to in all possible situations.

### Checking for Special Items

This lecture began with a simple example that showed how to handle a special value like 'bmw', which needed to be printed in a different format than other values in the list. Now that you have a basic understanding of conditional tests and if statements, let’s take a closer look at how you can watch for special values in a list and handle those values appropriately.

Let’s continue with the pizzeria example. The pizzeria displays a message whenever a topping is added to your pizza, as it’s being made. The code for this action can be written very efficiently by making a list of toppings the customer has requested and using a loop to announce each topping as it’s added to the pizza:

```python
requested_toppings = ['mushrooms', 'green peppers', 'extra cheese']

for requested_topping in requested_toppings:
    print(f"Adding {requested_topping}.")

print("\nFinished making your pizza!")
```

The output is straightforward because this code is just a simple for loop. But what if the pizzeria runs out of green peppers? An if statement inside the for loop can handle this situation appropriately:

```python
requested_toppings = ['mushrooms', 'green peppers', 'extra cheese']

for requested_topping in requested_toppings:
    if requested_topping == 'green peppers':
        print("Sorry, we are out of green peppers right now.")
    else:
        print(f"Adding {requested_topping}.")

print("\nFinished making your pizza!")
```

### Checking That a List Is Not Empty

We’ve made a simple assumption about every list we’ve worked with so far; we’ve assumed that each list has at least one item in it. Soon we’ll let users provide the information that’s stored in a list, so we won’t be able to assume that a list has any items in it each time a loop is run. In this situation, it’s useful to check whether a list is empty before running a for loop.

As an example, let’s check whether the list of requested toppings is empty before building the pizza. If the list is empty, we’ll prompt the user and make sure they want a plain pizza. If the list is not empty, we’ll build the pizza just as we did in the previous examples:

```python
requested_toppings = []

if requested_toppings:
    for requested_topping in requested_toppings:
        print(f"Adding {requested_topping}.")
    print("\nFinished making your pizza!")
else:
    print("Are you sure you want a plain pizza?")
```

### Using Multiple Lists

People will ask for just about anything, especially when it comes to pizza toppings. What if a customer actually wants french fries on their pizza? You can use lists and if statements to make sure your input makes sense before you act on it.

Let’s watch out for unusual topping requests before we build a pizza. The following example defines two lists. The first is a list of available toppings at the pizzeria, and the second is the list of toppings that the user has requested. This time, each item in requested_toppings is checked against the list of available toppings before it’s added to the pizza:

```python
available_toppings = ['mushrooms', 'olives', 'green peppers','pepperoni', 'pineapple', 'extra cheese']

requested_toppings = ['mushrooms', 'french fries', 'extra cheese']

for requested_topping in requested_toppings:
    if requested_topping in available_toppings:
        print(f"Adding {requested_topping}.")
    else:
        print(f"Sorry, we don't have {requested_topping}.")

print("\nFinished making your pizza!")
```

## STYLING YOUR IF STATEMENTS <a class="anchor" id="styling-your-if-statements"></a>

In every example in this chapter, you’ve seen good styling habits. The only recommendation PEP 8 provides for styling conditional tests is to use a single space around comparison operators, such as ==, >=, <=. For example:

```
if age < 4:
```

is better than:

```
if age<4:
```

Such spacing does not affect the way Python interprets your code; it just makes your code easier for you and others to read.

## SUMMARY <a class="anchor" id="summary"></a>

In this chapter you learned how to write conditional tests, which always evaluate to True or False. You learned to write simple if statements, if-else chains, and if-elif-else chains. You began using these structures to identify particular conditions you needed to test and to know when those conditions have been met in your programs. You learned to handle certain items in a list differently than all other items while continuing to utilize the efficiency of a for loop. You also revisited Python’s style recommendations to ensure that your increasingly complex programs are still relatively easy to read and understand.
