# RomanToInteger
A simple code for converting Roman letters to Integers using Python.

Convert Roman Numerals With Python
Prerequisites: Python fundamentals
Version: Python 3.10
Read Time: 30 minutes

#Introduction
As the name suggests, Roman numerals originated in ancient Rome more than 2,800 years ago. After the Romans’ eventual demise, numerals were still widely used during the Middle Ages. Even today, Roman numerals are prevalent in our everyday lives, showing up in clocks, movie titles, and more!

Instead of numbers like 1 and 2, Roman numerals use letters (predominantly "I" and "V").

Roman Numeral Chart
Using the chart above, "I" is 1, "V" is 5, "X" is 10, and so on…

However, when a large combination of these values gets thrown together, the value of the numeral becomes difficult to read.

Luckily, a sequence of Roman numerals can be easily converted to numbers with Python!

We will use loops, control flow statements, and built-in Python functions to convert any Roman numeral into a number. Let’s jump in!

# Setup
You'll need an editor for this tutorial. This can be achieved with any of the following:

You can write the code in our built-in Python editor.
You can save and run the code from a separate file_name.py file in an editor of your choice.

# Step 1: Get User Input
To enter a sequence of Roman numerals, we need to ask the user for input. This can be done with the built-in input() function:

numeral_input = input("Enter the roman numerals you want to convert: ")

Here, you are creating a variable called numeral_input and assigning the user's input to it.

# Step 2: Define roman_to_int() Function
Now that we have the user submitting input, let's define a roman_to_int() function to translate the Roman numerals into an integer value:

def roman_to_int(numeral):

In the function definition, we are specifying a numeral parameter that is a string of the Roman numeral we want to convert.

Inside the function, Iet’s loop through each character in the numeral string and convert them to integers!

At the start, we need to create a final_answer integer variable, initialized at 0, for storing our converted integer:

final_answer = 0

The 'final _answer' will be printed at the end of the function.

Next let's create a for loop that repeats a particular block of code for all the characters of the numeral variable (our user input):

for i in numeral:

Now, inside the loop, let’s use if-elif statements to check if our i variable satisfies certain constraints. If they do, we'll add its corresponding integer value to our final_answer variable:

for i in numeral:
  if i == "M":
    final_answer += 1000
  elif i == "D":
    final_answer += 500
  elif i == "C":
    final_answer += 100
  elif i == "L":
    final_answer += 50
  elif i == "X":
    final_answer += 10
  elif i == "V":
    final_answer += 5
  elif i == "I":
    final_answer += 1

Next, when we print the final_answer at the end, we should cast it as a string with the built-in str() function so that it can be printed with the rest of the message:

print("The roman numerals you entered translates to: " + str(final_answer) + "!")

Make sure the print() statement is on the same indentation as the if-elif statements. Otherwise, Python will think you’re trying to put the print() command in an if-elif statement before everything is calculated.

Lastly, outside the roman_to_int() function, let's use the input we prompted the user for so that our converted integer is printed:

roman_to_int(numeral_input)

Let's save the file and run the code! When prompted, type “XX” to test the roman_to_int() function. Your output should say:

“The Roman numerals you entered translate to: 20!”

Next, try “MDC”. You should receive an output relating to the value “1600”. If that is what you got, great! You’re almost done!

# Step 3: Handle Edge Cases
Not all Roman numerals are represented by one letter. For example, the numeral for 4 is "IV" (two letters, "I" and "V"). Same thing with 9, which translates to "IX".

We need to make code that handles these edge cases. Right now, we do not get "IV" when 4 is passed to our romanToInt() function. Instead, we will have an output of 6.

We will place this code before the for loop we made in the last step.

This can be done by the following:

if "CM" in numeral:
  final_answer += 900
  numeral = numeral.replace("CM", "")
if "CD" in numeral:
  final_answer += 400
  numeral = numeral.replace("CD", "")
if "XC" in numeral:
  final_answer += 90
  numeral = numeral.replace("XC", "")
if "XL" in numeral:
  final_answer += 40
  numeral = numeral.replace("XL", "")
if "IX" in numeral:
  final_answer += 9
  numeral = numeral.replace("IX", "")
if "IV" in numeral:
  final_answer += 4
  numeral = numeral.replace("IV", "")

If one of these values is in the numeral string, its corresponding integer value is added to the final_answer variable. Finally, these "nonwhole" Roman numerals with two letters are removed from the numeral variable since they are now calculated. This ensures the code runs smoothly and prints the correct answer.

For example, if you were to input "XLI," the code would see there is an "XL" in the numeral variable. It would add 40 to the final_answer, then remove the "XL" from numeral so the rest of the input is processed in the for loop...

Now that you're done, save your file and test out your program with the following to see if you get the correct integers:

"DXXXI" (531)
"DCCXCII" (792)
"LXXXIV" (84)

# Conclusion
Congratulations! You've successfully programmed a Roman numeral converter! We defined a function that uses loops, control flow statements, and built-in functions to convert a Roman numeral into its equivalent integer value. Additionally, we also included code that handled an edge case where a given Roman numeral was made of two letters, instead of one.

Bonus: Ready for a new challenge with this? Write a new int_to_roman() function that converts an integer into a Roman numeral!
