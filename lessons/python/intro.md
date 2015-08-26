---
layout: page
root: ../..
title: Introduction to python
---
## Introduction
In this bootcamp, we are using Wing IDE 101 as our development environment. In Wing, there are two ways that we can write python programs: using the python shell, or by  writing scripts. We'll write our first program using the command line and will then move on to writing our first script. 

## Using the Python shell
Wing IDE provides convenient command line access to python so users can test expressions and execute commands while also working on writing scripts. We will write our first program using it.

Traditionally, the first program one writes when learning a new language is called "hello world" and it is an exercise in displaying the words "hello world" using the programming language. We are going use the print command in python to do this on the python shell. In the python context, print means "display on the screen"

~~~python
>>> print "Hello, world"
~~~

When you type this in and hit enter, the phrase Hello, world appears immediately below the line of code you typed in. You've executed your first python command!

Now, let's set a variable and perform a calculation on it. Variables are set in python by declaring them. Variables are declared by using an equal sign. The variable name appears on the left side of the equals sign and its value appears on the right side. 

~~~python
>>> my_var = 5
~~~

In the above example, the variable is named my_var and it has a value of 5. This variable is stored in memory, so we can now manipulate it. Let's add 2 to my_var. To do so, we reset the value of my_var to be the current value of my_var plus 2:

~~~python
>>> my_var = my_var + 2
~~~

We do not immediately see a result returned to the screen as we need to explicitly tell python to display a result using print.

~~~ python
>>> print my_var
    7    
~~~

Next, let's add some text to our output on the screen to make it more readable. The term for combining two strings is concatenation, which means "to join together". Before we can concatenate my_var with text, however, we need to turn it into a string. Currently, it is an integer, which is a type of number. Variables with numerical data types cannot be concatenated with textual variables (known as strings); they must first be converted to strings using the str() function.

~~~ python
>>> my_var = str(my_var)
~~~

Now that we've converted our variable from an integer into a string, we can concatenate it with some text and print the result. To concatenate, you use the + sign between the two (or more) elements you wish to join. Note that strings must be contained within single or double quotes.

~~~python
>>> print "The value of my_var is currently: " + my_var
    The value of my_var is currently: 7
~~~
Note that the first appearance of the term "my_var" in the above is not replaced with the number 7 (my_var's value). This is because it is contained within the quotes, and thus python treats it as text rather than a variable. The second appearance of my_var is replaced with the number 7 as it is not within quotes and is thus evaluated as a variable by python.

We can combine the last two steps into a single line:

~~~python
>>> print "The value of my_var is currently: " + str(my_var)
    The value of my_var is currently: 7
~~~

## Writing a script
Next, we're going to write a script. Scripts are files that can be saved for reuse. This way, we don't need to type out our calculations and commands every time we want to perform a task. We can write it once and reuse it whenever we need.

Python scripts are saved with the .py extension.
  
### Writing a temperature conversion script
Now, let's write a script that converts a temperature from Celsius to Fahrenheit. First, we will create a variable that contains our temperature in Celsius and we will display it to the screen using print.

~~~ python
celsius = 15
print celsius
~~~
The formula to convert from Celsius to Fahrenheit is Celsius x 2 + 30. The multiplication sign in python is *, not x, so we type out the formula as follows:

~~~ python
celsius = 15

fahrenheit = (celsius * 2) + 30
print fahrenheit
~~~
When we run this script, the number 60 is returned. Now, let's update our script so that instead of just returning this number, the phrase "15 degrees Celsius is 60 degrees Fahrenheit" using our variables. Remember, we need to convert our numeric values into strings before we concatenate them with the text (string) we want to add to our output.

~~~ python
celsius = 15

fahrenheit = (celsius * 2) + 30
print str(celsius)+' degrees in Celsius is ' + str(fahrenheit) + ' degrees in Fahrenheit'
~~~

Currently, our variable celsius isn't actually very variable - it doesn't change! It has a "hard coded" value of 15. We can increase the usefulness of our program if we can make this variable more dynamic. For example, we could let a user input any number and we can perform the Celsius to Fahrenheit conversion on it.

To do so, we need to edit our celsius variable. Rather than setting it to the number 5, we will tell python that we want it to be a inputted number by using the input() function.

~~~ python
celsius = input()

fahrenheit = (celsius * 2) + 30
print str(celsius) + " degrees in Celsius is " + str(fahrenheit) + " degrees in Fahrenheit"
~~~

We can further improve our script by adding a textual message to our user prompt. To do so, we add the string we want to display to the user within the brackets of the input() function:


~~~ python
celsius = input("Enter a temperature in Celsius: ")

fahrenheit = (celsius * 2) + 30
print str(celsius) + " degrees in Celsius is " + str(fahrenheit) + " degrees in Fahrenheit"
~~~

### Adding a conditional / if statement
Another key concept in any programming language is the notion of conditionals. A conditional statement executes specified code only if defined conditions are met. A conditional can generally be phrased as "if x is true, then do y". Let's modify our script so that if the user inputs a temperature above 20 degrees, we add the phrase "That's pretty warm!" to our output. 

~~~ python
celsius = input("Enter a temperature in Celsius: ")

fahrenheit = (celsius * 2) + 30
print str(celsius) + " degrees in Celsius is " + str(fahrenheit) + " degrees in Fahrenheit"

if celsius > 20:
    print "That's pretty warm!"
~~~

Note the basic structure of the conditional statement above. The word "if" appears first, followed by the condition being tested and a colon. In this case, we are checking to see if the variable celsius is greater than 20 using the mathematical operator >. If this condition is true (i.e. if the value entered by the user is greater than 20), the indented code that follows is executed (i.e. our statement is printed to the screen). If this condition isn't met, nothing further happens.

We can expand our conditional statement to cover those situations where this condition isn't true using an else statement. In human language, we are going adjust our conditional so that if the temperature is above 20, we print "That's pretty warm!", otherwise (else) we will print "That's a bit cool".

~~~ python
celsius = input("Enter a temperature in Celsius: ")

fahrenheit = (celsius * 2) + 30
print str(celsius) + " degrees in Celsius is " + str(fahrenheit) + " degrees in Fahrenheit"

if celsius > 20:
    print "That's pretty warm!"
else :
    print "That's a bit cool"
~~~

Now, if we enter any value that is not greater than 20, our alternate phrase will print to the screen. But what if we want to test more than 2 conditions? Let's say we want a check for values below 5 degrees Celsius and print the phrase "That is cold!" if this condition is met. We can expand our conditional using an else if statement, which is typed as elif in python.

~~~python
celsius = input("Enter a temperature in Celsius: ")

fahrenheit = (celsius * 2) + 30
print str(celsius) + " degrees in Celsius is " + str(fahrenheit) + " degrees in Fahrenheit"

if celsius > 20:
    print "That's pretty warm!"
elif celsius < 5:
    print "That is cold!"
else:
    print "That's a bit cool"
~~~

Now, if the user enters a value above 20, we will see "That's pretty warm!"; if the value is between 5 and 20 (inclusive), we will see "That's a bit cool", and if the value entered is below 5, we will see the phrase "That is cold!" printed to the screen. Try modifying your script so that if the value entered is over 30 degrees, the phrase "Wow, that's hot!" is displayed. 

<b>Bonus</b>: Instead of having these phrases printed on a second line, can you instead add them to the first print statement above?

### Working with lists
A common task programming task is performing the same operation repeatedly over a list of data or values. Using our temperature example, we may have a series of temperatures that we need to convert from Celsius to Fahrenheit. While our existing script could work for a small number of values that we manually enter, this approach would be quite laborious for a large dataset containing 100+ temperatures. We are going to write a new script that will take a list of temperatures in Celsius and will convert them into Fahrenheit.

To start, we need to define a list. In python, you do so by naming your list variable and assigning its contents using the equal sign. To the right of the equal sign, you contain the list elements within [ ] brackets and separate each value using a comma. The below example shows a numerical list and a list of strings. Remember, strings must always be contained within single or double quotes.

~~~python
num_list = [15, 18, 12, 22, 34]
str_list = ['cats', 'dogs', 'koalas', 'parrots']

print num_list
print str_list
~~~

As you can see from the output printed to the screen, the entire list is printed when we print out either of these variables. For our purposes, however, we want to manipulate each individual value in a list of temperatures. We can do so by referring to the position or index of each element in our list. One oddity to note about most programming languages, including python, is that the count begins at 0 instead of 1. Thus, in our numbered list, the number 15 is at index (position) 0, 18 is at index 1, 12 is index 2, etc. Similarly, the word "koala" has an index of 2 in our string list.

We reference an individual list element by denoting its position after the list variable's name. The variable with the value of 'dog' is thus written as str_list[1]. Try printing out each individual part of str_list.

~~~python
num_list = [15, 18, 12, 22, 34]
str_list = ['cats', 'dogs', 'koalas', 'parrots']

print str_list[0]
print str_list[1]
print str_list[2]
print str_list[3]
~~~

We can also use variables to refer to the index of a list:

~~~python
num_list = [15, 18, 12, 22, 34]
str_list = ['cats', 'dogs', 'koalas', 'parrots']

a_num = 2

print str_list[a_num]
~~~

The above code will print the word "koalas" as this word is contained in index (position) 2 of our list str_list.

### Working with loops
Now that we're familiar with lists, let's return to the question of how we can process a list of temperatures so they are converted from Celsius to Fahrenheit. Start a new script and define a list of 5 or more temperatures.

~~~python
celsius = [15, 18, 12, 22, 34]
~~~

To process each list member, we need to use a structure called a for loop. As with conditional statements, we start our for loop with the keyword "for", then we define what we want to loop over, followed by a colon. The code we want to execute for each iteration of the loop then follows, indented. We will start by printing out each list member individually.

~~~python
celsius = [15, 18, 12, 22, 34]

for temperature in celsius:
    print temperature
~~~

In this example, the first line of our loop states that we want to loop over the list celsius. The variable "temperature" that appears in this line is a temporary variable that refers to the individual data element of the list, and we are free to call this anything we want. In human language, this line is saying "for each list item (hereafter referred to as temperature) in the list celsius, do the following:". The following line then prints out each list item as it is evaluated.

To complete the temperature conversion, we need to add our conversion formula within the loop. To do so, we add an indented line with the calculation below our for statement. The variable that we are converting is temperature, as this is the variable that refers to each list item in term; celsius refers to the entire list.

~~~python
celsius = [15, 18, 12, 22, 34]

for temperature in celsius:
    fahrenheit = temperature * 2 + 30
    print fahrenheit
~~~

Note that each list item is processed sequentially, not in parallel. In other words, python looks at index 0 in celsius (15), converts it to Fahrenheit based on the calculation we defined, and then prints out the result. It then looks at index 1 (18) and does the same thing and so on until the end of the list. It does NOT convert all values at once and then print them out.

