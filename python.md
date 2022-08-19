
### Error
Two common errors that we encounter while writing Python are SyntaxError and NameError.
SyntaxError means there is something wrong with the way your program is written — punctuation that does not belong, a command where it is not expected, or a missing parenthesis can all trigger a SyntaxError.
A NameError occurs when the Python interpreter sees a word it does not recognize. Code that contains something that looks like a variable but was never defined will throw a NameError.

### Exponents
Python can also perform exponentiation. In written math, you might see an exponent as a superscript number, but typing superscript numbers isn’t always easy on modern keyboards. Since this operation is so related to multiplication, we use the notation **.

```python 
# 2 to the 10th power, or 1024
print(2 ** 10)
 
# 8 squared, or 64
print(8 ** 2)
 
# 9 * 9 * 9, 9 cubed, or 729
print(9 ** 3)
 
# We can even perform fractional exponents
# 4 to the half power, or 2
print(4 ** 0.5)
```
Here, we compute some simple exponents. We calculate 2 to the 10th power, 8 to the 2nd power, 9 to the 3rd power, and 4 to the 0.5th power.

### Concatenation

```python 
birthday_string = "I am "
age = 10
birthday_string_2 = " years old today!"
 
# Concatenating an integer with strings is possible if we turn the integer into a string first
full_birthday_string = birthday_string + str(age) + birthday_string_2
 
# Prints "I am 10 years old today!"
print(full_birthday_string)
 
# If we just want to print an integer 
# we can pass a variable as an argument to 
# print() regardless of whether 
# it is a string.
 
# This also prints "I am 10 years old today!"
print(birthday_string, age, birthday_string_2)
```
Using str() we can convert variables that are not strings to strings and then concatenate them. But we don’t need to convert a number to a string for it to be an argument to a print statement.

### Multi-line Strings
Python strings are very flexible, but if we try to create a string that occupies multiple lines we find ourselves face-to-face with a SyntaxError. Python offers a solution: multi-line strings. By using three quote-marks (""" or ''') instead of one, we tell the program that the string doesn’t end until the next triple-quote. This method is useful if the string being defined contains a lot of quotation marks and we want to be sure we don’t close it prematurely.

```python 
leaves_of_grass = """
Poets to come! orators, singers, musicians to come!
Not to-day is to justify me and answer what I am for,
But you, a new brood, native, athletic, continental, greater than
  before known,
Arouse! for you must justify me.
"""
```
In the above example, we assign a famous poet’s words to a variable. Even though the quote contains multiple linebreaks, the code works!
If a multi-line string isn’t assigned a variable or used in an expression it is treated as a comment.

### Types of Arguments
In Python, there are 3 different types of arguments we can give a function.
Positional arguments: arguments that can be called by their position in the function definition.
Keyword arguments: arguments that can be called by their name.
Default arguments: arguments that are given default values.
Positional Arguments are arguments we have already been using! Their assignments depend on their positions in the function call. Let’s look at a function called calculate_taxi_price() that allows our users to see how much a taxi would cost to their destination 🚕.

```python 
def calculate_taxi_price(miles_to_travel, rate, discount):
  print(miles_to_travel * rate - discount )
In this function, miles_to_travel is positioned as the first parameter, rate is positioned as the second parameter, and discount is the third. When we call our function, the position of the arguments will be mapped to the positions defined in the function declaration.
# 100 is miles_to_travel
# 10 is rate
# 5 is discount
calculate_taxi_price(100, 10, 5)
```
Alternatively, we can use Keyword Arguments where we explicitly refer to what each argument is assigned to in the function call. Notice in the code example below that the arguments do not follow the same order as defined in the function declaration.

```python 
calculate_taxi_price(rate=0.5, discount=10, miles_to_travel=100)
```
Lastly, sometimes we want to give our function arguments default values. We can provide a default value to an argument by using the assignment operator (=). This will happen in the function declaration rather than the function call.
Here is an example where the discount argument in our calculate_taxi_price function will always have a default value of 10:

```python 
def calculate_taxi_price(miles_to_travel, rate, discount = 10):
  print(miles_to_travel * rate - discount )
```
When using a default argument, we can either choose to call the function without providing a value for a discount (and thus our function will use the default value assigned) or overwrite the default argument by providing our own:

```python 
# Using the default value of 10 for discount.
calculate_taxi_price(10, 0.5)
 
# Overwriting the default value of 10 with 20
calculate_taxi_price(10, 0.5, 20)
```
### Multiple Returns
Sometimes we may want to return more than one value from a function. We can return several values by separating them with a comma. Take a look at this example of a function that allows users in our travel application to check the upcoming week’s weather (starting on Monday):

```python 
weather_data = ['Sunny', 'Sunny', 'Cloudy', 'Raining', 'Snowing']
 
def threeday_weather_report(weather):
  first_day = " Tomorrow the weather will be " + weather[0]
  second_day = " The following day it will be " + weather[1]
  third_day = " Two days from now it will be " + weather[2]
  return first_day, second_day, third_day
```
This function takes in a set of data in the form of a list for the upcoming week’s weather. We can get our returned function values by assigning them to variables when we call the function:

```python 
monday, tuesday, wednesday = threeday_weather_report(weather_data)
 
print(monday)
print(tuesday)
print(wednesday)
This will print:
Tomorrow the weather will be Sunny
The following day it will be Sunny
Two days from now it will be Cloudy
```


### BASH
ls to list the contents of the current directory. It may look something like this:$ ls
Applications                Pictures
Codecademy                  Public
Desktop                     Downloads
Documents                   Library

mkdir test to make a new directory named test. Now, when you type ls you should see a folder called test:$ ls
Applications                Pictures
Codecademy                  Public
Desktop                     Downloads
Documents                   Library
test

cd test to navigate into the new directory. You won’t see an output when you do this.
echo "Hello Command Line" >> hello_cli.txt to create a new file named hello_cli.txt and add Hello Command Line to that file. When you type ls, you should see the following:$ ls
hello_cli.txt

cat hello_cli.txt to print the contents of the hello_cli.txt file to the terminal. You should see something like:$ cat hello_cli.txt
Hello Command Line

### Growing a List: Plus (+)
When we want to add multiple items to a list, we can use + to combine two lists (this is also known as concatenation).
Below, we have a list of items sold at a bakery called items_sold:

```python 
items_sold = ["cake", "cookie", "bread"]
```
Suppose the bakery wants to start selling "biscuit" and "tart":

```python 
items_sold_new = items_sold + ["biscuit", "tart"]
print(items_sold_new)
```
Would output:

```python 
['cake', 'cookie', 'bread', 'biscuit', 'tart']
```
In this example, we created a new variable, items_sold_new, which contained both the original items sold, and the new items. We can inspect the original items_sold and see that it did not change:

```python 
print(items_sold)
```
Would output:

```python 
['cake', 'cookie', 'bread']
```
We can only use + with other lists. If we type in this code:

```python 
my_list = [1, 2, 3]
my_list + 4
```
we will get the following error:

```python 
TypeError: can only concatenate list (not "int") to list
```
If we want to add a single element using +, we have to put it into a list with brackets ([]):

```python 
my_list + [4]
```
Let’s use + to practice combining two lists!

When accessing elements of an list, you must use an int as the index. If you use a float, you will get an error. This can be especially tricky when using division. For example print(calls[4/2]) will result in an error, because 4/2 gets evaluated to the float 2.0.
To solve this problem, you can force the result of your division to be an int by using the int() function. int() takes a number and cuts off the decimal point. For example, int(5.9) and int(5.0) will both become 5. Therefore, calls[int(4/2)] will result in the same value as calls[2], whereas calls[4/2] will result in an error.

### Accessing List Elements: Negative Index
What if we want to select the last element of a list?
We can use the index -1 to select the last item of a list, even when we don’t know how many elements are in a list.
Consider the following list with 6 elements:

```python 
pancake_recipe = ["eggs", "flour", "butter", "milk", "sugar", "love"]
```
If we select the -1 index, we get the final element, "love".

```python 
print(pancake_recipe[-1])
```
Would output:
love




This is equivalent to selecting the element with index 5:

```python 
print(pancake_recipe[5])
```
Would output:
love

Here are the negative index numbers for our list:
Element
Index
"eggs"
-6
"flour"
-5
"butter"
-4
"milk"
-3
"sugar"
-2
"love"
-1


```python 
shopping_list = ["eggs", "butter", "milk", "cucumbers", "juice", "cereal"]

last_element = shopping_list[-1] //cereal
index5_element = shopping_list[5] //cereal

print(last_element)
print(index5_element)
```
### Two-Dimensional (2D) Lists
We’ve seen that the items in a list can be numbers or strings. Lists can contain other lists! We will commonly refer to these as two-dimensional (2D) lists.
Once more, let’s look at a class height example:
		Noelle is 61 inches tall
		Ava is 70 inches tall
		Sam is 67 inches tall
		Mia is 64 inches tall

Previously, we saw that we could create a list representing both Noelle’s name and height:

```python 
noelle = ["Noelle", 61]
```
We can put several of these lists into one list, such that each entry in the list represents a student and their height:

```python 
heights = [["Noelle", 61], ["Ava", 70], ["Sam", 67], ["Mia", 64]]
```
We will often find that a two-dimensional list is a very good structure for representing grids such as games like tic-tac-toe.

```python 
#A 2d list with three lists in each of the indices. 
tic_tac_toe = [
            ["X","O","X"], 
            ["O","X","O"], 
            ["O","O","X"]
]

incoming_class = [["Kenny", "American", 9], ["Tanya", "Russian",  9], ["Madison", "Indian", 7]]
print(incoming_class)
#[['Kenny', 'American', 9], ['Tanya', 'Russian', 9], ['Madison', 'Indian', 7]]


incoming_class[2][2] = 8
print(incoming_class)
#[['Kenny', 'American', 9], ['Tanya', 'Russian', 9], ['Madison', 'Indian', 8]]


incoming_class[-3][-3] = "Ken"
print(incoming_class)
#[['Ken', 'American', 9], ['Tanya', 'Russian', 9], ['Madison', 'Indian', 8]]
```
### Combining Lists: The Zip Function
Learn about a popular Python built-in function called zip().
In Python, we have an assortment of built-in functions that allow us to build our programs faster and cleaner. One of those functions is zip().

The zip() function allows us to quickly combine associated data-sets without needing to rely on multi-dimensional lists. While zip() can work with many different scenarios, we are going to explore only a single one in this article.

Let’s use a list of student names and associated heights as our example data set:
		Jenny is 61 inches tall
		Alexus is 70 inches tall
		Sam is 67 inches tall
		Grace is 64 inches tall

Suppose that we already had a list of names and a list of heights:

```python 
names = ["Jenny", "Alexus", "Sam", "Grace"]
heights = [61, 70, 67, 64]
```
If we wanted to create a nested list that paired each name with a height, we could use the built-in function zip().

The zip() function takes two (or more) lists as inputs and returns an object that contains a list of pairs. Each pair contains one element from each of the inputs. This is how we would do it for our names and heights lists:

```python 
names_and_heights = zip(names, heights)
```
If we were to then examine this new variable names_and_heights, we would find it looks a bit strange:

```python 
print(names_and_heights)
```
Would output:
<zip object at 0x7f1631e86b48>

This zip object contains the location of this variable in our computer’s memory. Don’t worry though, it is fairly simple to convert this object into a useable list by using the built-in function list():

```python 
converted_list = list(names_and_heights)
print(converted_list)
```
Outputs:
[('Jenny', 61), ('Alexus', 70), ('Sam', 67), ('Grace', 64)]

Notice two things:
		Our data set has been converted from a zip memory object to an actual list (denoted by [ ])
		Our inner lists don’t use square brackets [ ] around the values. This is because they have been converted into tuples (an immutable type of list).

### List Methods
**.count()**
A list method to count the number of occurrences of an element in a list 

**.insert()**
To insert an element into a specific index of a list
store_line.insert(2, "Vikor")

**.pop()**
To remove an element from a specific index or from the end of a list 

The method can be called without a specific index. Using .pop() without an index will remove whatever the last element of the list is

.pop() is unique in that it will return the value that was removed. If we wanted to know what element was deleted, simply assign a variable to the call of the .pop() method. 

**range()**
A built-in Python function to create a sequence of integers 

**len()**
To get the length of a list 

**.sort()/ sorted()**
To sort a list  

##### Working with Lists
Now that we know how to create and access list data, we can start to explore additional ways of working with lists.
In this lesson, you’ll learn how to:
Add and remove items from a list using a specific index.
Create lists with continuous values.
Get the length of a list.
Select portions of a list (called slicing).
Count the number of times that an element appears in a list.
Sort a list of items.
**Note: **In some of the exercises, we will be using built-in functions in Python. If you haven’t yet explored the concept of a function, it may look a bit new. Below we compare it to the method syntax we learned in the earlier lesson.
Here is a preview:

```python 
# Example syntax for methods
list.method(input)
 
# Example syntax for a built-in function 
builtinfuncion(input)
```
### Range
The function range() takes a single input, and generates numbers starting at 0 and ending at the number **before** the input.
So, if we want the numbers from 0 through 9, we use range(10) because 10 is 1 greater than 9:

```python 
my_range = range(10)
print(my_range)
```
Would output:
range(0, 10)

Notice something different? The range() function is unique in that it creates a range object. It is not a typical list like the ones we have been working with.
In order to use this object as a list, we have to first convert it using another built-in function called list().
The list() function takes in a single input for the object you want to convert.

We use the list() function on our range object like this:

```python 
print(list(my_range))
```
Would output:
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

By default, range() creates a list starting at 0. However, if we call range() with two inputs, we can create a list that starts at a different number.
For example, range(2, 9) would generate numbers starting at 2 and ending at 8 (just before 9):

```python 
my_list = range(2, 9)
print(list(my_list))
```
Would output:
[2, 3, 4, 5, 6, 7, 8]

If we use a third input, we can create a list that “skips” numbers.
For example, range(2, 9, 2) will give us a list where each number is 2 greater than the previous number:

```python 
my_range2 = range(2, 9, 2)
print(list(my_range2))
```
Would output:
[2, 4, 6, 8]

We can skip as many numbers as we want!
For example, we’ll start at 1 and skip in increments of 10 between each number until we get to 100:

```python 
my_range3 = range(1, 100, 10)
print(list(my_range3))
```
Would output:
[1, 11, 21, 31, 41, 51, 61, 71, 81, 91]

Our list stops at 91 because the next number in the sequence would be 101, which is greater than 100 (our stopping point).

### Slicing Lists
In Python, often we want to extract only a portion of a list. Dividing a list in such a manner is referred to as slicing.
Lets assume we have a list of letters:

```python 
letters = ["a", "b", "c", "d", "e", "f", "g"]
```
Suppose we want to select from "b" through "f".

We can do this using the following syntax:** letters[start:end]**, where:
		start is the index of the first element that we want to include in our selection. In this case, we want to start at "b", which has index 1.
		end is the index of one more than the last index that we want to include. The last element we want is "f", which has index 5, so end needs to be 6.

```python 
sliced_list = letters[1:6]
print(sliced_list)
```
Would output:
["b", "c", "d", "e", "f"]

Notice that the element at index 6 (which is "g") is not included in our selection.

Slicing syntax in Python is very flexible. Let’s look at a few more problems we can tackle with slicing.
Take the list fruits as our example:

```python 
fruits = ["apple", "cherry", "pineapple", "orange", "mango"]
```

If we want to select the first n elements of a list, we could use the following code:

**fruits[:n]**

For our fruits list, suppose we wanted to slice the first three elements.
The following code would start slicing from index 0 and up to index 3. Note that the fruit at index 3 (orange) is not included in the results.

```python 
print(fruits[:3])
```
Would output:
['apple', 'cherry', 'pineapple']

We can do something similar when we want to slice the last n elements in a list:

**fruits[-n:]**

For our fruits list, suppose we wanted to slice the last two elements.
This code slices from the element at index -2 up through the last index.

```python 
print(fruits[-2:])
```
Would output:
['orange', 'mango']

Negative indices can also accomplish taking all but n last elements of a list.

**fruits[:-n]**

For our fruits example, suppose we wanted to slice all but the last element from the list.
This example starts counting from the 0 index up to the element at index -1.

```python 
print(fruits[:-1])
```
Would output:
['apple', 'cherry', 'pineapple', 'orange']


### Sorting Lists - sort() e sorted()
Often, we will want to sort a list in either numerical (1, 2, 3, …) or alphabetical (a, b, c, …) order.
We can sort a list using the method **.sort()**.
Suppose that we have a list of names:

```python 
names = ["Xander", "Buffy", "Angel", "Willow", "Giles"]
```
Let’s see what happens when we apply .sort():

```python 
names.sort()
print(names)
```
Would output:
['Angel', 'Buffy', 'Giles', 'Willow', 'Xander']

As we can see, the .sort() method sorted our list of names in alphabetical order.

.sort() also provides us the option to go in reverse. Instead of sorting in ascending order like we just saw, we can do so in descending order.

```python 
names.sort(reverse=True)
print(names)
```
Would output:
['Xander', 'Willow', 'Giles', 'Buffy', 'Angel']

**Note:** The .sort() method does not return any value and thus does not need to be assigned to a variable since it modifies the list directly. If we do assign the result of the method, it would assign the value of None to the variable.

A second way of sorting a list in Python is to use the built-in function **sorted()**.
The sorted() function is different from the .sort() method in two ways:
It comes before a list, instead of after as all built-in functions do.
It generates a new list rather than modifying the one that already exists.
Let’s return to our list of names:

```python 
names = ["Xander", "Buffy", "Angel", "Willow", "Giles"]
```
Using sorted(), we can create a new list, called sorted_names:

```python 
sorted_names = sorted(names)
print(sorted_names)

This yields the list sorted alphabetically:
['Angel', 'Buffy', 'Giles', 'Willow', 'Xander']

Note that using sorted did not change names:

```python 
print(names)
```
Would output:
['Xander', 'Buffy', 'Angel', 'Willow', 'Giles']


### For Loops: Introduction
Now that we can appreciate what loops do for us, let’s start with your first type of loop, a for loop, a type of definite iteration.
In a for loop, we will know in advance how many times the loop will need to iterate because we will be working on a collection with a predefined length. In our examples, we will be using Python lists as our collection of elements.
With for loops, on each iteration, we will be able to perform an action on each element of the collection.
Before we work with any collection, let’s examine the general structure of a for loop:
**for <temporary variable> in <collection>:
  <action>**
Let’s break down each of these components:
		A for keyword indicates the start of a for loop.
		A <temporary variable> that is used to represent the value of the element in the collection the loop is currently on.
		An in keyword separates the temporary variable from the collection used for iteration.
		A <collection> to loop over. In our examples, we will be using a list.
		An <action> to do anything on each iteration of the loop.
Let’s link these concepts back to our ingredients example. This for loop prints each ingredient in ingredients:

```python 
ingredients = ["milk", "sugar", "vanilla extract", "dough", "chocolate"]
 
for ingredient in ingredients:
  print(ingredient)
```
In this example:
		ingredient is the <temporary variable>.
		ingredients is our <collection>.
		print(ingredient) was the <action> performed on every iteration using the temporary variable of ingredient.

This code outputs:
milk
sugar
vanilla extract
dough
chocolate
Some things to note about for loops:

##### Temporary Variables:
A temporary variable’s name is arbitrary and does not need to be defined beforehand. Both of the following code snippets do the exact same thing as our above example:

```python 
for i in ingredients:
		  print(i)
		
for item in ingredients:
		 print(item)
		
```
Programming best practices suggest we make our temporary variables as descriptive as possible. Since each iteration (step) of our loop is accessing an ingredient it makes more sense to call our temporary variable ingredient rather than i or item.

##### Indentation:
Notice that in all of these examples the print statement is indented. Everything at the same level of indentation after the for loop declaration is included in the loop body and is run on every iteration of the loop.
for ingredient in ingredients:
		  # Any code at this level of indentation 
		  # will run on each iteration of the loop
		  print(ingredient)
		

If we ever forget to indent, we’ll get an IndentationError or unexpected behavior.

##### Elegant loops:
Python loves to help us write elegant code so it allows us to write simple for loops in one-line. In order to see the below example as one line, you may need to expand your narrative window. Here is the previous example in a single line:

```python 
for ingredient in ingredients: print(ingredient)
```
**Note:** One-line for loops are useful for simple programs. It is not recommended you write one-line loops for any loop that has to perform multiple complex actions on each iteration. Doing so will hurt the readability of your code and may ultimately lead to buggier code.


### For Loops: Using Range
Often we won’t be iterating through a specific list (or any collection), but rather only want to perform a certain action multiple times.
For example, if we wanted to print out a "Learning Loops!" message six times using a for loop, we would follow this structure:

**for <temporary variable> in <list of length 6>:
  print("Learning Loops!")**

Notice that we need to iterate through a list with a length of six, but we don’t necessarily care what is inside of the list.
To create arbitrary collections of any length, we can pair our for loops with the trusty Python built-in function range().
An example of how the range() function works, this code generates a collection of 6 integer elements from 0 to 5:

```python 
six_steps = range(6)

# six_steps is now a collection with 6 elements:
# 0, 1, 2, 3, 4, 5
```
We can then use the range directly in our for loops as the collection to perform a six-step iteration:

```python 
for temp in range(6):
  print("Learning Loops!")
```
Would output:
Learning Loops!
Learning Loops!
Learning Loops!
Learning Loops!
Learning Loops!
Learning Loops!

Something to note is we are not using temp anywhere inside of the loop body. If we are curious about which loop iteration (step) we are on, we can use temp to track it. Since our range starts at 0, we will add + 1 to our temp to represent how many iterations (steps) our loop takes more accurately.

```python 
for temp in range(6):
  print("Loop is on iteration number " + str(temp + 1))
```
Would output:
Loop is on iteration number 1
Loop is on iteration number 2
Loop is on iteration number 3
Loop is on iteration number 4
Loop is on iteration number 5
Loop is on iteration number 6


### While Loops: Introduction
In Python, for loops are not the only type of loops we can use. Another type of loop is called a while loop and is a form of indefinite iteration.
A while loop performs a set of instructions as long as a given condition is true.
The structure follows this pattern:

**while <conditional statement>:
  <action>**

Let’s examine this example, where we print the integers 0 through 3:

```python 
count = 0
while count <= 3:
  # Loop Body
  print(count)
  count += 1
```
Let’s break the loop down:
		count is initially defined with the value of 0. The conditional statement in the while loop is count <= 3, which is true at the initial iteration of the loop, so the loop body executes.
Inside the loop body, count is printed and then incremented by 1.
		When the first iteration of the loop has finished, Python returns to the top of the loop and checks the conditional again. After the first iteration, count would be equal to 1 so the conditional still evaluates to True and so the loop continues.
		This continues until the count variable becomes 4. At that point, when the conditional is tested it will no longer be True and the loop will stop.

The output would be:
0
1
2
3

Note the following about while loops before we write our own:

##### Indentation:
Notice that in our example the code under the loop declaration is indented. Similar to a for loop, everything at the same level of indentation after the while loop declaration is run on every iteration of the loop while the condition is true.
```python 
while count <= 3:
# Loop Body
		print(count)
		count += 1
		# Any other code at this level of indentation will
		# run on each iteration
```
If we ever forget to indent, we’ll get an IndentationError or unexpected behavior.

##### Elegant loops:
Similar to for loops, Python allows us to write elegant one-line while loops. Here is our previous example in a single line:

```python 
count = 0
while count <= 3: print(count); count += 1
```		

Note: Here we separate each statement with a ; to denote a separate line of code.


### Loop Control: Continue
While the break control statement will come in handy, there are other situations where we don’t want to end the loop entirely. What if we only want to skip the current iteration of the loop?

Let’s take this list of integers as our example:

```python 
big_number_list = [1, 2, -1, 4, -5, 5, 2, -9]
```
What if we want to print out all of the numbers in a list, but only if they are positive integers. We can use another common loop control statement called continue.

```python 
for i in big_number_list:
  if i <= 0:
    continue
  print(i)
```
This would produce the output:
1
2
4
5
2

Notice a few things:
		Similar to when we were using the break control statement, our continue control statement is usually paired with some form of a conditional (if/elif/else).
		When our loop first encountered an element (-1) that met the conditions of the if statement, it checked the code inside the block and saw the continue. When the loop then encounters a continue statement it immediately skips the current iteration and moves onto the next element in the list (4).
		The output of the list only printed positive integers in the list because every time our loop entered the if statement and saw the continue statement it simply moved to the next iteration of the list and thus never reached the print statement.


### Nested Loops
Loops can be nested in Python, as they can with other programming languages. We will find certain situations that require nested loops.
Suppose we are in charge of a science class, that is split into three project teams:

```python 
project_teams = [["Ava", "Samantha", "James"], ["Lucille", "Zed"], ["Edgar", "Gabriel"]]
```
Using a for or while loop can be useful here to get each team:

```python 
for team in project_teams:
  print(team)
```
Would output:
["Ava", "Samantha", "James"]
["Lucille", "Zed"]
["Edgar", "Gabriel"]

But what if we wanted to print each individual student? In this case we would actually need to nest our loops to be able loop through each sub-list. Here is what it would look like:

```python 
# Loop through each sublist
for team in project_teams:
  # Loop elements in each sublist
  for student in team:
    print(student)
```
This would output:
Ava
Samantha
James
Lucille
Zed
Edgar
Gabriel


### List Comprehensions: Introduction
So far we have seen many of the ideas about using loops in our code. Python prides itself on allowing programmers to write clean and elegant code. We have already seen this with Python giving us the ability to write while and for loops in a single line.
In this exercise, we are going to examine another way we can write elegant loops in our programs using list comprehensions.
To start, let’s say we had a list of integers and wanted to create a list where each element is doubled. We could accomplish this using a for loop and a new list called doubled:
```python 
numbers = [2, -1, 79, 33, -45]
doubled = []
 
for number in numbers:
  doubled.append(number * 2)
 
print(doubled)
```
Would output:
[4, -2, 158, 66, -90]

Let’s see how we can use the power of list comprehensions to solve these types of problems in one line. Here is our same problem but now written as a list comprehension:

```python 
numbers = [2, -1, 79, 33, -45]
doubled = [num * 2 for num in numbers]
print(doubled)
```
Let’s break down our example in a more general way:

**new_list = [<expression> for <element> in <collection>]**

In our doubled example, our list comprehension:
		Takes an element in the list numbers
		Assigns that element to a variable called num (our <element>)
		Applies the <expression> on the element stored in num and adds the result to a new list called doubled
		Repeats steps 1-3 for every other element in the numbers list (our <collection>)

Our result would be the same:
[4, -2, 158, 66, -90]

```python 
grades = [90, 88, 62, 76, 74, 89, 48, 57]
scaled_grades = [num + 10 for num in grades]
print(scaled_grades[-1])
 ```
Would print: 
67


### List Comprehensions: Conditionals
List Comprehensions are very flexible. We even can expand our examples to incorporate conditional logic.
Suppose we wanted to double only our negative numbers from our previous numbers list.
We will start by using a for loop and a list only_negative_doubled:
```python 
numbers = [2, -1, 79, 33, -45]
only_negative_doubled = []
 
for num in numbers:
  if num < 0: 
    only_negative_doubled.append(num * 2)
 
print(only_negative_doubled) 
```
Would output:
[-2, -90]

Now, here is what our code would look like using a list comprehension:

```python 
numbers = [2, -1, 79, 33, -45]
negative_doubled = [num * 2 for num in numbers if num < 0]
print(negative_doubled)
```
Would output the same result:
[-2, -90]

In our negative_doubled example, our list comprehension:
		Takes an element in the list numbers.
		Assigns that element to a variable called num.
		Checks if the condition num < 0 is met by the element stored in num. If so, it goes to step 4, otherwise it skips it and goes to the next element in the list.
		Applies the expression num * 2 on the element stored in num and adds the result to a new list called negative_doubled
		Repeats steps 1-3 (and sometimes 4) for every other element in the numbers list.
We can also use If-Else conditions directly in our comprehensions. For example, let’s say we wanted to double every negative number but triple all positive numbers. Here is what our code might look like:

```python 
numbers = [2, -1, 79, 33, -45]
doubled = [num * 2 if num < 0 else num * 3 for num in numbers ]
print(doubled)
```
Would output:
[6, -2, 237, 99, -90]

This is a bit different than our previous comprehension since the conditional if num < 0 else num * 3 comes after the expression num * 2 but before our for keyword.

### Product in sublist
When using list comprehension, sometimes the items in the list that you’re iterating through will be lists themselves! In these cases, you can access multiple items in those sub-lists by using the following syntax:
```python 
original_list = [[1, 2], [3, 4],  [5, 6]]
new_list = [item1 + item2 for (item1, item2) in original_list]
new_list will now contain the sum of each sub-list.

nested_lists = [[4, 8], [15, 16], [23, 42]]
product = [item1 * item2 for (item1, item2) in nested_lists]
```
Would print:
[32, 240, 966]


**A string can be thought of as a list of characters.**
Like any other list, each character in a string has an index. Consider the string:

```python 
favorite_fruit = "blueberry"
```
We can select specific letters from this string using the index. Let’s look at the first letter of the string.

```python 
print(favorite_fruit[1])

# Output: l
```
Whoops, is that the first letter you expected? Notice that the letter at index 1 of "blueberry" isn’t b, it’s l. This is because the indices of a string start at 0. b is located at the zero index and we could select it using:

```python 
print(favorite_fruit[0])

# Output: b
```
It’s important to note that indices of strings must be integers. If we were to try to select a non-integer index we would get a TypeError.
For example:

```python 
print(favorite_fruit[1.5])
```
This would result in:
Traceback (most recent call last):
  File "script.py", line 3, in <module>
    print(favorite_fruit[1.5])
TypeError: string indices must be integers


### Cut Me a Slice of String
Not only can we select a single character from a string, but we can also select entire chunks of characters from a string. We can do this with the following syntax:

**string[first_index:last_index]**

This is called slicing a string. When we slice a string we are creating a brand new string that starts at (and includes) the first_index and ends at (but excludes) the last_index.
Let’s look at some examples of this. Recall our favourite fruit:

```python 
favorite_fruit = "blueberry"
```
Let’s say we wanted a new string that contains the letters be. We could slice favorite_fruit as follows:

```python 
print(favorite_fruit[4:6])
# Output: be
```
Notice how the character at the first index, b, is included, but the character at the last index, r, is excluded. If you look for the indices 4 and 6 in the diagram, you can see how the r is outside that range.
We can also have open-ended selections. If we remove the first index, the slice starts at the beginning of the string and if we remove the second index the slice continues to the end of the string.

```python 
print(favorite_fruit[:4])
# Output: blue
 
print (favorite_fruit[4:])
# Output: berry
```
Again, notice how the b from berry is excluded from the first example and included in the second example.

### More and More String Slicing (How Long is that String?)
Python comes with some built-in functions for working with strings. One of the most commonly used of these functions is len(). len() returns the number of characters in a string:

```python 
favorite_fruit = "blueberry"
 
length = len(favorite_fruit)
 
print(length)

# Output: 9
```
If you are taking the length of a sentence the spaces are counted as well.
```python 
fruit_sentence = "I love blueberries"
 
print(len(fruit_sentence))

# Output: 18
```
len() comes in handy when we are trying to select characters from the end of a string. What is the index of the last character,"y", of favorite_fruit from above? You can try to run the following code:

```python 
last_char = favorite_fruit[len(favorite_fruit)]
 
print(last_char)
```
This will result in:
IndexError: string index out of range

Why does this generate an IndexError? Because the indices start at 0, so the final character in favorite_fruit has an index of 8. len(favorite_fruit) returns 9 and, because there is no value at that index, an IndexError occurs.
Instead, the last character in a string has an index that is len(string_name) - 1.

```python 
last_char = favorite_fruit[len(favorite_fruit)-1]
 
print(last_char)

# Output: y
```
You could also slice the last several characters of a string using len():

```python 
length = len(favorite_fruit)
last_chars = favorite_fruit[length-4:]
print(last_chars)

# Output: erry
```
Using a len() statement as the starting index and omitting the final index lets you slice n characters from the end of a string, where n is the amount you subtract from len().


### Negative Indices
In the previous exercise, we used len() to get a slice of characters at the end of a string.
There’s a much easier way to do this — we can use negative indices! Negative indices count backward from the end of the string, so string_name[-1] is the last character of the string, string_name[-2] is the second last character of the string, etc.
Here are some examples:

```python 
favorite_fruit = 'blueberry'
print(favorite_fruit[-1])
# => 'y'
 
print(favorite_fruit[-2])
# => 'r'
 
print(favorite_fruit[-3:])
# => 'rry'
```
Notice that we are able to slice the last three characters of ‘blueberry’ by having a starting index of -3 and omitting a final index.


### Strings are Immutable
So far in this lesson, we’ve been selecting characters from strings, slicing strings, and concatenating strings. Each time we perform one of these operations we are creating an entirely new string.
This is because strings are immutable. This means that we cannot change a string once it is created. We can use it to create other strings, but we cannot change the string itself.
This property, generally, is known as mutability. Data types that are mutable can be changed, and data types, like strings, that are immutable cannot be changed.

### Escape Characters
Occasionally when working with strings, you’ll find that you want to include characters that already have a special meaning in python. For example let’s say I create the string
 
```python 
favorite_fruit_conversation = "He said, "blueberries are my favorite!""
```
We’ll have accidentally ended the string before we wanted to by including the " character. The way we can do this is by introducing escape characters. By adding a backslash in front of the special character we want to escape, \", we can include it in a string.

```python 
favorite_fruit_conversation = "He said, \"blueberries are my favorite!\""
```
Now it works!


### Strings and Conditionals 
There’s an even easier way than iterating through the entire string to determine if a character is in a string. We can do this type of check more efficiently using in. in checks if one string is part of another string.
Here is what the syntax of in looks like:

**letter in word**

Here, letter in word is a boolean expression that is True if the string letter is in the string word. Here are some examples:

```python 
print("e" in "blueberry")
# => True
print("a" in "blueberry")
# => False
```
In fact, this method is more powerful than the function you wrote in the last exercise because it not only works with letters, but with entire strings as well.

```python 
print("blue" in "blueberry")
# => True
print("blue" in "strawberry")
# => False
```



### Formatting Methods
There are three string methods that can change the casing of a string. These are **.lower()**, **.upper()**, and **.title()**.
.lower() returns the string with all lowercase characters.
.upper() returns the string with all uppercase characters.
.title() returns the string in title case, which means the first letter of each word is capitalized.
Here’s an example of .lower() in action:

```python 
favorite_song = 'SmOoTH'
favorite_song_lowercase = favorite_song.lower()
print(favorite_song_lowercase)

# => 'smooth'
```
Every character was changed to lowercase! It’s important to remember that string methods can only **create** new strings, they do not change the original string.

```python 
print(favorite_song)
# => 'SmOoTH'
```
### Splitting Strings
.upper(), .lower(), and .title() all are performed on an existing string and produce a string in return. Let’s take a look at a string method that returns a different object entirely!

**.split()** is performed on a string, takes one argument, and returns a list of substrings found between the given argument (which in the case of .split() is known as the delimiter). The following syntax should be used:

**string_name.split(delimiter)**

If you do not provide an argument for .split() it will default to splitting at spaces.
For example, consider the following strings:

```python 
man_its_a_hot_one = "Like seven inches from the midday sun"
print(man_its_a_hot_one.split())
# => ['Like', 'seven', 'inches', 'from', 'the', 'midday', 'sun']
```
.split returned a list with each word in the string. Important to note: if we run .split() on a string with no spaces, we will get the same string in return.


### Splitting Strings II
If we provide an argument for .split() we can dictate the character we want our string to be split on. This argument should be provided as a string itself.
Consider the following example:

```python 
greatest_guitarist = "santana"
print(greatest_guitarist.split('n'))
# => ['sa', 'ta', 'a']
```
We provided 'n' as the argument for .split() so our string “santana” got split at each 'n' character into a list of three strings.
What do you think happens if we split the same string at 'a'?

```python 
print(greatest_guitarist.split('a'))
# => ['s', 'nt', 'n', ' ']
```
Notice that there is an unexpected extra '' string in this list. When you split a string on a character that it also ends with, you’ll end up with an empty string at the end of the list.

You can use any string as the argument for .split(), making it a versatile and powerful tool.


### Splitting Strings III
We can also split strings using escape sequences. Escape sequences are used to indicate that we want to split by something in a string that is not necessarily a character. The two escape sequences we will cover here are
		\n Newline
		\t Horizontal Tab
Newline or \n will allow us to split a multi-line string by line breaks and \t will allow us to split a string by tabs. \t is particularly useful when dealing with certain datasets because it is not uncommon for data points to be separated by tabs.
Let’s take a look at an example of splitting by an escape sequence:

```python 
smooth_chorus = \
"""And if you said, "This life ain't good enough."
I would give my world to lift you up
I could change my life to better suit your mood
Because you're so smooth"""
 
chorus_lines = smooth_chorus.split('\n')
 
print(chorus_lines)
```
This code is splitting the multi-line string at the newlines (\n) which exist at the end of each line and saving it to a new list called chorus_lines. Then it prints chorus_lines which will produce the output

['And if you said, "This life ain\'t good enough."', 'I would give my world to lift you up', 'I could change my life to better suit your mood', "Because you're so smooth"]

The new list contains each line of the original string as its own smaller string. Also, notice that Python automatically escaped the ' character in the first line and adjusted to double quotation marks to allow the apostrophe on last line when it created the new list.


### Joining Strings
Now that you’ve learned to break strings apart using .split(), let’s learn to put them back together using .join(). .join() is essentially the opposite of .split(), it joins a list of strings together with a given delimiter. The syntax of .join() is:

**'delimiter'.join(list_you_want_to_join)**

Now this may seem a little weird, because with .split() the argument was the delimiter, but now the argument is the list. This is because join is still a string method, which means it has to act on a string. The string .join() acts on is the delimiter you want to join with, therefore the list you want to join has to be the argument.

This can be a bit confusing, so let’s take a look at an example.

```python 
my_munequita = ['My', 'Spanish', 'Harlem', 'Mona', 'Lisa']
print(' '.join(my_munequita))
# => 'My Spanish Harlem Mona Lisa'
```
We take the list of strings, my_munequita, and we joined it together with our delimiter, ' ', which is a space. The space is important if you are trying to build a sentence from words, otherwise, we would have ended up with:

print(''.join(my_munequita))
# => 'MySpanishHarlemMonaLisa'
```

You can also join using escape sequences as the delimiter. Consider the following example:

```python 
smooth_fifth_verse_lines = ['Well I\'m from the barrio', 'You hear my rhythm on your radio', 'You feel the turning of the world so soft and slow', 'Turning you \'round and \'round']
 
smooth_fifth_verse = '\n'.join(smooth_fifth_verse_lines)
 
print(smooth_fifth_verse)
```
This code is taking the list of strings and joining them using a newline \n as the delimiter. Then it prints the result and produces the output:

Well I'm from the barrio
You hear my rhythm on your radio
You feel the turning of the world so soft and slow
Turning you 'round and 'round


**.strip()**
When working with strings that come from real data, you will often find that the strings aren’t super clean. You’ll find lots of extra whitespace, unnecessary linebreaks, and rogue tabs.
Python provides a great method for cleaning strings: .strip(). Stripping a string removes all whitespace characters from the beginning and end. Consider the following example:

```python 
featuring = "           rob thomas                 "
print(featuring.strip())
# => 'rob thomas'
```
All the whitespace on either side of the string has been stripped, but the whitespace in the middle has been preserved.
You can also use .strip() with a character argument, which will strip that character from either end of the string.

```python 
featuring = "!!!rob thomas       !!!!!"
print(featuring.strip('!'))
# => 'rob thomas       '
```
By including the argument '!' we are able to strip all of the ! characters from either side of the string. Notice that now that we’ve included an argument we are no longer stripping whitespace, we are ONLY stripping the argument.


### Replace
The next string method we will cover is .replace(). Replace takes two arguments and replaces all instances of the first argument in a string with the second argument. The syntax is as follows

**string_name.replace(substring_being_replaced, new_substring)**

Great! Let’s put it in context and look at an example.

```python 
with_spaces = "You got the kind of loving that can be so smooth"
with_underscores = with_spaces.replace(' ', '_')
print(with_underscores)
# 'You_got_the_kind_of_loving_that_can_be_so_smooth'
```
Here we used .replace() to change every instance of a space in the string above to be an underscore instead.
Note that in this example, we used a single character, but these substrings can be multiple characters long!



**.find()**
Another interesting string method is .find(). .find() takes a string as an argument and searching the string it was run on for that string. It then returns the first index value where that string is located.
Here’s an example:

```python 
print('smooth'.find('t'))
# => '4'
```
We searched the string 'smooth' for the string 't' and found that it was at the fourth index spot, so .find() returned 4.
You can also search for larger strings, and .find() will return the index value of the first character of that string.

```python 
print("smooth".find('oo'))
# => '2'
```
Notice here that 2 is the index of the first o.


**.format()**
Python also provides a handy string method for including variables in strings. This method is .format(). .format() takes variables as an argument and includes them in the string that it is run on. You include {} marks as placeholders for where those variables will be imported.

Consider the following function:

```python 
def favorite_song_statement(song, artist):
  return "My favorite song is {} by {}.".format(song, artist)
```
The function favorite_song_statement takes two arguments, song and artist, then returns a string that includes both of the arguments and prints a sentence. Note: .format() can take as many arguments as there are {} in the string it is run on, which in this case is two.

Here’s an example of the function being run:

```python 
print(favorite_song_statement("Smooth", "Santana"))
# => "My favorite song is Smooth by Santana."
```
Now you may be asking yourself, I could have written this function using string concatenation instead of .format(), why is this method better? The answer is legibility and reusability. It is much easier to picture the end result .format() than it is to picture the end result of string concatenation and legibility is everything. You can also reuse the same base string with different variables, allowing you to cut down on unnecessary, hard to interpret code.

**.format() II**
.format() can be made even more legible for other people reading your code by including keywords. Previously, with .format(), you had to make sure that your variables appeared as arguments in the same order that you wanted them to appear in the string, which added unnecessary complications when writing code.
By including keywords in the string, and in the arguments, you can remove that ambiguity. Let’s look at an example.

```python 
def favorite_song_statement(song, artist):
  return "My favorite song is {song} by {artist}.".format(song=song, artist=artist)
```
Now it is clear to anyone reading the string what it is supposed to return, they don’t even need to look at the arguments of .format() in order to get a clear understanding of what is supposed to happen. You can even reverse the order of artist and song in the code above and it will work the same way.

For example, if the arguments of .format() are in a different order, the code will still work since the keywords are present:

```python 
def favorite_song_statement(song, artist):
  # this will have the same output as the above example
  return "My favorite song is {song} by {artist}.".format(artist=artist, song=song)
```

This makes writing AND reading the code much easier.



### Introduction to Dictionary
A dictionary is an unordered set of key: value pairs.
It provides us with a way to map pieces of data to each other so that we can quickly find values that are associated with one another.

Suppose we want to store the prices of various items sold at a cafe:
		Avocado Toast is 6 dollars
		Carrot Juice is 5 dollars
		Blueberry Muffin is 2 dollars

In Python, we can create a dictionary called menu to store this data:

```python 
menu = {"avocado toast": 6, "carrot juice": 5, "blueberry muffin": 2}
```
Notice that:
		A dictionary begins and ends with curly braces { and }.
		Each item consists of a key ("avocado toast") and a value (6).
		Each key: value pair is separated by a comma.
It’s considered good practice to insert a space () after each comma, but our code will still run without the space.


### Make a Dictionary
In the previous exercise, we saw a dictionary that maps strings to numbers (i.e., "avocado toast": 6). However, the keys can be numbers as well.
For example, if we were mapping restaurant bill subtotals to the bill total after tip, a dictionary could look like:

```python 
subtotal_to_total = {20: 24, 10: 12, 5: 6, 15: 18}
```
Values can be of any type. We can use a string, a number, a list, or even another dictionary as the value associated with a key!

For example:

```python 
students_in_classes = {"software design": ["Aaron", "Delila", "Samson"], "cartography": ["Christopher", "Juan", "Marco"], "philosophy": ["Frederica", "Manuel"]}
```
The list ["Aaron", "Delila", "Samson"], which is the value for the key "software design", represents the students in that class.
We can also mix and match key and value types. For example:

```python 
person = {"name": "Shuri", "age": 18, "family": ["T'Chaka", "Ramonda"]}
```

### Invalid Keys
We can have a list or a dictionary as a value of an item in a dictionary, but we cannot use these data types as keys of the dictionary. If we try to, we will get a TypeError.

For example:

```python 
powers = {[1, 2, 4, 8, 16]: 2, [1, 3, 9, 27, 81]: 3}
```
This code will yield:
TypeError: unhashable type: 'list'

The word “unhashable” in this context means that this ‘list’ is an object that can be changed.

Dictionaries in Python rely on each key having a hash value, a specific identifier for the key. If the key can change, that hash value would not be reliable. So the keys must always be unchangeable, hashable data types, like numbers or strings.

### Add A Key
To add a single key: value pair to a dictionary, we can use the syntax:

```python 
dictionary[key] = value
```
For example, if we had our menu dictionary from the first exercise:

```python 
menu = {"oatmeal": 3, "avocado toast": 6, "carrot juice": 5, "blueberry muffin": 2}
```
And we wanted to add a new item, "cheesecake" for 8 dollars, we could use:

```python 
menu["cheesecake"] = 8
```
Now, menu looks like:

```python 
{"oatmeal": 3, "avocado toast": 6, "carrot juice": 5, "blueberry muffin": 2, "cheesecake": 8}
```

### Add Multiple Keys
If we wanted to add multiple key : value pairs to a dictionary at once, we can use the **.update()** method.

Looking at our sensors object from a previous exercise:

```python 
sensors = {"living room": 21, "kitchen": 23, "bedroom": 20}
```
If we wanted to add 3 new rooms, we could use:

```python 
sensors.update({"pantry": 22, "guest room": 25, "patio": 34})
```
This would add all three items to the sensors dictionary.

Now, sensors looks like:

```python 
{"living room": 21, "kitchen": 23, "bedroom": 20, "pantry": 22, "guest room": 25, "patio": 34}
```
### Dict Comprehensions
Let’s say we have two lists that we want to combine into a dictionary, like a list of students and a list of their heights, in inches:

```python 
names = ['Jenny', 'Alexus', 'Sam', 'Grace']
heights = [61, 70, 67, 64]
```
Python allows you to create a dictionary using a dict comprehension, with this syntax:

```python 
students = {key:value for key, value in zip(names, heights)}

#students is now {'Jenny': 61, 'Alexus': 70, 'Sam': 67, 'Grace': 64}
```
Remember that zip() combines two lists into an iterator of tuples with the list elements paired together. This dict comprehension:
Takes a pair from the iterator of tuples
Names the elements in the pair key (the one originally from the names list) and value (the one originally from the heights list)
Creates a key : value item in the students dictionary
Repeats steps 1-3 for the entire iterator of pairs


### Get A Key
Once you have a dictionary, you can access the values in it by providing the key. For example, let’s imagine we have a dictionary that maps buildings to their heights, in metres:

```python 
building_heights = {"Burj Khalifa": 828, "Shanghai Tower": 632, "Abraj Al Bait": 601, "Ping An": 599, "Lotte World Tower": 554.5, "One World Trade": 541.3}
```
Then we can access the data in it like this:

```python 
>>> building_heights["Burj Khalifa"]
828
>>> building_heights["Ping An"]
599
```

### Safely Get a Key
We saw in the last exercise that we had to add a key:value pair to a dictionary in order to avoid a KeyError. This solution is not sustainable. We can’t predict every key a user may call and add all of those placeholder values to our dictionary!

Dictionaries have a **.get()** method to search for a value instead of the my_dict[key] notation we have been using. If the key you are trying to .get() does not exist, it will return None by default:

```python 
building_heights = {"Burj Khalifa": 828, "Shanghai Tower": 632, "Abraj Al Bait": 601, "Ping An": 599, "Lotte World Tower": 554.5, "One World Trade": 541.3}
 
#this line will return 632:
building_heights.get("Shanghai Tower")
 
#this line will return None:
building_heights.get("My House")
```
You can also **specify a value to return if the key doesn’t exist**. For example, we might want to return a building height of 0 if our desired building is not in the dictionary:

```python 
>>> building_heights.get('Shanghai Tower', 0)
632
>>> building_heights.get('Mt Olympus', 0)
0
>>> building_heights.get('Kilimanjaro', 'No Value')
'No Value'
```

### Delete a Key
Sometimes we want to get a key and remove it from the dictionary. Imagine we were running a raffle, and we have this dictionary mapping ticket numbers to prizes:

```python 
raffle = {223842: "Teddy Bear", 872921: "Concert Tickets", 320291: "Gift Basket", 412123: "Necklace", 298787: "Pasta Maker"}
```
When we get a ticket number, we want to return the prize and also remove that pair from the dictionary, since the prize has been given away. We can use **.pop()** to do this. Just like with .get(), we can provide a default value to return if the key does not exist in the dictionary:

```python 
>>> raffle.pop(320291, "No Prize")
"Gift Basket"
>>> raffle
{223842: "Teddy Bear", 872921: "Concert Tickets", 412123: "Necklace", 298787: "Pasta Maker"}

>>> raffle.pop(100000, "No Prize")
"No Prize"
>>> raffle
{223842: "Teddy Bear", 872921: "Concert Tickets", 412123: "Necklace", 298787: "Pasta Maker"}

>>> raffle.pop(872921, "No Prize")
"Concert Tickets"
>>> raffle
{223842: "Teddy Bear", 412123: "Necklace", 298787: "Pasta Maker"}
```
.pop() works to delete items from a dictionary, when you know the key value.


### Get All Keys
Sometimes we want to operate on all of the keys in a dictionary. For example, if we have a dictionary of students in a math class and their grades:

```python 
test_scores = {"Grace":[80, 72, 90], "Jeffrey":[88, 68, 81], "Sylvia":[80, 82, 84], "Pedro":[98, 96, 95], "Martin":[78, 80, 78], "Dina":[64, 60, 75]}
```
We want to get a roster of the students in the class, without including their grades. We can do this with the built-in list() function:

```python 
>>> list(test_scores)
["Grace", "Jeffrey", "Sylvia", "Pedro", "Martin", "Dina"]
```
Dictionaries also have a **.keys()** method that returns a dict_keys object. A dict_keys object is a view object, which provides a look at the current state of the dictionary, without the user being able to modify anything. The dict_keys object returned by .keys() is a set of the keys in the dictionary. You cannot add or remove elements from a dict_keys object, but it can be used in the place of a list for iteration:

```python 
for student in test_scores.keys():
  print(student)
```
will yield:
Grace
Jeffrey
Sylvia
Pedro
Martin
Dina


### Get All Values
Dictionaries have a **.values()** method that returns a dict_values object (just like a dict_keys object but for values!) with all of the values in the dictionary. It can be used in the place of a list for iteration:

```python 
test_scores = {"Grace":[80, 72, 90], "Jeffrey":[88, 68, 81], "Sylvia":[80, 82, 84], "Pedro":[98, 96, 95], "Martin":[78, 80, 78], "Dina":[64, 60, 75]}
 
for score_list in test_scores.values():
  print(score_list)
```
will yield:
[80, 72, 90]
[88, 68, 81]
[80, 82, 84]
[98, 96, 95]
[78, 80, 78]
[64, 60, 75]

There is no built-in function to get all of the values as a list, but if you really want to, you can use:

```python 
list(test_scores.values())
```
However, for most purposes, the dict_values object will act the way you want a list to act.


### Get All Items
You can get both the keys and the values with the **.items()** method. Like .keys() and .values(), it returns a dict_list object. Each element of the dict_list returned by .items() is a tuple consisting of:
(key, value)
so to iterate through, you can use this syntax:

```python 
biggest_brands = {"Apple": 184, "Google": 141.7, "Microsoft": 80, "Coca-Cola": 69.7, "Amazon": 64.8}
 
for company, value in biggest_brands.items():
  print(company + " has a value of " + str(value) + " billion dollars. ")
```
which would yield this output:
Apple has a value of 184 billion dollars.
Google has a value of 141.7 billion dollars.
Microsoft has a value of 80 billion dollars.
Coca-Cola has a value of 69.7 billion dollars.
Amazon has a value of 64.8 billion dollars.

### Dic inside a dic
```python 
medical_records = {'Marina': {'Age': 27, 'Sex': 'Female', 'BMI': 31.1, 'Children': 2, 'Smoker': 'Non-smoker', 'Insurance_cost': 6607.0}, 'Vinay': {'Age': 24, 'Sex': 'Male', 'BMI': 26.9, 'Children': 0, 'Smoker': 'Non-smoker', 'Insurance_cost': 3225.0}, 'Connie': {'Age': 43, 'Sex': 'Female', 'BMI': 25.3, 'Children': 3, 'Smoker': 'Non-smoker', 'Insurance_cost': 8886.0}, 'Isaac': {'Age': 35, 'Sex': 'Male', 'BMI': 20.6, 'Children': 4, 'Smoker': 'Smoker', 'Insurance_cost': 16444.0}, 'Valentina': {'Age': 52, 'Sex': 'Female', 'BMI': 18.7, 'Children': 1, 'Smoker': 'Non-smoker', 'Insurance_cost': 6420.0}}
```
Print one specially:
```python 
print("Connie's insurance cost is " + str(medical_records["Connie"]["Insurance_cost"]) + " dollars.")
```

Each one: 
```python 
for name, record in medical_records.items():
  print(name + " is a " + str(record["Age"]) + \
  " year old " + record["Sex"] + " " + record["Smoker"] \
  + " with a BMI of " + str(record["BMI"]) + \
  " and insurance cost of " + str(record["Insurance_cost"]))
```


### Types
Python equips us with many different ways to store data. A float is a different kind of number from an int, and we store different data in a list than we do in a dict. These are known as different types. We can check the type of a Python variable using the **type()** function.

```python 
a_string = "Cool String"
an_int = 12
 
print(type(a_string))
# prints "<class 'str'>"
 
print(type(an_int))
# prints "<class 'int'>"
```
Above, we defined two variables, and checked the type of these two variables. A variable’s type determines what you can do with it and how you can use it. You can’t .get() something from an integer, just as you can’t add two dictionaries together using +. This is because those operations are defined at the type level.


### Class
A class is a template for a data type. It describes the kinds of information that class will hold and how a programmer will interact with that data. Define a class using the class keyword. PEP 8 Style Guide for Python Code recommends capitalizing the names of classes to make them easier to identify.

```python 
class CoolClass:
  pass
```
In the above example we created a class and named it CoolClass. We used the pass keyword in Python to indicate that the body of the class was intentionally left blank so we don’t cause an IndentationError. We’ll learn about all the things we can put in the body of a class in the next few exercises.


### Instantiation
A class doesn’t accomplish anything simply by being defined. A class must be instantiated. In other words, we must create an instance of the class, in order to breathe life into the schematic.
Instantiating a class looks a lot like calling a function. We would be able to create an instance of our defined CoolClass as follows:

```python 
cool_instance = CoolClass()
```
Above, we created an object by adding parentheses to the name of the class. We then assigned that new instance to the variable cool_instance for safe-keeping so we can access our instance of CoolClass at a later time.


### Object-Oriented Programming
A class instance is also called an object. The pattern of defining classes and creating objects to represent the responsibilities of a program is known as Object Oriented Programming or OOP.
Instantiation takes a class and turns it into an object, the type() function does the opposite of that. When called with an object, it returns the class that the object is an instance of.

```python 
print(type(cool_instance))
# prints "<class '__main__.CoolClass'>"
```
We then print out the type() of cool_instance and it shows us that this object is of type __main__.CoolClass.

In Python __main__ means “this current file that we’re running” and so one could read the output from type() to mean “the class CoolClass that was defined here, in the script you’re currently running.”


### Class Variables
When we want the same data to be available to every instance of a class we use a class variable. A class variable is a variable that’s the same for every instance of the class.
You can define a class variable by including it in the indented part of your class definition, and you can access all of an object’s class variables with object.variable syntax.

```python 
class Musician:
  title = "Rockstar"
 
drummer = Musician()
print(drummer.title)
# prints "Rockstar"
```
Above we defined the class Musician, then instantiated drummer to be an object of type Musician. We then printed out the drummer’s .title attribute, which is a class variable that we defined as the string “Rockstar”.

If we defined another musician, like guitarist = Musician() they would have the same .title attribute.


### Methods
Methods are functions that are defined as part of a class. The first argument in a method is always the object that is calling the method. Convention recommends that we name this first argument self. Methods always have at least this one argument.
We define methods similarly to functions, except that they are indented to be part of the class.

```python 
class Dog:
  dog_time_dilation = 7
 
  def time_explanation(self):
    print("Dogs experience {} years for every 1 human year.".format(self.dog_time_dilation))
 
pipi_pitbull = Dog()
pipi_pitbull.time_explanation()
# Prints "Dogs experience 7 years for every 1 human year."
```
Above we created a Dog class with a time_explanation method that takes one argument, self, which refers to the object calling the function. We created a Dog named pipi_pitbull and called the .time_explanation() method on our new object for Pipi.
Notice we didn’t pass any arguments when we called .time_explanation(), but were able to refer to self in the function body. When you call a method it automatically passes the object calling the method as the first argument.


### Methods with Arguments
Methods can also take more arguments than just self:

```python 
class DistanceConverter:
  kms_in_a_mile = 1.609
  def how_many_kms(self, miles):
    return miles * self.kms_in_a_mile
 
converter = DistanceConverter()
kms_in_5_miles = converter.how_many_kms(5)
print(kms_in_5_miles)
# prints "8.045"
```

Above we defined a DistanceConverter class, instantiated it, and used it to convert 5 miles into kilometres. Notice again that even though how_many_kms takes two arguments in its definition, we only pass miles, because self is implicitly passed (and refers to the object converter).


### Constructors
There are several methods that we can define in a Python class that have special behaviour. These methods are sometimes called “magic,” because they behave differently from regular methods. Another popular term is dunder methods, so-named because they have two underscores (double-underscore abbreviated to “dunder”) on either side of them.

The first dunder method we’re going to use is the **__init__()** method (note the two underscores before and after the word “init”). This method is used to initialize a newly created object. It is called every time the class is instantiated.
Methods that are used to prepare an object being instantiated are called constructors. The word “constructor” is used to describe similar features in other object-oriented programming languages but programmers who refer to a constructor in Python are usually talking about the __init__() method.

```python 
class Shouter:
  def __init__(self):
    print("HELLO?!")
 
shout1 = Shouter()
# prints "HELLO?!"
 
shout2 = Shouter()
# prints "HELLO?!"
```

Above we created a class called Shouter and every time we create an instance of Shouter the program prints out a shout. Don’t worry, this doesn’t hurt the computer at all.
Pay careful attention to the instantiation syntax we use. Shouter() looks a lot like a function call, doesn’t it? If it’s a function, can we pass parameters to it? We absolutely can, and those parameters will be received by the __init__() method.

```python 
class Shouter:
  def __init__(self, phrase):
    # make sure phrase is a string
    if type(phrase) == str:
 
      # then shout it out
      print(phrase.upper())
 
shout1 = Shouter("shout")
# prints "SHOUT"
 
shout2 = Shouter("shout")
# prints "SHOUT"
 
shout3 = Shouter("let it all out")
# prints "LET IT ALL OUT"
```
Above we’ve updated our Shouter class to take the additional parameter phrase. When we created each of our objects we passed an argument to the constructor. The constructor takes the argument phrase and, if it’s a string, prints out the all-caps version of phrase.


### Instance Variables
We’ve learned so far that a class is a schematic for a data type and an object is an instance of a class, but why is there such a strong need to differentiate the two if each object can only have the methods and class variables the class has? This is because each instance of a class can hold different kinds of data.
The data held by an object is referred to as an instance variable. Instance variables aren’t shared by all instances of a class — they are variables that are specific to the object they are attached to.
Let’s say that we have the following class definition:

```python 
class FakeDict:
  pass
```
We can instantiate two different objects from this class, fake_dict1 and fake_dict2, and assign instance variables to these objects using the same attribute notation that was used for accessing class variables.

```python 
fake_dict1 = FakeDict()
fake_dict2 = FakeDict()
 
fake_dict1.fake_key = "This works!"
fake_dict2.fake_key = "This too!"
 
# Let's join the two strings together!
working_string = "{} {}".format(fake_dict1.fake_key, fake_dict2.fake_key)
print(working_string)
# prints "This works! This too!"
```


### Attribute Functions
Instance variables and class variables are both accessed similarly in Python. This is no mistake, they are both considered attributes of an object. If we attempt to access an attribute that is neither a class variable nor an instance variable of the object Python will throw an AttributeError.

```python 
class NoCustomAttributes:
  pass
 
attributeless = NoCustomAttributes()
 
try:
  attributeless.fake_attribute
except AttributeError:
  print("This text gets printed!")
 
# prints "This text gets printed!"
```
What if we aren’t sure if an object has an attribute or not? hasattr() will return True if an object has a given attribute and False otherwise. If we want to get the actual value of the attribute, getattr() is a Python function that will return the value of a given object and attribute. In this function, we can also supply a third argument that will be the default if the object does not have the given attribute.

The syntax and parameters for these functions look like this:
hasattr(object, “attribute”) has two parameters:
object : the object we are testing to see if it has a certain attribute
attribute : name of attribute we want to see if it exists
getattr(object, “attribute”, default) has three parameters (one of which is optional):
object : the object whose attribute we want to evaluate
attribute : name of attribute we want to evaluate
default : the value that is returned if the attribute does not exist (note: this parameter is **optional**)
Calling those functions looks like this:

```python 
hasattr(attributeless, "fake_attribute")
# returns False
 
getattr(attributeless, "other_fake_attribute", 800)
# returns 800, the default value
```
Above we checked if the attributeless object has the attribute fake_attribute. Since it does not, hasattr() returned False. After that, we used getattr to attempt to retrieve other_fake_attribute. Since other_fake_attribute isn’t a real attribute on attributeless, our call to getattr() returned the supplied default value 800, instead of throwing an AttributeError.

```python 
can_we_count_it = [{'s': False}, "sassafrass", 18, ["a", "c", "s", "d", "s"]]

for element in can_we_count_it:
  if hasattr(element, "count"):
    print(str(type(element)) + " has the count attribute!")
  else:
      print(str(type(element)) + " does not have the count attribute :(")
```
Output:
<class 'dict'> does not have the count attribute :(
<class 'str'> has the count attribute!
<class 'int'> does not have the count attribute :(
<class 'list'> has the count attribute!



### Self
Since we can already use dictionaries to store key-value pairs, using objects for that purpose is not really useful. Instance variables are more powerful when you can guarantee a rigidity to the data the object is holding.
This convenience is most apparent when the constructor creates the instance variables, using the arguments passed in to it. If we were creating a search engine, and we wanted to create classes for each separate entry we could return. We’d do that like this:

```python 
class SearchEngineEntry:
  def __init__(self, url):
    self.url = url
 
codecademy = SearchEngineEntry("www.codecademy.com")
wikipedia = SearchEngineEntry("www.wikipedia.org")
 
print(codecademy.url)
# prints "www.codecademy.com"
 
print(wikipedia.url)
# prints "www.wikipedia.org"
```
Since the self keyword refers to the object and not the class being called, we can define a secure method on the SearchEngineEntry class that returns the secure link to an entry.

```python 
class SearchEngineEntry:
  secure_prefix = "https://"
  def __init__(self, url):
    self.url = url
 
  def secure(self):
    return "{prefix}{site}".format(prefix=self.secure_prefix, site=self.url)
 
codecademy = SearchEngineEntry("www.codecademy.com")
wikipedia = SearchEngineEntry("www.wikipedia.org")
 
print(codecademy.secure())
# prints "https://www.codecademy.com"
 
print(wikipedia.secure())
# prints "https://www.wikipedia.org"
```
Above we define our secure() method to take just the one required argument, self. We access both the class variable self.secure_prefix and the instance variable self.url to return a secure URL.
This is the strength of writing object-oriented programs. We can write our classes to structure the data that we need and write methods that will interact with that data in a meaningful way.


### Everything is an Object
Attributes can be added to user-defined objects after instantiation, so it’s possible for an object to have some attributes that are not explicitly defined in an object’s constructor. We can use the dir() function to investigate an object’s attributes at runtime. dir() is short for directory and offers an organised presentation of object attributes.

```python 
class FakeDict:
  pass
 
fake_dict = FakeDict()
fake_dict.attribute = "Cool"
 
dir(fake_dict)
# Prints ['__class__', '__delattr__', '__dict__', '__dir__', '__doc__', '__eq__', '__format__', '__ge__', '__getattribute__', '__gt__', '__hash__', '__init__()', '__init_subclass__', '__le__', '__lt__', '__module__', '__ne__', '__new__', '__reduce__', '__reduce_ex__', '__repr__', '__setattr__', '__sizeof__', '__str__', '__subclasshook__', '__weakref__', 'attribute']
```
That’s certainly a lot more attributes than we defined! Python automatically adds a number of attributes to all objects that get created. These internal attributes are usually indicated by double-underscores. But sure enough, attribute is in that list.
Do you remember being able to use type() on Python’s native data types? This is because they are also objects in Python. Their classes are int, float, str, list, and dict. These Python classes have special syntax for their instantiation, 1, 1.0, "hello", [], and {} specifically. But these instances are still full-blown objects to Python.

```python 
fun_list = [10, "string", {'abc': True}]
 
type(fun_list)
# Prints <class 'list'>
 
dir(fun_list)
# Prints ['__add__', '__class__', [...], 'append', 'clear', 'copy', 'count', 'extend', 'index', 'insert', 'pop', 'remove', 'reverse', 'sort']
```
Above we define a new list. We check it’s type and see that’s an instantiation of class list. We use dir() to explore its attributes, and it gives us a large number of internal Python dunder attributes, but, afterward, we get the usual list methods.


### String Representation
One of the first things we learn as programmers is how to print out information that we need for debugging. Unfortunately, when we print out an object we get a default representation that seems fairly useless.

```python 
class Employee():
  def __init__(self, name):
    self.name = name
 
argus = Employee("Argus Filch")
print(argus)
# prints "<__main__.Employee object at 0x104e88390>"
```
This default string representation gives us some information, like where the class is defined and our computer’s memory address where this object is stored, but is usually not useful information to have when we are trying to debug our code.
We learned about the dunder method __init__(). Now, we will learn another dunder method called __repr__(). This is a method we can use to tell Python what we want the string representation of the class to be. __repr__() can only have one parameter, self, and must return a string.
In our Employee class above, we have an instance variable called name that should be unique enough to be useful when we’re printing out an instance of the Employee class.

```python 
class Employee():
  def __init__(self, name):
    self.name = name
 
  def __repr__(self):
    return self.name
 
argus = Employee("Argus Filch")
print(argus)
# prints "Argus Filch"
```
We implemented the __repr__() method and had it return the .name attribute of the object. When we printed the object out it simply printed the .name of the object! Cool!


### Review
So far we’ve covered what a data type actually is in Python. We explored what the functionality of Python’s built-in types (also referred to as primitives) are. We learned how to create our own data types using the class keyword.
We explored the relationship between a class and an object — we create objects when we instantiate a class, we find the class when we check the type() of an object. We learned the difference between class variables (the same for all objects of a class) and instance variables (unique for each object).
We learned about how to define an object’s functionality with methods. We created multiple objects from the same class, all with similar functionality, but with different internal data. They all had the same methods, but produced different output because they were different instances.
Take a moment to congratulate yourself, object-oriented programming is a complicated concept.


### Modules Python Introduction
In the world of programming, we care a lot about making code reusable. In most cases, we write code so that it can be reusable for ourselves. But sometimes we share code that’s helpful across a broad range of situations.
In this lesson, we’ll explore how to use tools other people have built in Python that are not included automatically for you when you install Python. Python allows us to package code into files or sets of files called modules.
A module is a collection of Python declarations intended broadly to be used as a tool. Modules are also often referred to as “libraries” or “packages” — a package is really a directory that holds a collection of modules.
Usually, to use a module in a file, the basic syntax you need at the top of that file is:

```python 
from module_name import object_name
 ```
Often, a library will include a lot of code that you don’t need that may slow down your program or conflict with existing code. Because of this, it makes sense to only import what you need.
One common library that comes as part of the Python Standard Library is datetime. datetime helps you work with dates and times in Python.
Let’s get started by importing and using the datetime module. In this case, you’ll notice that datetime is both the name of the library and the name of the object that you are importing.


### Modules Python Random
datetime is just the beginning. There are hundreds of Python modules that you can use. Another one of the most commonly used is random which allows you to generate numbers or select items at random.
With random, we’ll be using more than one piece of the module’s functionality, so the import syntax will look like:
import random
We’ll work with two common random functions:
		random.choice() which takes a list as an argument and returns a number from the list
		random.randint() which takes two numbers as arguments and generates a random number between the two numbers you passed in
Let’s take randomness to a whole new level by picking a random number from a list of randomly generated numbers between 1 and 100.


### Modules Python Namespaces
Notice that when we want to invoke the randint() function we call random.randint(). This is default behavior where Python offers a namespace for the module. A namespace isolates the functions, classes, and variables defined in the module from the code in the file doing the importing. Your local namespace, meanwhile, is where your code is run.
Python defaults to naming the namespace after the module being imported, but sometimes this name could be ambiguous or lengthy. Sometimes, the module’s name could also conflict with an object you have defined within your local namespace.
Fortunately, this name can be altered by aliasing using the as keyword:

```python 
import module_name as name_you_pick_for_the_module
```
Aliasing is most often done if the name of the library is long and typing the full name every time you want to use one of its functions is laborious.
You might also occasionally encounter import *. The * is known as a “wildcard” and matches anything and everything. This syntax is considered dangerous because it could pollute our local namespace. Pollution occurs when the same name could apply to two possible things. For example, if you happen to have a function floor() focused on floor tiles, using from math import * would also import a function floor() that rounds down floats.
Let’s combine your knowledge of the random library with another fun library called matplotlib, which allows you to plot your Python code in 2D.
You’ll use a new random function random.sample() that takes a range and a number as its arguments. It will return the specified number of random numbers from that range.

```python 
#random.sample takes a list and randomly selects k items from it
new_list = random.sample(list, k)
#for example:
nums = [1, 2, 3, 4, 5]
sample_nums = random.sample(nums, 3)
print(sample_nums) # 2, 5, 1
```
### Modules Python Decimals
Let’s say you are writing software that handles monetary transactions. If you used Python’s built-in floating-point arithmetic to calculate a sum, it would result in a weirdly formatted number.

```python 
cost_of_gum = 0.10
cost_of_gumdrop = 0.35
 
cost_of_transaction = cost_of_gum + cost_of_gumdrop
# Returns 0.44999999999999996
```
Being familiar with rounding errors in floating-point arithmetic you want to use a data type that performs decimal arithmetic more accurately. You could do the following:
from decimal import Decimal

```python  
cost_of_gum = Decimal('0.10')
cost_of_gumdrop = Decimal('0.35')
 
cost_of_transaction = cost_of_gum + cost_of_gumdrop
# Returns 0.45 instead of 0.44999999999999996
```
Above, we use the decimal module’s Decimal data type to add 0.10 with 0.35. Since we used the Decimal type the arithmetic acts much more as expected.
Usually, modules will provide functions or data types that we can then use to solve a general problem, allowing us more time to focus on the software that we are building to solve a more specific problem.
Ready, set, fix some floating point math by using decimals!


### Modules Python Files and Scope
You may remember the concept of scope from when you were learning about functions in Python. If a variable is defined inside of a function, it will not be accessible outside of the function.
Scope also applies to classes and to the files you are working within.
Files have scope? You may be wondering.
Yes. Even files inside the same directory do not have access to each other’s variables, functions, classes, or any other code. So if I have a file **sandwiches.py** and another file **hungry_people.py**, how do I give my hungry people access to all the sandwiches I defined?
Well, files are actually modules, so you can give a file access to another file’s content using that glorious import statement.
With a single line of from sandwiches import sandwiches at the top of **hungry_people.py**, the hungry people will have all the sandwiches they could ever want.

### Exploring Data with SQL 
Like most organizations, Codecademy uses SQL (Structured Query Language)  to access its database. 
A database is a set of data stored in a computer. This data is usually structured  into tables. Tables can grow large and have a multitude of columns and records. Spreadsheets, like Microsoft Excel and Google Sheets, allow you to view and  manipulate data directly: with selecting, filtering, sorting, etc. By applying a  number of these operations you can obtain the subset of data you are seeking. SQL (pronounced “S-Q-L” or “sequel”) allows you to write queries which define  the subset of data you are seeking. Unlike Excel and Sheets, your computer and  SQL will handle how to get the data; you can focus on what data you would like.  You can save these queries, refine them, share them, and run them on different  databases. 
It is a great way to access data and a great entry point to programming  because its syntax (the specific vocabulary that gives instructions to the  computer) is very human-readable. Without knowing any SQL, you might still be  able to guess what each command will do. 
On her first day at Codecademy, Catherine wants to become familiar with the  company’s data, so she connects to the database and uses SQL to explore the  database. 
Next, Catherine wants to take a look at the churn rate. 
Churn rate is the percent of subscribers to a monthly service who have  canceled. For example, in January, let’s say Codecademy had 1,000 learners. In  February, 200 learners sign up, and 250 cancel. 
The churn rate for February would be: 

Catherine wants to analyze the churn rates for Codecademy for the past few  months so she writes another SQL query. 

```
SELECT COUNT(DISTINCT user_id) AS 'enrollments', 
 COUNT(CASE 
 WHEN strftime("%m", cancel_date) = '03' 
 THEN user_id 
 END) AS 'march_cancellations', 
 ROUND(100.0 * COUNT(CASE 
 WHEN strftime("%m", cancel_date) = '03' 
 THEN user_id 
 END) / COUNT(DISTINCT user_id)) AS 'churn_rate' 
FROM pro_users 
WHERE signup_date < '2017-04-01'
 AND ( 
 (cancel_date IS NULL) OR 
 (cancel_date > '2017-03-01') 
 ); 
```
### Time for Python! 
After interacting with the database, it is time to analyze the data further and  eventually visualize the data. And SQL cannot get us there. 
Python is a general-purpose programming language. It can do almost all of  what other languages can do with comparable, or faster, speed. It is often  chosen by Data Analysts and Data Scientists for prototyping, visualization, and  execution of data analyses on datasets. 
There’s an important question here. Plenty of other programming languages,  like R, can be useful in the field of data science. Why are so many people  choosing Python? 
One major factor is Python’s versatility. There are over 125,000 third-party  Python libraries. These libraries make Python more useful for specific  purposes, from the traditional (e.g. web development, text processing) to the  cutting edge (e.g. AI and machine learning). For example, a biologist might use  the Biopython library to aid their work in genetic sequencing. Additionally, Python has become a go-to language for data analysis. With data focused libraries like pandas, NumPy, and Matplotlib, anyone familiar with  Python’s syntax and rules can use it as a powerful tool to process, manipulate,  and visualize data. 
### Analyzing Data with Pandas 
Catherine wants to know if Codecademy learners are finding what they need.  She needs to analyze data from a survey that was administered to a subset of  visitors. 
Catherine selects the survey data from the SQL database and downloads it  onto her computer. She saves the data as a CSV file (extension .csv), which  stands for Comma-Separated Values. CSV is a text-only spreadsheet format  that lets us store and explore data. 
To analyze the survey data, Catherine will use pandas. Python is a  programming language, and pandas is a special set of commands in Python  that lets us analyze spreadsheet data. Pandas can do a lot of the things that  SQL can do, but it’s also backed by the power of Python, so we can easily  transition from analyzing our data with pandas to visualizing it using other  Python tools. 
### Visualizing Data with Matplotlib and Seaborn 
Catherine wants to visualize her analysis and share it with her boss. For this,  she will use Matplotlib, another Python module. 
Matplotlib lets Catherine create line charts, bar charts, pie charts, and more. It  gives her precise control over colors and labels so that she can create the  perfect chart to communicate her findings. 
Catherine has written some code using Matplotlib that visualizes hours of 
usage on Codecademy! 
### Welcome to Data Literacy 
Welcome to this course on data literacy! First things first, let’s answer a crucial  question: Why is data literacy important? In other words, why should anyone  aim to be data literate? 
There are a lot of good answers! In this lesson, we’ll see how data literacy  helped 19th-century doctors end cholera epidemics and discover the root  cause of the disease. We’ll explore how it has helped reveal discrimination in  hard-to-measure settings like hiring practices, and advance medical knowledge  by improving clinical trial data quality. 
Data literacy also helps us to produce readable work for other people. As we’ll  see, even when good data is there, the inability to tell a clear story can have  dire consequences. 
It’s no secret that data is an incredibly powerful tool. With all that at stake, it’s  also not a surprise that understanding a data-driven conclusion can feel  overwhelming sometimes – both as an audience member and as an analyst. No  matter which side we find ourselves on, data literacy is about how well we read,  interpret, and communicate with data. 
Let’s dive in with some case studies about data literacy triumphs and failures. 
### Data Gaps 
Garbage in, garbage out is a data-world phrase that means “our data-driven  conclusions are only as strong, robust, and well-supported as the data behind  them.” 
For example: we have a lot of data on heart attacks, but there’s room for  improvement when it comes to data quality. Heart disease is the leading cause  of death in women, but as of 2021, women account for only 38% of participants  in relevant research studies. 
There are key differences between men’s and women’s heart attacks that  impact how they’re treated, but our data doesn’t yet adequately outline those  differences. This leads ultimately to worse outcomes in treatment and a higher  post-heart attack mortality rate for women. 
How does data literacy factor in? Part of understanding and communicating  with data means asking the right questions so that we end up with useful,  relevant data. We can already answer lots of questions about heart attacks,  but we won’t learn the ins and outs of women’s heart attacks by studying  mostly men. 
Part of practicing good data literacy means asking… 
Do we have sufficient data to answer the question at hand? 
 Can my data answer my exact question? 
### Addressing Bias 
One question the data on heart attacks might prompt is “why did the trials have  only 38% female participation?” 
In part, for historical reasons: in the 1950s, pregnant women in Europe and  Canada were prescribed a drug called thalidomide for morning sickness. This 
drug resulted in severe birth defects and was taken off the market. As a result,  in 1977 the US Food and Drug Administration (FDA) recommended excluding  from early-stage clinical trials all women who could become pregnant. While  intended to protect women, the recommendation put them at risk in a different  way, limiting our knowledge of the effects of drugs on women’s bodies. The FDA reversed these recommendations in the 1990s, and today  government-funded clinical trials must include women and other minorities.  Yet, the trials don’t need to include minority groups at representative levels,  and the majority of drug trials in the US aren’t government-funded anyway. In this case, participation might also be impacted by media representations. In  typical TV or movie heart attacks, we almost always see a man clutching at his  arm or chest. Not only do women have heart attacks too (we wouldn’t know it  from watching TV), they rarely experience chest pain as a symptom. (In fact, in the top 20 “heart attack” movies* on IMDB, only two heart attacks  happen to women: one is fake, and the other is a disguised murder. So… zero  real heart attacks in women in a list of top 20 “heart attack” movies!) It might seem like a stretch from data literacy to TV heart attacks, but sound  science means examining bias and controlling variables wherever possible. Part of practicing good data literacy means asking… 

● Who participated in the data? 
● Who is left out? 
● Who made the data? 
*top movies with keyword “heart attack” where there is actually a heart attack  mentioned or shown in the movie – not The Exorcist, which is on that list  because people have had heart attacks while watching it… yikes! 
### Variable Types 
In our tree census, we are collecting data about two types of variables: one that  we measure (height) and one that we categorize (species). 
The difference between measuring and categorizing is so important that the  data itself is termed differently: 
● Variables that are measured are Numerical variables 
 ● Variables that are categorized are Categorical variables.
### Numerical variables 
Numerical variables are a combination of the measurement and the unit.  Without the unit, a numerical variable is just a number. 
Imagine I go into a cafe and ask the barista for 3. Three what???? Or  my friend asks how far Toledo is and I say 300. 300 miles? Kilometers? Minutes? Without units, numbers don’t mean anything. 
There are two ways to get a number: by counting and measuring. Counting  gives us whole numbers and discrete variables. Measuring gives us potentially  partial values and continuous variables. 
In our tree census, we are measuring the height of our trees in feet (indicated in  the variable name, ‘Height (ft)’), a continuous variable.

### Categorical variables 
Categorical variables describe characteristics with words or relative values. In the tree census, trees species are described with words like London Plane,  Honeylocust, or Pin Oak. This is the best description and encodes all the  information we need about the species. This kind of categorical variable is  a nominal variable which literally means a named value. 
We also captured whether or not our trees grew alone. In our ‘Single’ variable,  there were only two options: Yes and No. This is called a dichotomous  variable. Dichotomous variables have only 2 logical possibilities, “on/off”, “yes/ no”, “true/false”, “0/1”, there’s no middle ground and no 3rd option. If there is a  logical third option, it’s not a dichotomous variable. 
Finally, let’s say that we wanted to capture how “pretty” we thought each tree  was. This isn’t really a thing we can measure, but we can subjectively say on a  scale of 1 to 5, how pretty we think each tree is. The prettiest trees are a 5, the  least pretty trees are a 1. 
That ranking is inherently ordered and therefore called an ordinal variable. Ordinal variables are really popular in survey design “on a scale of 1-5 how  much do you agree with this statement?” This is called a likert scale. They also  show up in the Olympics and other competitions where someone wins 1st, 2nd,  or 3rd place. 
Ordinal variables can get a little confusing because they are often represented  as numbers. But they don’t represent measurements or counts, they represent  categories. For example, let’s say an Olympian wins Gold and Bronze medals, it  doesn’t make sense to say that they averaged Silver. The same is true of likert  scales: there’s no average between “Very pretty” and “Pretty.” 
SQL is a programming language designed to manipulate and manage data  stored in relational databases. 

● A relational database is a database that organizes information into one or more tables. 
● A table is a collection of data organized into rows and  columns. 
● Constraints add information about how a column can be used. 
● A statement is a string of characters that the database recognizes as a valid  command. 
- CREATE TABLE creates a new table. 
- INSERT INTO adds a new row to a table. 
- SELECT queries data from a table. 
- ALTER TABLE changes an existing table. 
- UPDATE edits a row in a table. 
- DELETE FROM deletes rows from a table. 


### Case 
A CASE statement allows us to create different outputs (usually in 
the SELECT statement). It is SQL’s way of handling if-then logic. Suppose we want to condense the ratings in movies to three levels: 
- If the rating is above 8, then it is Fantastic. 
- If the rating is above 6, then it is Poorly Received. 
- Else, Avoid at All Costs. 

```
SELECT name, 
 CASE 
  WHEN imdb_rating > 8 THEN 'Fantastic'   WHEN imdb_rating > 6 THEN 'Poorly Received'   ELSE 'Avoid at All Costs' 
 END 
FROM movies; 
```
●  Each WHEN tests a condition and the following THEN gives  us the string if the condition is true. 
● The ELSE gives us the string if all the above conditions are  false. 
●  The CASE statement must end with END. 

In the result, you have to scroll right because the column name is very long. To  shorten it, we can rename the column to ‘Review’ using AS: 

```
SELECT name, 
 CASE 
  WHEN imdb_rating > 8 THEN 'Fantastic' 
  WHEN imdb_rating > 6 THEN 'Poorly Received' 
  ELSE 'Avoid at All Costs' 
 END AS 'Review' 
FROM movies; 
```
### AND Operator 
The AND operator allows multiple conditions to be combined. Records must  match both conditions that are joined by AND to be included in the result set.  The given query will match any car that is blue and made after 2014. 
```
SELECT model  
FROM cars  
WHERE color = 'blue'  
  AND year > 2014; 
```
### AS Clause 
Columns or tables can be aliased using the AS clause. This allows columns or  tables to be specifically renamed in the returned result set. The given query will  return a result set with the column for name renamed to movie_title. 
```
SELECT name AS 'movie_title' 
FROM movies;
``` 
### OR Operator 
The OR operator allows multiple conditions to be combined. Records matching  either condition joined by the OR are included in the result set. The given query will match customers whose state is either 'CA' or 'NY'. 

```
SELECT name 
FROM customers  
WHERE state = 'CA'  
   OR state = 'NY'; 
```
### % Wildcard 
The % wildcard can be used in a LIKE operator pattern to match zero or more  unspecified character(s). The given query will match any movie that begins  with The, followed by zero or more of any characters. 
```
SELECT name 
FROM movies 
WHERE name LIKE 'The%'; 
```
### SELECT Statement 
The SELECT * statement returns all columns from the provided table in the  result set. The given query will fetch all columns and records (rows) from  the movies table. 
```
SELECT * 
FROM movies; 
```
### _ Wildcard 
The _ wildcard can be used in a LIKE operator pattern to match any single  unspecified character. The given query will match any movie which begins with  a single character, followed by ove. 
```
SELECT name 
FROM movies 
WHERE name LIKE '_ove'; 
```
### ORDER BY Clause 
The ORDER BY clause can be used to sort the result set by a particular column  either alphabetically or numerically. It can be ordered in two ways: 
● DESC is a keyword used to sort the results in descending  order. 
● ASC is a keyword used to sort the results in ascending order (default). 
```
SELECT * 
FROM contacts 
ORDER BY birth_date DESC; 
```
### LIKE Operator 
The LIKE operator can be used inside of a WHERE clause to match a specified  pattern. The given query will match any movie that begins with Star in its title. 
```
SELECT name 
FROM movies
WHERE name LIKE 'Star%'; 
```
### DISTINCT Clause 
Unique values of a column can be selected using a DISTINCT query. For a  table contact_details having five rows in which the city column contains  Chicago, Madison, Boston, Madison, and Denver, the given query would return: 

Chicago Madison Boston Denver 

```
SELECT DISTINCT city 
FROM contact_details; 
```
### BETWEEN Operator 
The BETWEEN operator can be used to filter by a range of values. The range of  values can be text, numbers, or date data. The given query will match any  movie made between the years 1980 and 1990, inclusive. 
```
SELECT * 
FROM movies 
WHERE year BETWEEN 1980 AND 1990; 
```
### LIMIT Clause 
The LIMIT clause is used to narrow, or limit, a result set to the specified number  of rows. The given query will limit the result set to 5 rows. 
```
SELECT * 
FROM movies 
LIMIT 5; 
```
### NULL Values 
Column values can be NULL, or have no value. These records can be matched  (or not matched) using the IS NULL and IS NOT NULL operators in combination  with the WHERE clause. The given query will match all addresses where the  address has a value or is not NULL. 
```
SELECT address 
FROM records 
WHERE address IS NOT NULL; 
```
### WHERE Clause 
The WHERE clause is used to filter records (rows) that match a certain  condition. The given query will select all records where  
the pub_year equals 2017. 
```
SELECT title 
FROM library 
WHERE pub_year = 2017;
```

### AGGREGATE FUNCTIONS 
Introduction 
We’ve learned how to write queries to retrieve information from the database.  Now, we are going to learn how to perform calculations using SQL. Calculations performed on multiple rows of a table are called aggregates. In this lesson, we have given you a table named fake_apps which is made up of  fake mobile applications data. 
Here is a quick preview of some important aggregates that we will cover in the  next five exercises: 
- COUNT(): count the number of rows 
- SUM(): the sum of the values in a column 
- MAX()/MIN(): the largest/smallest value 
- AVG(): the average of the values in a column 
- ROUND(): round the values in the column 

### Column References 
The GROUP BY and ORDER BY clauses can reference the selected columns by  number in which they appear in the SELECT statement. The example query will  count the number of movies per rating, and will: 
GROUP BY column 2 (rating) 
ORDER BY column 1 (total_movies) 
```
SELECT COUNT(*) AS 'total_movies',  
   rating  
FROM movies  
GROUP BY 2  
ORDER BY 1; 
```

### SUM() Aggregate Function 
The SUM() aggregate function takes the name of a column as an argument and  returns the sum of all the value in that column. 
```
SELECT SUM(salary) 
FROM salary_disbursement; 
```

### MAX() Aggregate Function 
The MAX() aggregate function takes the name of a column as an argument and  returns the largest value in a column. The given query will return the largest  value from the amount column. 
```
SELECT MAX(amount)  
FROM transactions; 
```
### COUNT() Aggregate Function 
The COUNT() aggregate function returns the total number of rows that match  the specified criteria. For instance, to find the total number of employees who  have less than 5 years of experience, the given query can be used. Note: A column name of the table can also be used instead of *.  Unlike COUNT(*), this variation COUNT(column) will not count NULL values in  that column.
```
SELECT COUNT(*) 
FROM employees 
WHERE experience < 5; 
```
### GROUP BY Clause 
The GROUP BY clause will group records in a result set by identical values in  one or more columns. It is often used in combination with aggregate functions  to query information of similar records. The GROUP BY clause can come  after FROM or WHERE but must come before any ORDER BY or LIMIT clause. The given query will count the number of movies per rating. 
```
SELECT rating,  
   COUNT(*)  
FROM movies  
GROUP BY rating; 
```
### MIN() Aggregate Function 
The MIN() aggregate function returns the smallest value in a column. For  instance, to find the smallest value of the amount column from the table  named transactions, the given query can be used. 

```
SELECT MIN(amount)  
FROM transactions; 
```
### AVG() Aggregate Function 
The AVG() aggregate function returns the average value in a column. For  instance, to find the average salary for the employees who have less than 5  years of experience, the given query can be used. 
```
SELECT AVG(salary) 
FROM employees 
WHERE experience < 5; 
```
### HAVING Clause 
The HAVING clause is used to further filter the result set groups provided by  the GROUP BY clause. HAVING is often used with aggregate functions to filter  the result set groups based on an aggregate property. The given query will  select only the records (rows) from only years where more than 5 movies were  released per year. 
The HAVING clause must always come after a GROUP BY clause but must come  before any ORDER BY or LIMIT clause. 
```
SELECT year,  
   COUNT(*)  
FROM movies  
GROUP BY year 
HAVING COUNT(*) > 5; 
```
### Aggregate Functions 
Aggregate functions perform a calculation on a set of values and return a single  value: 
- COUNT() 
- SUM() 
- MAX() 
- MIN()
- AVG() 

### ROUND() Function 
The ROUND() function will round a number value to a specified number of  places. It takes two arguments: a number, and a number of decimal places. It  can be combined with other aggregate functions, as shown in the given query.  This query will calculate the average rating of movies from 2015, rounding to 2  decimal places. 
```
SELECT year,  
   ROUND(AVG(rating), 2)  
FROM movies  
WHERE year = 2015; 
```
### Multiple Tables 
##### Outer Join 
An outer join will combine rows from different tables even if the join condition is  not met. In a LEFT JOIN, every row in the left table is returned in the result set,  and if the join condition is not met, then NULL values are used to fill in the  columns from the right table. 
```
SELECT column_name(s) 
FROM table1 
LEFT JOIN table2 
  ON table1.column_name = table2.column_name; 
```
##### WITH Clause 
The WITH clause stores the result of a query in a temporary table  (temporary_movies) using an alias. 
Multiple temporary tables can be defined with one instance of  the WITH keyword. 
```
WITH temporary_movies AS ( 
   SELECT * 
   FROM movies 
) 
SELECT * 
FROM temporary_movies 
WHERE year BETWEEN 2000 AND 2020; 
```

##### UNION Clause 
The UNION clause is used to combine results that appear from  multiple SELECT statements and filter duplicates. 
For example, given a first_names table with a column name containing rows of  data “James” and “Hermione”, and a last_names table with a  column name containing rows of data “James”, “Hermione” and “Cassidy”, the  result of this query would contain three names: “Cassidy”, “James”, and  “Hermione”. 
```
SELECT name 
FROM first_names 
UNION
SELECT name 
FROM last_names 
```
##### CROSS JOIN Clause 
The CROSS JOIN clause is used to combine each row from one table with each  row from another in the result set. This JOIN is helpful for creating all possible  combinations for the records (rows) in two tables. 
The given query will select the shirt_color and pants_color columns from the  result set, which will contain all combinations of combining the rows in  the shirts and pants tables. If there are 3 different shirt colors in the shirts table  and 5 different pants colors in the pants table then the result set will contain 3  x 5 = 15 rows. 
```
SELECT shirts.shirt_color, 
   pants.pants_color 
FROM shirts 
CROSS JOIN pants; 
```
### Foreign Key 
A foreign key is a reference in one table’s records to the primary key of another  table. To maintain multiple records for a specific row, the use of foreign key  plays a vital role. For instance, to track all the orders of a specific customer, the  table order (illustrated at the bottom of the image) can contain a foreign key. 
### Primary Key 
A primary key column in a SQL table is used to uniquely identify each record in  that table. A primary key cannot be NULL. In the example, customer_id is the  primary key. The same value cannot re-occur in a primary key column. Primary 
keys are often used in JOIN operations. 

### Inner Join 
The JOIN clause allows for the return of results from more than one table by  joining them together with other results based on common column values  specified using an ON clause. INNER JOIN is the default JOIN and it will only  return results matching the condition specified by ON. 
```
SELECT * 
FROM books 
JOIN authors 
  ON books.author_id = authors.id; 
```
### Making API request in Python 
Now that you have a pretty good idea of how the Census Data API works, let’s  take a look at how to pull the data in Python. Begin by importing  the requests library with this command: 
import requests 
Next, we can use the get() method to return the data from our desired URL: 
```
r = requests.get('https://api.census.gov/data/2020/acs/ acs5?get=NAME,B08303_001E&for=state:*')  
```
The result is a response object (just like in the last exercise), but this time we  stored it in a variable named r. 
We can look at that response data by using the .text attribute. The text attribute  turns the data into a string. 
We can also use the .json() method that can automatically decode JSON data  into the appropriate Python object. This is useful when working with JSON  data, as in the case of the Census API, to have the data in a more intuitive data  structure. 
```
# Access data as JSON string 
print(r.text) 
# Access decoded JSON data as Python object
print(r.json()) 
```
### Converting JSON to CSV 
If you haven’t written Python before, you can still do this exercise even though  it might feel a little like magic. Follow along and it will become clearer later on  (we promise it isn’t magic!). 
While JSON is a great universal format for data interchange, it might not be the  ideal format in other aspects, such as readability. Instead, having the data in a  tabular format (like a CSV) can make it much more human-readable and  accessible. Therefore, being able to convert between file types is essential. There are several libraries in Python to work with different data formats. For  example, to convert the Census data from JSON to CSV, we can use the built in csv library: 

```
import csv 
```
As a refresher, visit https://api.census.gov/data/2020/acs/acs5? get=NAME,B08303_001E&for=state:* in your browser to view the total  commuters count for all states. 
The JSON data we got from the Census API is a list of lists in Python, where  each inner list corresponds to a single row of data. To convert from JSON to  CSV, we want to write each sublist as a comma-separated row of data to file.  This bit of code is a little complicated. We will use the writerows() method from  the csv library: 
```
with open('census.csv', mode='w', newline='') as file: writer = csv.writer(file) 
writer.writerows(r.json()) 
```
##### What is that code doing? 
We first make a variable and call it file. Then we use open() to open a file, since  we are going to write that file, we open it with mode='w' for writing mode.  The newline='' ensures that newlines are always interpreted correctly. Next, we use the writer() function from the csv library to make a writer object  (don’t worry about what this is right now). We then use the writerows() method  to write each row of data into comma-separated format. 
### Exploring data using pandas 
Now that we have our data saved into an easy-to-work-with format, let’s  investigate it. 
We’ll use Python’s pandas library, which is designed for working with data (and  will quickly become familiar to you). Start by importing the library and using  the read_csv() function to read the CSV data into a DataFrame object:
import pandas 
```
census_df = pandas.read_csv("census.csv") 
```
By default, the first row of the CSV file is read in as the header row. We can use  the .head() method to preview the first few rows of the DataFrame. Sometimes columns have ambiguous or confusing names (like Census codes).  We might also want to rename those columns. We can use  
the .columns attribute to rename the column headings if needed: 
```
# Preview DataFrame 
print(census_df.head()) 
# Rename DataFrame columns 
census_df.columns = ['name', 'total_commuters', 'state'] 
```
The pandas library offers a lot more functionality for exploring and manipulating  tabular data, but that is out of scope for this lesson. You can learn more in  our Learn Data Analysis with Pandas course. 
### Simulating binomial distribution 
Sometimes you want to simulate a lot of different scenarios. It would be very  expensive to run thousands of tests, but it’s very cheap to generate thousands  of results. 
In this exercise, we are going to simulate binomial data. Binomial distributions  are very useful for modeling different types of data, from drug treatment  effectiveness to stock price trends. 
Binomial events always have 2 possible outcomes, which we refer to  as success and failure. The probability of a successful outcome is represented  by the parameter p. For example, for the event of a coin toss using a fair  coin, p would be 0.5. 
There are lots of ways to do this. We could flip a coin a bunch of times and  write down the results or we could use the random.binomial() method from  the numpy library in Python. 
To use the random.binomial() method, we have to tell it how many trials we  want to simulate (n) and the probability of ‘success’ in a single trial (p), and  how many experiments to run. 
In the example below, there were 1 flip per trial (n), the probability (p) of getting  ‘success’ is .5 (the coin is fair), and we conducted the experiment 2,000 times  (size).
```
print(random.binomial(n = 1, p = 0.5, size=2000)) 
```
The output from our simulation is a list of 0’s and 1’s. This is the number of  successes in each experiment. In this case, since we are simulating a single  trial, 1 would mean the outcome of the trial was a success and 0 would mean  the outcome was a failure. 
If we wanted to do 10 flips per experiment, the result would be a list of numbers  from 0 to 10 representing the number of successes in each experiment. 
```
print(numpy.random.binomial(n=10, p=0.5, size=2000))
``` 
Binomial distributions are really cool – and you will definitely see them again in  your Data Science journey. 
### Reading a File 
Computers use file systems to store and retrieve data. Each file is an individual  container of related information. If you’ve ever saved a document, downloaded  a song, or even sent an email you’ve created a file on some computer  somewhere. Even script.py, the Python program you’re editing in the learning  environment, is a file. 
So, how do we interact with files using Python? We’re going to learn how to  read and write different kinds of files using code. Let’s say we had a file  called real_cool_document.txt with these contents: 
```
real_cool_document.txt 
Wowsers! 
```
We could read that file like this: 
```
script.py 
with open('real_cool_document.txt') as cool_doc:   cool_contents = cool_doc.read() 
print(cool_contents) 
```
This opens a file object called cool_doc and creates a new indented block  where you can read the contents of the opened file. We then read the contents  of the file cool_doc using cool_doc.read() and save the resulting string into the  variable cool_contents. Then we print cool_contents, which outputs the  statement Wowsers!. 
### Iterating Through Lines 
When we read a file, we might want to grab the whole document in a single  string, like .read() would return. But what if we wanted to store each line in a 
variable? We can use the .readlines() function to read a text file line by line  instead of having the whole thing. Suppose we have a file: 
```
keats_sonnet.txt 
To one who has been long in city pent, 
’Tis very sweet to look into the fair 
And open face of heaven,—to breathe a prayer Full in the smile of the blue firmament. 
script.py 
with open('keats_sonnet.txt') as keats_sonnet:   for line in keats_sonnet.readlines(): 
    print(line) 
```
The above script creates a temporary file object called keats_sonnet that points  to the file keats_sonnet.txt. It then iterates over each line in the document and  prints the entire file out. 
### Reading a Line 
Sometimes you don’t want to iterate through a whole file. For that, there’s a  different file method, .readline(), which will only read a single line at a time. If  the entire document is read line by line in this way subsequent calls  to .readline() will not throw an error but will start returning an empty string ("").  Suppose we had this file: 
```
millay_sonnet.txt 
I shall forget you presently, my dear, 
So make the most of this, your little day, 
Your little month, your little half a year, Ere I forget, or die, or move away, 
script.py 
with open('millay_sonnet.txt') as sonnet_doc:   first_line = sonnet_doc.readline() 
  second_line = sonnet_doc.readline() 
  print(second_line) 
```
This script also creates a file object called sonnet_doc that points to the  file millay_sonnet.txt. It then reads in the first line  
using sonnet_doc.readline() and saves that to the variable first_line. It then  saves the second line (So make the most of this, your little day,) into the  variable second_line and then prints it out. 
### Writing a File 
Reading a file is all well and good, but what if we want to create a file of our  own? With Python we can do just that. It turns out that our open() function that  we’re using to open a file to read needs another argument to open a file to write 
to. 
```
script.py 
with open('generated_file.txt', 'w') as gen_file:   gen_file.write("What an incredible file!") 
```
Here we pass the argument 'w' to open() in order to indicate to open the file in  write-mode. The default argument is 'r' and passing 'r' to open() opens the file  in read-mode as we’ve been doing. 
This code creates a new file in the same folder as script.py and gives it the  text What an incredible file!. It’s important to note that if there is already a file  called generated_file.txt it will completely overwrite that file, erasing whatever  its contents were before. 
### Appending to a File 
So maybe completely deleting and overwriting existing files is something that  bothers you. Isn’t there a way to just add a line to a file without completely  deleting it? Of course there is! Instead of opening the file using the  argument 'w' for write-mode, we open it with 'a' for append-mode. If we have a  generated file with the following contents: 
```
generated_file.txt 
This was a popular file... 
Then we can add another line to that file with the  following code: 
script.py 
with open('generated_file.txt', 'a') as gen_file:   gen_file.write("... and it still is") 
```
In the code above we open a file object in the temporary variable gen_file. This  variable points to the file generated_file.txt and, since it’s open in append mode, adds the line ... and it still is as a new line to the file. If you were to open  the file after running the script it would look like this: 
```
generated_file.txt 
This was a popular file... 
... and it still is 
```
Notice that opening the file in append-mode, with 'a' as an argument to open(),  means that using the file object’s .write() method appends whatever is passed  to the end of the file in a new line. If we were to run script.py again, this would  be what generated_file.txt looks like: 
```
generated_file.txt 
This was a popular file... 
... and it still is
... and it still is 
```
Notice that we’ve appended "... and it still is" to the file a second time! This is  because in script.py we opened generated_file.txt in append-mode. 
##### What's With "with"? 
We’ve been opening these files with this with block so far, but it seems a little  weird that we can only use our file variable in the indented block. Why is that? The with keyword invokes something called a context manager for the file that  we’re calling open() on. This context manager takes care of opening the file  when we call open() and then closing the file after we leave the indented block. Why is closing the file so complicated? Well, most other aspects of our code  deal with things that Python itself controls. All the variables you create:  integers, lists, dictionaries — these are all Python objects, and Python knows  how to clean them up when it’s done with them. Since your files  exist outside your Python script, we need to tell Python when we’re done with  them so that it can close the connection to that file. Leaving a file connection  open unnecessarily can affect performance or impact other programs on your  computer that might be trying to access that file. 
The with syntax replaces older ways to access files where you need to  call .close() on the file object manually. We can still open up a file and append  to it with the old syntax, as long as we remember to close the file connection  afterwards. 
```
fun_cities_file = open('fun_cities.txt', 'a') 
# We can now append a line to "fun_cities". fun_cities_file.write("Montréal") 
# But we need to remember to close the file fun_cities_file.close() 
```
In the above script we added “Montréal” as a new line in our file fun_cities.txt.  However, since we used the older-style syntax, we had to remember to close  the file afterwards. Since this is necessarily more verbose (requires at least one  more line of code) without being any more expressive, using with is preferred. 
### What Is a CSV File? 
Text files aren’t the only thing that Python can read, but they’re the only thing  that we don’t need any additional parsing library to understand. CSV files are an  example of a text file that impose a structure to their data. CSV stands  for Comma-Separated Values and CSV files are usually the way that data from  spreadsheet software (like Microsoft Excel or Google Sheets) is exported into a  portable format. 


In a CSV file that same exact data would be rendered like this: 
```
users.csv 
Name,Username,Email 
Roger Smith,rsmith,wigginsryan@yahoo.com 
Michelle Beck,mlbeck,hcosta@hotmail.com 
Ashley Barker,a_bark_x,a_bark_x@turner.com 
Lynn Gonzales,goodmanjames,lynniegonz@hotmail.com Jennifer Chase,chasej,jchase@ramirez.com 
Charles Hoover,choover,choover89@yahoo.com 
Adrian Evans,adevans,adevans98@yahoo.com 
Susan Walter,susan82,swilliams@yahoo.com 
Stephanie King,stephanieking,sking@morris-tyler.com Erika Miller,jessica32,ejmiller79@yahoo.com 
```
Notice that the first row of the CSV file doesn’t actually represent any data, just  the labels of the data that’s present in the rest of the file. The rest of the rows  of the file are the same as the rows in the spreadsheet software, just instead of  being separated into different cells they’re separated by… well I suppose it’s  fair to say they’re separated by commas. 
### Reading a CSV File 
Recall our CSV file from our last exercise: 
```
users.csv 
Name,Username,Email 
Roger Smith,rsmith,wigginsryan@yahoo.com
Michelle Beck,mlbeck,hcosta@hotmail.com 
Ashley Barker,a_bark_x,a_bark_x@turner.com 
Lynn Gonzales,goodmanjames,lynniegonz@hotmail.com 
```
Even though we can read these lines as text without a problem, there are ways  to access the data in a format better suited for programming purposes. In  Python we can convert that data into a dictionary using  
the csv library’s DictReader object. Here’s how we’d create a list of the email  addresses of all of the users in the above table: 
```
import csv 
list_of_email_addresses = [] 
with open('users.csv', newline='') as users_csv:   user_reader = csv.DictReader(users_csv) 
  for row in user_reader: 
    list_of_email_addresses.append(row['Email']) 
```
In the above code we first import our csv library, which gives us the tools to  parse our CSV file. We then create the empty list list_of_email_addresses which  we’ll later populate with the email addresses from our CSV. Then we open  the users.csv file with the temporary variable users_csv. 
We pass the additional keyword argument newline='' to the file  opening open() function so that we don’t accidentally mistake a line break in  one of our data fields as a new row in our CSV (read more about this in the  Python documentation). 
After opening our new CSV file we use csv.DictReader(users_csv) which  converts the lines of our CSV file to Python dictionaries which we can use  access methods for. The keys of the dictionary are, by default, the entries in  the first line of our CSV file. Since our CSV’s first line calls the third field in our  CSV “Email“, we can use that as the key in each row of our DictReader. 
When we iterate through the rows of our user_reader object, we access all of  the rows in our CSV as dictionaries (except for the first row, which we used to  label the keys of our dictionary). By accessing the 'Email' key of each of these  rows we can grab the email address in that row and append it to  our list_of_email_addresses. 
### Reading Different Types of CSV Files 
I need to level with you, I’ve been lying to you for the past two exercises. Well,  kind of. We’ve been acting like CSV files are Comma-Separated Values files. It’s  true that CSV stands for that, but it’s also true that other ways of separating  values are valid CSV files these days. 
People used to call Tab-Separated Values files TSV files, but as other  separators grew in popularity everyone realized that creating a new .[a-z]sv file 
format for every value-separating character used is not sustainable. So we call all files with a list of different values a CSV file and then use  different delimiters (like a comma or tab) to indicate where the different values  start and stop. 
Let’s say we had an address book. Since addresses usually use commas in  them, we’ll need to use a different delimiter for our information. Since none of  our data has semicolons (;) in them, we can use those. 
```
addresses.csv 
Name;Address;Telephone 
Donna Smith;126 Orr Corner Suite 857\nEast Michael, LA  54411;906-918-6560 
Aaron Osborn;6965 Miller Station Suite 485\nNorth  Michelle, KS 64364;815.039.3661x42816 
Jennifer Barnett;8749 Alicia Vista Apt. 288\nLake  Victoriaberg, TN 51094;397-796-4842x451 
Joshua Bryan;20116 Stephanie Stravenue\nWhitneytown, IA  87358;(380)074-6173 
Andrea Jones;558 Melissa Keys Apt. 588\nNorth  Teresahaven, WA 63411;+57(8)7795396386 
Victor Williams;725 Gloria Views Suite 628\nEast Scott,  IN 38095;768.708.3411x954 
```
Notice the \n character, this is the escape sequence for a new line. The  possibility of a new line escaped by a \n character in our data is why we pass  the newline='' keyword argument to the open() function. 
Also notice that many of these addresses have commas in them! This is okay,  we’ll still be able to read it. If we wanted to, say, print out all the addresses in  this CSV file we could do the following: 
```
import csv 
with open('addresses.csv', newline='') as addresses_csv:   address_reader = csv.DictReader(addresses_csv,  delimiter=';') 
  for row in address_reader: 
    print(row['Address']) 
```
Notice that when we call csv.DictReader we pass in the delimiter parameter,  which is the string that’s used to delineate separate fields in the CSV. We then  iterate through the CSV and print out each of the addresses. 
### Writing a CSV File 
Naturally if we have the ability to read different CSV files we might want to be  able to programmatically create CSV files that save output and data that  someone could load into their spreadsheet software. Let’s say we have a big list  of data that we want to save into a CSV file. We could do the following:
```
big_list = [{'name': 'Fredrick Stein', 'userid':  6712359021, 'is_admin': False}, {'name': 'Wiltmore  Denis', 'userid': 2525942, 'is_admin': False}, {'name':  'Greely Plonk', 'userid': 15890235, 'is_admin': False},  {'name': 'Dendris Stulo', 'userid': 572189563,  'is_admin': True}]  
import csv 
with open('output.csv', 'w') as output_csv:   fields = ['name', 'userid', 'is_admin'] 
  output_writer = csv.DictWriter(output_csv,  fieldnames=fields) 
  output_writer.writeheader() 
  for item in big_list: 
    output_writer.writerow(item) 
```
In our code above we had a set of dictionaries with the same keys for each, a  prime candidate for a CSV. We import the csv library, and then open a new CSV  file in write-mode by passing the 'w' argument to the open() function. We then define the fields we’re going to be using into a variable called fields.  We then instantiate our CSV writer object and pass two arguments. The first  is output_csv, the file handler object. The second is our list of  fields fields which we pass to the keyword parameter fieldnames. Now that we’ve instantiated our CSV file writer, we can start adding lines to the  file itself! First we want the headers, so we call .writeheader() on the writer  object. This writes all the fields passed to fieldnames as the first row in our file.  Then we iterate through our big_list of data. Each item in big_list is a dictionary  with each field in fields as the keys. We call output_writer.writerow() with  the item dictionaries which writes each line to the CSV file. 
### Reading a JSON File 
CSV isn’t the only file format that Python has a built-in library for. We can also  use Python’s file tools to read and write JSON. JSON, an abbreviation of  JavaScript Object Notation, is a file format inspired by the programming  language JavaScript. The name, like CSV is a bit of a misnomer — some JSON  is not valid JavaScript (and plenty of JavaScript is not valid JSON). JSON’s format is endearingly similar to Python dictionary syntax, and so JSON  files might be easy to read from a Python developer standpoint. Nonetheless,  Python comes with a json package that will help us parse JSON files into actual  Python dictionaries. Suppose we have a JSON file like the following: 
```
purchase_14781239.json 
{ 
  'user': 'ellen_greg',
  'action': 'purchase', 
  'item_id': '14781239', 
}
``` 
We would be able to read that in as a Python dictionary with the following code: 
```
json_reader.py 
import json 
with open('purchase_14781239.json') as purchase_json:   purchase_data = json.load(purchase_json) 
print(purchase_data['user']) 
# Prints 'ellen_greg' 
```
First we import the json package. We opened the file using our  trusty open() command. Since we’re opening it in read-mode we just need to  pass the file name. We save the file in the temporary variable purchase_json. We continue by parsing purchase_json using json.load(), creating a Python  dictionary out of the file. Saving the results into purchase_data means we can  interact with it. We print out one of the values of the JSON file by keying into  the purchase_data object. 
### Writing a JSON File 
Naturally we can use the json library to translate Python objects to JSON as  well. This is especially useful in instances where you’re using a Python library  to serve web pages, you would also be able to serve JSON. Let’s say we had a  Python dictionary we wanted to save as a JSON file: 


```
turn_to_json = { 
  'eventId': 674189, 
  'dateTime': '2015-02-12T09:23:17.511Z', 
  'chocolate': 'Semi-sweet Dark', 
  'isTomatoAFruit': True 
}
``` 
We’d be able to create a JSON file with that information by doing the following:
```
import json 
with open('output.json', 'w') as json_file:   json.dump(turn_to_json, json_file) 
```
We import the json module, open up a write-mode file under the  variable json_file, and then use the json.dump() method to write to the  file. json.dump() takes two arguments: first the data object, then the file object  you want to save.

### Lambda Functions 
Learn how to define a Python function in one line! A function is an object that is able to accept some sort of input, possibly  modify it, and return some sort of output. In Python, a lambda function is a  one-line shorthand for function. A simple lambda function might look like this: 
```
add_two = lambda my_input: my_input + 2 
```
So this code: 
```
print(add_two(3)) 
print(add_two(100)) 
print(add_two(-2)) 
would print: 
>>> 5 
>>> 102 
>>> 0 
```
Let’s break this syntax down: 
●  The function is stored in a variable called add_two lambda declares that this is a lambda function (if you are familiar with  normal Python functions, this is similar to how we use def to declare a  function) 
● my_input is what we call the input we are passing into add_two 
● We are returning my_input plus 2 (with normal Python functions, we use the keyword return) 

Let’s write a lambda function that checks if a string is a substring of the  string “This is the master string”. 
```
is_substring = lambda my_string: my_string in "This is the master string" So, 
```
the code: 
```
print(is_substring('I')) 
print(is_substring('am')) 
print(is_substring('the')) 
print(is_substring('master')) 
would print: 
>>> False 
>>> False
>>> True 
>>> True 
```
We might want a function that will perform differently based on different inputs.  Let’s say that we have a function check_if_A_grade that outputs 'Got an A!' if a  grade is at least 90, and otherwise says you 'Did not get an A…'. So, the code: 
```
print(check_if_A_grade(91)) 
print(check_if_A_grade(70)) 
print(check_if_A_grade(20)) 
would print: 
>>> 'Got an A!' 
>>> 'Did not get an A...' 
>>> 'Did not get an A...' 
```
We can do this using an if statement in our lambda function, with syntax that  looks like: 
```
<WHAT TO RETURN IF STATEMENT IS TRUE> if <IF STATEMENT> else  <WHAT TO RETURN IF STATEMENT IS FALSE> 
```
So this is what our check_if_A_grade function might look like: 
```
check_if_A_grade = lambda grade: 'Got an A!' if grade >= 90 else 'Did not get  an A...' 
```
This is what this line of code does: 
1- Declare lambda function with an input called grade (lambda grade:) 
2- Return 'Got an A!' if this statement is true:grade >= 90 
3- Otherwise, return 'Did not get an A...' if this statement is not true:grade >=  90 

Lambda functions only work if we’re just doing a one line command. If we  wanted to write something longer, we’d need a more complex function. Lambda  functions are great when you need to use a function once. Because you aren’t  defining a function, the reusability aspect functions is not present with lambda  functions. By saving the work of defining a function, a lambda function allows  us to efficiently run an expression and produce an output for a specific task,  such as defining a column in a table, or populating information in a dictionary. 
### Contains A 
Welcome! Let’s dive into lambda functions by exploring the in keyword! This lesson will help you review lambda functions by providing some challenge  exercises. If you need a refresher on the syntax of lambda functions, review  this article on lambda functions.
In Python, you can check if a string contains a substring by using the  keyword in. For example, the line: 
```
return "I" in "Team" 
```
would return False, as there is no "I" in "Team". However: 
```
return "I" in "I love Python" 
returns True, because there is an "I" in "I love Python". 
```
Remember that to make a lambda function you can use the syntax: lambda 
```
my_input: <my_input modified somehow> For example, a lambda 
```
that would return my_input plus 1 would look like: 
```
plus_one = lambda 
my_input: my_input+1 
```
### Long String 
To find the number of characters in a string, we use len. This block of code: 
```
print(len("Hello")) 
print(len("world!")) 
print(len("Hello, world!")) 
```
would print out: 
5 
6 
13 
```
#Write your lambda function here 
long_string = lambda str: len(str) > 12 
print(long_string("short")) 
print(long_string("photosynthesis")) 
```
### Ends With A 
You can get a character of a string string_name by using the  syntax string_name[index], where index is the place of character you want to  get, starting at 0. The last character in the string is string_name[-1]. 
For example:
```
my_string = "Whoa! A seesaw" 
print(my_string[0]) 
print(my_string[2]) 
print(my_string[-1]) 
```
would print 
"W" 
"o" 
"w" 
```
#Write your lambda function here 
ends_in_a = lambda str : str[-1] == 'a' 
print(ends_in_a("data")) 
print(ends_in_a("aardvark")) 
```
### Double Or Zero 
Python makes math easy. To multiply, you can use *: 
```
>>> 4*2 
8 
>>> 2*3 
6 
>>> 0*10 
0 
>>> 20*10 
200 
```
As a reminder, to return different output depending on different input, we can  use if and else inside our lambda function: 
```
add_or_subtract = lambda input_number: input_number - 1 if input_number >=  0 else input_number + 1 
```

The function add_or_subtract will return your input minus 1 if your input is  positive or 0, and otherwise will return your input plus 1. 
Here are some examples of how it would work: 
```
>>> add_or_subtract(0) 
-1 
>>> add_or_subtract(8) 
7 
>>> add_or_subtract(-4) 
-3 
#Write your lambda function here 
double_or_zero = lambda num: num * 2 if num > 10 else 0
print(double_or_zero(15)) 
print(double_or_zero(5)) 
```
### Even/Odd 
In Python, %, or the modulo operator, returns the remainder after division. 
```
>>> 4%2 #This divides evenly 
0 
>>> 7%3 #7/3 has a remainder of 1 
1 
>>> 27%10 
7 
>>> 30%10 
0 
```
You can use % 2 to determine if a number is even or odd. If it is even, there  should be no remainder (an output of 0). If it is odd, there should be a  remainder of 1: 
```
>>> 4%2  
0 
>>> 7%2 
1 
>>> 9%2 
1 
>>> 0%2 
0 
#Write your lambda function here 
even_or_odd = lambda num: "even" if num%2 == 0 else  "odd" 
print(even_or_odd(10)) 
print(even_or_odd(5)) 
```
### Multiple of Three 
In general, using %n will tell you if an integer is a multiple of n. If the result is 0,  the integer is a multiple of n (since there is no remainder in the division): 
```
>>> 4%4 #4 is a multiple of 4 
0 
>>> 12%5 #12 is not a multiple of 5 
2  
>>> 9%2 #9 is not a multiple of 2
1 
>>> 100%10 #100 is a multiple of 10 
0 
#Write your lambda function here 
multiple_of_three = lambda num : "multiple of three" if  num%3 == 0 else "not a multiple" 
print(multiple_of_three(9)) 
print(multiple_of_three(10)) 
```
### Movie Rating 
Comparisons can be done using: 
● <: less than 
● <=: less than or equal to 
● >: greater than 
● >=: greater than or equal to 
● ==: equal to 
● !=: not equal to 

These statements return either True or False: 
```
>>> 4 < 4 
False 
>>> 4 <= 4 
True  
>>> 9 > 2  
True 
>>> 9 >= 2 
True 
>>> 1 > 2  
False 
#Write your lambda function here 
rate_movie = lambda rating : "I liked this movie" if  rating > 8.5 else "This movie was not very good" 
print(rate_movie(9.2)) 
print(rate_movie(7.2)) 
```
### Ones' Place 
You can use the modulo operator (%) with 10 to find the ones’ place of an  integer. 
Here are some examples: 
```
>>> 41%10 
1 
>>> 2%10 
2 
>>> 39%10 
9 
>>> 103%10 
3 
>>> 20%10 
0 
#Write your lambda function here 
ones_place = lambda num : num%10 
print(ones_place(123)) 
print(ones_place(4)) 
```
### Double Square 
You can find the square of a number by multiplying it by itself: 
```
eight_squared = 8*8 
#The value of eight_squared is now 64 
```
or by using the exponential operator **: 
```
seven_squared = 7**2 
#The value of seven_squared is now 49 
#Write your lambda function here 
double_square = lambda num: (num**2)*2 
print(double_square(5)) 
print(double_square(3)) 
```
### Add Random 
random.randint(a,b) will return an integer  between a and b (inclusive). 
So, random.randint(5, 8) could return any integer between 5 and 8 including  both 5 and 8. 
random.randint(0, 100) could return any integer between 0 and 100 including  both 0 and 100. 
```
import random 
#Write your lambda function here 
add_random = lambda num : num + random.randint(1, 10) 
print(add_random(5)) 
print(add_random(100))
```
### Introduction to Pandas and NumPy 
pandas and NumPy are very useful libraries in Python. Let’s learn  how to use them! 
##### Pandas 
Pandas is a very popular library for working with data (its goal is to be the most  powerful and flexible open-source tool, and in our opinion, it has reached that  goal). DataFrames are at the center of pandas. A DataFrame is structured like a  table or spreadsheet. The rows and the columns both have indexes, and you  can perform operations on rows or columns separately. 
A pandas DataFrame can be easily changed and manipulated. Pandas has  helpful functions for handling missing data, performing operations on columns  and rows, and transforming data. If that wasn’t enough, a lot of SQL functions  have counterparts in pandas, such as join, merge, filter by, and group by. With  all of these powerful tools, it should come as no surprise that pandas is very  popular among data scientists. 
#### NumPy 
NumPy is an open-source Python library that facilitates efficient numerical  operations on large quantities of data. There are a few functions that exist in  NumPy that we use on pandas DataFrames. For us, the most important part  about NumPy is that pandas is built on top of it. So, NumPy is a dependency of  Pandas. 
###### Installation 
If you have Anaconda installed, NumPy and pandas may have been auto installed as well! If they haven’t been, or if you want to update to the latest  versions, you can open a terminal window and run the following commands: 
```
conda install numpy 
conda install pandas 
```
If you don’t have Anaconda installed, you can alternatively install the libraries  using pip by running the following commands from your terminal: 
```
pip install numpy 
pip install pandas 
```
Once you’ve installed these libraries, you’re ready to open any Python coding  environment (we recommend Jupyter Notebook). Before you can use these  libraries, you’ll need to import them using the following lines of code. We’ll use  the abbreviations np and pd, respectively, to simplify our function calls in the  future.
```
import numpy as np 
import pandas as pd 
```
##### NumPy Arrays 
NumPy arrays are unique in that they are more flexible than normal Python lists.  They are called ndarrays since they can have any number (n) of dimensions (d).  They hold a collection of items of any one data type and can be either a vector  (one-dimensional) or a matrix (multi-dimensional). NumPy arrays allow for fast  element access and efficient data manipulation. 
The code below initializes a Python list named list1: 
```
list1 = [1,2,3,4] 
```
To convert this to a one-dimensional ndarray with one row and four columns,  we can use the np.array() function: 
```
array1 = np.array(list1) 
print(array1) 
[1 2 3 4] 
```
To get a two-dimensional ndarray from a list, we must start with a Python list of  lists: 
```
list2 = [[1,2,3],[4,5,6]] 
array2 = np.array(list2) 
print(array2) 
[[1 2 3] 
 [4 5 6]] 
```
In the above output, you may notice that the NumPy array print-out is displayed  in a way that clearly demonstrates its multi-dimensional structure: two rows  and three columns. 
Many operations can be performed on NumPy arrays which makes them very  helpful for manipulating data: 
● Selecting array elements 
● Slicing arrays 
● Reshaping arrays 
● Splitting arrays 
● Combining arrays 
● Numerical operations (min, max, mean, etc) 

Mathematical operations can be performed on all values in a ndarray at one  time rather than having to loop through values, as is necessary with a Python  list. This is very helpful in many scenarios. Say you own a toy store and decide  to decrease the price of all toys by €2 for a weekend sale. With the toy prices  stored in an ndarray, you can easily facilitate this operation.
```
toyPrices = np.array([5,8,3,6]) 
print(toyPrices - 2) 
[3 6 1 4] 
```
If, however, you had stored your toy prices in a Python list, you would have to  manually loop through the entire list to decrease each toy price. 
```
toyPrices = [5,8,3,6] 
# print(toyPrices - 2) -- Not possible. Causes an error for i in range(len(toyPrices)): 
    toyPrices[i] -= 2 
print(toyPrices) 
[3,6,1,4] 
```
##### Pandas Series and Dataframes 
Just as the ndarray is the foundation of the NumPy library, the Series is the  core object of the pandas library. A pandas Series is very similar to a one dimensional NumPy array, but it has additional functionality that allows values  in the Series to be indexed using labels. A NumPy array does not have the  flexibility to do this. This labeling is useful when you are storing pieces of data  that have other data associated with them. Say you want to store the ages of  students in an online course to eventually figure out the average student age. If  stored in a NumPy array, you could only access these ages with the internal  ndarray indices 0,1,2.... With a Series object, the indices of values are set  to 0,1,2... by default, but you can customize the indices to be other values such  as student names so an age can be accessed using a name. Customized  indices of a Series are established by sending values into the Series  constructor, as you will see below. 
A Series holds items of any one data type and can be created by sending in a  scalar value, Python list, dictionary, or ndarray as a parameter to the pandas  Series constructor. If a dictionary is sent in, the keys may be used as the  indices. 
```
# Create a Series using a NumPy array of ages with the  default numerical indices 
ages = np.array([13,25,19]) 
series1 = pd.Series(ages) 
print(series1) 
0 | 13 
1 | 25 
2 | 19 
dtype: int64 
```
When printing a Series, the data type of its elements is also printed. To  customize the indices of a Series object, use the index argument of 
the Series constructor. 
```
# Create a Series using a NumPy array of ages but  customize the indices to be the names that correspond to  each age 
ages = np.array([13,25,19]) 
series1 = pd.Series(ages,index=['Emma', 'Swetha',  'Serajh']) 
print(series1) 
Emma | 13 
Swetha | 25 
Serajh | 19 
dtype: int64 
```
Series objects provide more information than NumPy arrays do. Printing a  NumPy array of ages does not print the indices or allow us to customize them. 
```
ages = np.array([13,25,19]) 
print(ages) 
[13 25 19] 
```
Another important type of object in the pandas library is the DataFrame. This  object is similar in form to a matrix as it consists of rows and columns. Both  rows and columns can be indexed with integers or String names. One  DataFrame can contain many different types of data types, but within a column,  everything has to be the same data type. A column of a DataFrame is  essentially a Series. All columns must have the same number of elements  (rows). 
There are different ways to fill a DataFrame such as with a CSV file, a SQL  query, a Python list, or a dictionary. Here we have created a DataFrame using a  Python list of lists. Each nested list represents the data in one row of the  DataFrame. We use the keyword columns to pass in the list of our custom  column names. 
```
dataf = pd.DataFrame([ 
    ['John Smith','123 Main St',34], 
    ['Jane Doe', '456 Maple Ave',28], 
    ['Joe Schmo', '789 Broadway',51] 
    ], 
    columns=['name','address','age']) 
```
This is how the DataFrame is displayed: 
```
 name | address | age 0 | John Smith | 123 Main St | 34 
1 | Jane Doe | 456 Maple Ave | 28 
2 | Joe Schmo | 789 Broadway | 51
```

The default row indices are 0,1,2..., but these can be changed. For example,  they can be set to be the elements in one of the columns of the DataFrame. To  use the names column as indices instead of the default numerical values, we  can run the following command on our DataFrame: 
```
dataf.set_index('name') 
 name | address | age 
John Smith | 123 Main St | 34 
Jane Doe | 456 Maple Ave | 28 
Joe Schmo | 789 Broadway | 51 
```
DataFrames are useful because they make it much easier to select, manipulate,  and summarize data. Their tabular format (a table with rows and columns) also  makes it easier to label, simpler to read, and easier to export data to and from a  
spreadsheet. Understanding the power of these new data structures is the key  to unlocking many new avenues for data manipulation, exploration, and  analysis! 
##### Importing the Pandas Module 
Pandas is a Python module for working with tabular data (i.e., data in a table  with rows and columns). Tabular data has a lot of the same functionality as SQL  or Excel, but Pandas adds the power of Python. 
In order to get access to the Pandas module, we’ll need to install the module  and then import it into a Python file. 
The pandas module is usually imported at the top of a  Python file under the alias pd. 
```
import pandas as pd 
```
If we need to access the pandas module, we can do so by operating on pd. In this lesson, you’ll learn the basics of working with a single table in Pandas,  such as: 
● Create a table from scratch 
● Loading data from another file 
● Selecting certain rows or columns of a table 

```
# Before we analyze anything, we need to import pandas 
import pandas as pd 
```
We can load data into Pandas from a csv (comma-separated variable) file. This  data represents purchases from ShoeFly.com. 
```
df = pd.read_csv('shoefly_orders.csv') 
```
Let's examine the first 10 rows of our data! 
```
df.head(10)
``` 
``` 
	id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
0	54791	Rebecca	Lindsay	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
1	53450	Emily	Joyce	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy
2	91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
3	14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
4	79357	Andrew	Banks	AB4318@gmail.com	boots	leather	brown
5	52386	Julie	Marsh	JulieMarsh59@gmail.com	sandals	fabric	black
6	20487	Thomas	Jensen	TJ5470@gmail.com	clogs	fabric	navy
7	76971	Janice	Hicks	Janice.Hicks@gmail.com	clogs	faux-leather	navy
8	21586	Gabriel	Porter	GabrielPorter24@gmail.com	clogs	leather	brown
9	62083	Frances	Palmer	FrancesPalmer50@gmail.com	wedges	leather	white
``` 

Let's select everyone who ordered black sandals. 
```
df[(df.shoe_type == 'sandals') & (df.shoe_color ==  'black')] 
```

``` 
	id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
2	91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
5	52386	Julie	Marsh	JulieMarsh59@gmail.com	sandals	fabric	black
``` 
Let's see what Susan Dennis ordered. 
```
df[(df.first_name == 'Susan') & (df.last_name ==  'Dennis')] 
```
``` 
	id	first_name	last_name	email	shoe_type	shoe_material
12	45832	Susan	Dennis	SusanDennis58@gmail.com	ballet flats	fabric
``` 

It looks like Susan ordered white fabric ballet flats! 

##### Create a DataFrame I 
A DataFrame is an object that stores data as rows and columns. You can think  of a DataFrame as a spreadsheet or as a SQL table. You can manually create a  DataFrame or fill it with data from a CSV, an Excel spreadsheet, or a SQL query. 
DataFrames have rows and columns. Each column has a name, which is a  string. Each row has an index, which is an integer. DataFrames can contain  many different data types: strings, ints, floats, tuples, etc. 
You can pass in a dictionary to pd.DataFrame(). Each key is a column name  and each value is a list of column values. The columns must all be the same  length or you will get an error. Here’s an example: 
```
df1 = pd.DataFrame({ 
    'name': ['John Smith', 'Jane Doe', 'Joe Schmo'],     'address': ['123 Main St.', '456 Maple Ave.', '789  Broadway'], 
    'age': [34, 28, 51] 
}) 
```
This command creates a DataFrame called df1 that looks like this: 
``` 
address	age	name
123 Main St.	34	John Smith
456 Maple Ave.	28	Jane Doe
789 Broadway	51	Joe Schmo
``` 

Note that the columns will appear in alphabetical order because dictionaries  don’t have any inherent order for columns. 
You can also add data using lists. 
For example, you can pass in a list of lists, where each one represents a row of  data. Use the keyword argument columns to pass a list of column names.
```
df2 = pd.DataFrame([ 
    ['John Smith', '123 Main St.', 34], 
    ['Jane Doe', '456 Maple Ave.', 28], 
    ['Joe Schmo', '789 Broadway', 51] 
    ], 
    columns=['name', 'address', 'age']) 
```
This command produces a DataFrame df2 that looks like this: 
```
name	address	age
John Smith	123 Main St.	34
Jane Doe	456 Maple Ave.	28
Joe Schmo	789 Broadway	51
```



In this example, we were able to control the ordering of the columns because  we used lists. 
### Comma Separated Variables (CSV) 
We now know how to create our own DataFrame. However, most of the time,  we’ll be working with datasets that already exist. One of the most common  formats for big datasets is the CSV. 
CSV (comma separated values) is a text-only spreadsheet format. You can find  CSVs in lots of places: 
● Online datasets (here’s an example from data.gov) 
● Export from Excel or Google Sheets 
● Export from SQL 

The first row of a CSV contains column headings. All subsequent rows contain  values. Each column heading and each variable is separated by a comma: 

column1,column2,column3 
value1,value2,value3 

That example CSV represents the following table: 
```
column1	column2	column3
value1	value2	value3
```

Write the following data as a CSV in cupcakes.csv.
```
name	cake_flavor	frosting_flavor	topping
Chocolate Cake	chocolate	chocolate	chocolate shavings
Birthday Cake	vanilla	vanilla	rainbow sprinkles
Carrot Cake	carrot	cream cheese	almonds
```

name,cake_flavor,frosting_flavor,topping 
Chocolate Cake,chocolate,chocolate,chocolate shavings Birthday Cake,vanilla,vanilla,rainbow sprinkles Carrot Cake,carrot,cream cheese,almonds

### Loading and Saving CSVs 
When you have data in a CSV, you can load it into a DataFrame in Pandas  using .read_csv(): 
```
pd.read_csv('my-csv-file.csv') 
```
In the example above, the .read_csv() method is called. The CSV file called my csv-file is passed in as an argument. 
We can also save data to a CSV, using .to_csv(). 
```
df.to_csv('new-csv-file.csv') 
```
In the example above, the .to_csv() method is called on df (which represents a  DataFrame object). The name of the CSV file is passed in as an argument (new csv-file.csv). By default, this method will save the CSV file in your current  directory. 
### Inspect a DataFrame 
When we load a new DataFrame from a CSV, we want to know what it looks like. If it’s a small DataFrame, you can display it by typing print(df). 
If it’s a larger DataFrame, it’s helpful to be able to inspect a few items without  having to look at the entire DataFrame. 
The method .head() gives the first 5 rows of a DataFrame. If you want to see  more rows, you can pass in the positional argument n. For  
example, df.head(10) would show the first 10 rows. 
The method df.info() gives some statistics for each column. 
### Select Columns 
Now we know how to create and load data. Let’s select parts of those datasets  that are interesting or important to our analyses. 
Suppose you have the DataFrame called customers, which contains the ages of  your customers:
```
name	age
Rebecca Erikson	35
Thomas Roberson	28
Diane Ochoa	42
…	…
```


Perhaps you want to take the average or plot a histogram of the ages. In order  to do either of these tasks, you’d need to select the column. There are two possible syntaxes for selecting all values from a column: 
● Select the column as if you were selecting a value from a dictionary  using a key. In our example, we would type customers['age'] to select  the ages. 
● If the name of a column follows all of the rules for a variable name (doesn’t start with a number, doesn’t contain spaces or special  characters, etc.), then you can select it using the following  notation: df.MySecondColumn. In our example, we would  type customers.age. 

When we select a single column, the result is called a Series. 

The DataFrame df represents data collected by four health clinics run by the  same organization. Each row represents a month from January through June  and shows the number of appointments made at four different clinics. You want to analyze what’s been happening at the North location. Create a  variable called clinic_north that contains ONLY the data from the  column clinic_north. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154], 
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south',  'clinic_west'] 
) 
clinic_north = df['clinic_north'] 
print(type(clinic_north))
print(type(df)) 
```
Out: 
<class 'pandas.core.series.Series'> 
<class 'pandas.core.frame.DataFrame'> 

### Selecting Multiple Columns 
When you have a larger DataFrame, you might want to select just a few  columns. 
For instance, let’s return to a DataFrame of orders from ShoeFly.com: 
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
54791	Rebecca	Lindsay	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
53450	Emily	Joyce	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy
91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
```


We might just be interested in the customer’s last_name and email. We want a  DataFrame like this: 
```
last_name	email
Lindsay	RebeccaLindsay57@hotmail.com
Joyce	EmilyJoyce25@gmail.com
Waller	Joyce.Waller@gmail.com
Erickson	Justin.Erickson@outlook.com
```

To select two or more columns from a DataFrame, we use a list of the column  names. To create the DataFrame shown above, we would use: 
```
new_df = orders[['last_name', 'email']]
```
Note: Make sure that you have a double set of brackets ([[]]), or this command  won’t work! 

Now, you want to compare visits to the Northern and Southern clinics. Create a variable called clinic_north_south that contains ONLY the data from  the columns clinic_north and clinic_south. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154], 
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south', 
 'clinic_west'] 
) 
clinic_north_south = df[['clinic_north',  
'clinic_south']] 
print(type(clinic_north_south)) 
```
Out: 
<class 'pandas.core.frame.DataFrame'> 
### Select Rows 
Let’s revisit our orders from ShoeFly.com:
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
54791	Rebecca	Lindsay	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
53450	Emily	James	EmilyJames25@gmail.com	ballet flats	faux-leather	navy
91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
```

Maybe our Customer Service department has just received a message from  Joyce Waller, so we want to know exactly what she ordered. We want to select  this single row of data. 
DataFrames are zero-indexed, meaning that we start with the 0th row and  count up from there. Joyce Waller’s order is the 2nd row. 
We select it using the following command: 
```
orders.iloc[2] 
```
When we select a single row, the result is a Series (just like when we select a  single column). 
You’re getting ready to staff the clinic for March this year. You want to know  how many visits took place in March last year, to help you prepare. Write a command that will produce a Series made up of the March data  from df from all four clinic sites and save it to the variable march. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154], 
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south', 
 'clinic_west']) 
march = df.iloc[2] 
print(march) 
OUT: 
month March 
clinic_east 81 
clinic_north 96 
clinic_south 65 
clinic_west 96 
Name: 2, dtype: object 
```
### Selecting Multiple Rows 
You can also select multiple rows from a DataFrame. 
Here are a few more rows from ShoeFly.com’s orders DataFrame: 
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
54791	Rebecca	Lindsay	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
53450	Emily	Joyce	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy
91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
79357	Andrew	Banks	AB4318@gmail.com	boots	leather	brown
52386	Julie	Marsh	JulieMarsh59@gmail.com	sandals	fabric	black
20487	Thomas	Jensen	TJ5470@gmail.com	clogs	fabric	navy
76971	Janice	Hicks	Janice.Hicks@gmail.com	clogs	faux-leather	navy
21586	Gabriel	Porter	GabrielPorter24@gmail.com	clogs	leather	brown
```

Here are some different ways of selecting multiple rows: 
● orders.iloc[3:7] would select all rows starting at the 3rd row and up to  but not including the 7th row (i.e., the 3rd row, 4th row, 5th row, and  6th row) 
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
79357	Andrew	Banks	AB4318@gmail.com	boots	leather	brown
52386	Julie	Marsh	JulieMarsh59@gmail.com	sandals	fabric	black
20487	Thomas	Jensen	TJ5470@gmail.com	clogs	fabric	navy
```
● orders.iloc[:4] would select all rows up to, but not including the 4th  row (i.e., the 0th, 1st, 2nd, and 3rd rows) 
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
54791	Rebecca	Lindsay	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
53450	Emily	Joyce	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy
91987	Joyce	Waller	Joyce.Waller@gmail.com	sandals	fabric	black
14437	Justin	Erickson	Justin.Erickson@outlook.com	clogs	faux-leather	red
```
● orders.iloc[-3:] would select the rows starting at the 3rd to last row  and up to and including the final row 
```
id	first_name	last_name	email	shoe_type	shoe_material	shoe_color
20487	Thomas	Jensen	TJ5470@gmail.com	clogs	fabric	navy
76971	Janice	Hicks	Janice.Hicks@gmail.com	clogs	faux-leather	navy
21586	Gabriel	Porter	GabrielPorter24@gmail.com	clogs	leather	brown
```

### Select Rows with Logic I 
You can select a subset of a DataFrame by using logical statements: 
```
df[df.MyColumnName == desired_column_value] 
```
We have a large DataFrame with information about our customers. A few of the  many rows look like this:
```
name	address	phone	age
Martha Jones	123 Main St.	234-567-8910	28
Rose Tyler	456 Maple Ave.	212-867-5309	22
Donna Noble	789 Broadway	949-123-4567	35
Amy Pond	98 West End Ave.	646-555-1234	29
Clara Oswald	54 Columbus Ave.	714-225-1957	31
…	…	…	…
```
Suppose we want to select all rows where the customer’s age is 30. We would  use: 
```
df[df.age == 30] 
```
In Python, == is how we test if a value is exactly equal to another value. We can use other logical statements, such as: 
● Greater Than, > — Here, we select all rows where the customer’s age  is greater than 30:df[df.age > 30] 
● Less Than, < — Here, we select all rows where the customer’s age is less than 30:df[df.age < 30] 
● Not Equal, != — This snippet selects all rows where the customer’s name is not Clara Oswald:df[df.name != 'Clara Oswald'] 
You’re going to staff the clinic for January of this year. You want to know how  many visits took place in January of last year, to help you prepare. Create variable january using a logical statement that selects the row  of df where the 'month' column is 'January'. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154], 
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south',  'clinic_west']) 
january = df[df.month == 'January']  
print(january) 
```

OUT: 
 month clinic_east clinic_north clinic_south clinic_west 
0 January 100 100 23 100 
### Select Rows with Logic II 
You can also combine multiple logical statements, as long as each statement is  in parentheses. 
For instance, suppose we wanted to select all rows where the customer’s age  was under 30 or the customer’s name was “Martha Jones”: 
```
name	address	phone	age
Martha Jones	123 Main St.	234-567-8910	28
Rose Tyler	456 Maple Ave.	212-867-5309	22
Donna Noble	789 Broadway	949-123-4567	35
Amy Pond	98 West End Ave.	646-555-1234	29
Clara Oswald	54 Columbus Ave.	714-225-1957	31
…			
```
We could use the following code: 
```
df[(df.age < 30) | 
   (df.name == 'Martha Jones')] 
```
In Python, | means “or” and & means “and”. 

You want to see how the number of clinic visits changed between March and  April. 
Create the variable march_april, which contains the data from March and April.  Do this using two logical statements combined using |, which means “or”. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154], 
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south', 
 'clinic_west'])
march_april = df[(df.month == 'March') | (df.month ==  'April')]  
print(march_april) 
```
OUT: 
month clinic_east clinic_north clinic_south clinic_west 2 March 81 96 65 96 3 April 80 80 54 180 
### Select Rows with Logic III 
Suppose we want to select the rows where the customer’s name is either  “Martha Jones”, “Rose Tyler” or “Amy Pond”. 

We could use the isin command to check that df.name is one of a list of values: 
```
df[df.name.isin(['Martha Jones', 
     'Rose Tyler', 
     'Amy Pond'])] 
```
Another doctor thinks that you have a lot of clinic visits in the late Winter. Create the variable january_february_march, containing the data from January,  February, and March. Do this using a single logical statement with  the isin command. 
```
import codecademylib3 
import pandas as pd 
df = pd.DataFrame([ 
 ['January', 100, 100, 23, 100], 
 ['February', 51, 45, 145, 45], 
 ['March', 81, 96, 65, 96], 
 ['April', 80, 80, 54, 180], 
 ['May', 51, 54, 54, 154],
 ['June', 112, 109, 79, 129]], 
 columns=['month', 'clinic_east', 
 'clinic_north', 'clinic_south', 
 'clinic_west']) 
january_february_march = df[df.month.isin(['January',  'February', 'March'])]  
print(january_february_march) 
```
OUT: 
month clinic_east clinic_north clinic_south clinic_west 0 January 100 100 23 100 1 February 51 45 145 45 2 March 81 96 65 96 
### Setting indices 
When we select a subset of a DataFrame using logic, we end up with non consecutive indices. This is inelegant and makes it hard to use .iloc(). We can fix this using the method .reset_index(). For example, here is a  DataFrame called df with non-consecutive indices: 
```
	First Name	Last Name
0	John	Smith
4	Jane	Doe
7	Joe	Schmo
```
If we use the command df.reset_index(), we get a new DataFrame with a new  set of indices: 
```
	index	First Name	Last Name
0	0	John	Smith
1	4	Jane	Doe
2	7	Joe	Schmo
```
Note that the old indices have been moved into a new column called 'index'.  Unless you need those values for something special, it’s probably better to use  the keyword drop=True so that you don’t end up with that extra column. If we  run the command df.reset_index(drop=True), we get a new DataFrame that  looks like this:
```
	First Name	Last Name
0	John	Smith
1	Jane	Doe
2	Joe	Schmo
```
Using .reset_index() will return a new DataFrame, but we usually just want to  modify our existing DataFrame. If we use the keyword inplace=True we can just  modify our existing DataFrame. 

### Adding a Column I 
Sometimes, we want to add a column to an existing DataFrame. We might want  to add new information or perform a calculation based on the data that we  already have. 
One way that we can add a new column is by giving a list of the same length as  the existing DataFrame. 
Suppose we own a hardware store called The Handy Woman and have a  DataFrame containing inventory information: 
```
Product ID	Product Description	Cost to Manufacture	Price
1	3 inch screw	0.50	0.75
2	2 inch nail	0.10	0.25
3	hammer	3.00	5.50
4	screwdriver	2.50	3.00
```

It looks like the actual quantity of each product in our warehouse is missing! Let’s use the following code to add that information to our DataFrame. 
```
df['Quantity'] = [100, 150, 50, 35] 
```
Our new DataFrame looks like this: 
```
Product ID	Product Description	Cost to Manufacture	Price	Quantity
1	3 inch screw	0.50	0.75	100
2	2 inch nail	0.10	0.25	150
3	hammer	3.00	5.50	50
4	screwdriver	2.50	3.00	35
```
### Adding a Column II 
We can also add a new column that is the same for all rows in the DataFrame.  Let’s return to our inventory example:
```
Product ID	Product Description	Cost to Manufacture	Price
1	3 inch screw	0.50	0.75
2	2 inch nail	0.10	0.25
3	hammer	3.00	5.50
4	screwdriver	2.50	3.00
```
Suppose we know that all of our products are currently in-stock. We can add a  column that says this: 
```
df['In Stock?'] = True 
```
Now all of the rows have a column called In Stock? with value True. 
```
Product ID	Product Description	Cost to Manufacture	Price	In Stock?
1	3 inch screw	0.50	0.75	True
2	2 inch nail	0.10	0.25	True
3	hammer	3.00	5.50	True
4	screwdriver	2.50	3.00	True
```

### Adding a Column III 
Finally, you can add a new column by performing a function on the existing  columns. 
Maybe we want to add a column to our inventory table with the amount of sales  tax that we need to charge for each item. The following code multiplies  each Price by 0.075, the sales tax for our state: 
```
df['Sales Tax'] = df.Price * 0.075 
```
Now our table has a column called Sales Tax: 
```
Product ID	Product Description	Cost to Manufacture	Price	Sales Tax
1	3 inch screw	0.50	0.75	0.06
2	2 inch nail	0.10	0.25	0.02
3	hammer	3.00	5.50	0.41
4	screwdriver	2.50	3.00	0.22
```
### Performing Column Operations 
In the previous exercise, we learned how to add columns to a DataFrame. Often, the column that we want to add is related to existing columns, but  requires a calculation more complex than multiplication or addition. For example, imagine that we have the following table of customers. 
```
Name	Email
JOHN SMITH	john.smith@gmail.com
Jane Doe	jdoe@yahoo.com
joe schmo	joeschmo@hotmail.com
```

It’s a little annoying that the capitalization is different for each row. Perhaps  we’d like to make it more consistent by making all of the letters uppercase.

We can use the apply function to apply a function to every value in a particular  column. For example, this code overwrites the existing 'Name' columns by  applying the function upper to every row in 'Name'. 
```
df['Name'] = df.Name.apply(str.upper) 
```
The result: 
```
Name	Email
JOHN SMITH	john.smith@gmail.com
JANE DOE	jdoe@yahoo.com
JOE SCHMO	joeschmo@hotmail.com
```

### Reviewing Lambda Function 
A lambda function is a way of defining a function in a single line of code.  Usually, we would assign them to a variable. 
For example, the following lambda function multiplies a number by 2 and then  adds 3: 
```
mylambda = lambda x: (x * 2) + 3 
print(mylambda(5)) 
```
The output: 
> 13 
Lambda functions work with all types of variables, not just integers! Here is an  example that takes in a string, assigns it to the temporary variable x, and then  converts it into lowercase: 
```
stringlambda = lambda x: x.lower() 
print(stringlambda("Oh Hi Mark!")) 
```
The output: 
> "oh hi mark!" 
Learn more about lambda functions in this article! 
### Reviewing Lambda Function: If Statements 
We can make our lambdas more complex by using a modified form of an if  statement. 
Suppose we want to pay workers time-and-a-half for overtime (any work above  40 hours per week). The following function will convert the number of hours  into time-and-a-half hours using an if statement: 
```
def myfunction(x): 
    if x > 40: 
        return 40 + (x - 40) * 1.50
    else: 
        return x 
```
Below is a lambda function that does the same thing: 
```
myfunction = lambda x: 40 + (x - 40) * 1.50 if x > 40  else x 
```
In general, the syntax for an if function in a lambda function is: lambda x: 
[OUTCOME IF TRUE] if [CONDITIONAL] else [OUTCOME IF FALSE] 

### Applying a Lambda to a Column 
In Pandas, we often use lambda functions to perform complex operations on  columns. For example, suppose that we want to create a column containing the  email provider for each email address in the following table: 
```
Name	Email
JOHN SMITH	john.smith@gmail.com
Jane Doe	jdoe@yahoo.com
joe schmo	joeschmo@hotmail.com
```
We could use the following code with a lambda function and the string  method .split(): 
```
df['Email Provider'] = df.Email.apply( 
    lambda x: x.split('@')[-1] 
    ) 
```
The result would be: 
```
Name	Email	Email Provider
JOHN SMITH	john.smith@gmail.com	gmail.com
Jane Doe	jdoe@yahoo.com	yahoo.com
joe schmo	joeschmo@hotmail.com	hotmail.com
```

Create a lambda function get_last_name which takes a string with someone’s  first and last name (i.e., John Smith), and returns just the last name  (i.e., Smith). 
The DataFrame df represents the hours worked by different employees over the  course of the week. It contains the following columns: 
● 'name': The employee’s name 
● 'hourly_wage': The employee’s hourly wage 
● 'hours_worked': The number of hours worked this week 

Use the lambda function get_last_name to create a new column last_name with 
only the employees’ last name. 
```
import codecademylib3 
import pandas as pd 
df = pd.read_csv('employees.csv') 
# Add columns here 
print(df) 
get_last_name = lambda name : name.split()[-1] df['last_name'] = df.name.apply(get_last_name) print(df) 
```
Out:
```
	id	name	hourly_wage	hours_worked
0	10310	Lauren Durham	19	43
1	18656	Grace Sellers	17	40
2	61254	Shirley Rasmussen	16	30
3	16886	Brian Rojas	18	47
4	89010	Samantha Mosley	11	38
5	87246	Louis Guzman	14	39
```

```
	id	name	hourly_wage	hours_worked	last_name
0	10310	Lauren Durham	19	43	Durham
1	18656	Grace Sellers	17	40	Sellers
2	61254	Shirley Rasmussen	16	30	Rasmussen
3	16886	Brian Rojas	18	47	Rojas
4	89010	Samantha Mosley	11	38	Mosley
5	87246	Louis Guzman	14	39	Guzman
```
### Applying a Lambda to a Row 
We can also operate on multiple columns at once. If we use apply without  specifying a single column and add the argument axis=1, the input to our  lambda function will be an entire row, not a column. To access particular values  of the row, we use the syntax row.column_name or row[‘column_name’]. Suppose we have a table representing a grocery list: 
```
Item	Price	Is taxed?
Apple	1.00	No
Milk	4.20	No
Paper Towels	5.00	Yes
Light Bulbs	3.75	Yes
```

If we want to add in the price with tax for each line, we’ll need to look at two  columns: Price and Is taxed?. 
If Is taxed? is Yes, then we’ll want to multiply Price by 1.075 (for 7.5% sales tax). If Is taxed? is No, we’ll just have Price without multiplying it. 
We can create this column using a lambda function and the keyword axis=1: 
```
df['Price with Tax'] = df.apply(lambda row:      row['Price'] * 1.075 
     if row['Is taxed?'] == 'Yes' 
     else row['Price'], 
     axis=1 
) 
```
If an employee worked for more than 40 hours, she needs to be paid overtime  (1.5 times the normal hourly wage). 
For instance, if an employee worked for 43 hours and made $10/hour, she  would receive $400 for the first 40 hours that she worked, and an additional  $45 for the 3 hours of overtime, for a total for $445. 
Create a lambda function total_earned that accepts an input row with  keys hours_worked and hourly_wage and uses an if statement to calculate the  hourly wage. 
Use the lambda function total_earned and apply to add a  
column total_earned to df with the total amount earned by each employee.

```
import codecademylib3 
import pandas as pd 
df = pd.read_csv('employees.csv') 
total_earned = lambda row: (row.hourly_wage * 40) +  ((row.hourly_wage * 1.5) * (row.hours_worked - 40)) \  if row.hours_worked > 40 \ 
 else row.hourly_wage * row.hours_worked 
  
df['total_earned'] = df.apply(total_earned, axis = 1) print(df) 
```
Out: 
```
	id	name	hourly_wage	hours_worked	total_earned
0	10310	Lauren Durham	19	43	845.5
1	18656	Grace Sellers	17	40	680.0
2	61254	Shirley Rasmussen	16	30	480.0
3	16886	Brian Rojas	18	47	909.0
4	89010	Samantha Mosley	11	38	418.0
5	87246	Louis Guzman	14	39	546.0
```

### Renaming Columns 
When we get our data from other sources, we often want to change the column  names. For example, we might want all of the column names to follow variable  name rules, so that we can use df.column_name (which tab-completes) rather than df['column_name'] (which takes up extra space). You can change all of the column names at once by setting  
the .columns property to a different list. This is great when you need to change  all of the column names at once, but be careful! You can easily mislabel  columns if you get the ordering wrong. Here’s an example: 
```
df = pd.DataFrame({
    'name': ['John', 'Jane', 'Sue', 'Fred'],     'age': [23, 29, 21, 18] 
}) 
df.columns = ['First Name', 'Age'] 
```
This command edits the existing DataFrame df. 
The DataFrame df contains data about movies from IMDb. 
We want to present this data to some film producers. Right now, our column  names are in lower case, and are not very descriptive. Let’s modify df using  the .columns attribute to make the following changes to the columns: 
```
Old	New
id	ID
name	Title
genre	Category
year	Year Released
imdb_rating	Rating
```

```
import codecademylib3 
import pandas as pd 
df = pd.read_csv('imdb.csv') 
# Rename columns here 
print(df) 
df.columns = ['ID', 'Title', 'Category', 'Year  Released', 'Rating'] 
print(df) 
```
OUT: 
```
id	name	genre	year	imdb_rating	
0	1	Avatar	action	2009	7.9
1	2	Jurassic World	action	2015	7.3
2	3	The Avengers	action	2012	8.1
3	4	The Dark Knight	action	2008	9.0
4	5	Star Wars: Episode I - The Phantom Menace	action	1999	6.6
5	6	Star Wars	action	1977	8.7
```

```
	ID	Title	Category	Year Released	Rating
0	1	Avatar	action	2009	7.9
1	2	Jurassic World	action	2015	7.3
2	3	The Avengers	action	2012	8.1
3	4	The Dark Knight	action	2008	9.0
4	5	Star Wars: Episode I - The Phantom Menace	action	1999	6.6
5	6	Star Wars	action	1977	8.7
```

### Renaming Columns II 
You also can rename individual columns by using the .rename method. Pass a  dictionary like the one below to the columns keyword argument: {'old_column_name1': 'new_column_name1', 'old_column_name2':  'new_column_name2'} 
Here’s an example: 
```
df = pd.DataFrame({ 
    'name': ['John', 'Jane', 'Sue', 'Fred'],     'age': [23, 29, 21, 18] 
}) 
df.rename(columns={ 
    'name': 'First Name', 
    'age': 'Age'}, 
    inplace=True) 
```
The code above will rename name to First Name and age to Age. Using rename with only the columns keyword will create a new DataFrame, leaving your original DataFrame unchanged. That’s why we also passed in the  keyword argument inplace=True. 

Using inplace=True lets us edit  the original DataFrame. 

There are several reasons why .rename is preferable to .columns: 
- You can rename just one column 
- You can be specific about which column names are getting changed  (with .column you can accidentally switch column names if you’re not careful) 

Note: If you misspell one of the original column names, this command won’t  fail. It just won’t change anything. 


Let’s practice what you just learned! 

Once more, you’ll be the data analyst for ShoeFly.com, a fictional online shoe  store. 
More messy order data has been loaded into the variable orders. Examine the  first 5 rows of the data using print and .head(). 
Many of our customers want to buy vegan shoes (shoes made from materials  that do not come from animals). Add a new column called shoe_source, which  is vegan if the materials is not leather and animal otherwise. 

Our marketing department wants to send out an email to each customer. Using  the columns last_name and gender create a column called salutation which  contains Dear Mr. <last_name> for men and Dear Ms. <last_name> for women. 
```
import codecademylib3 
import pandas as pd 
orders = pd.read_csv('shoefly.csv') 
#print 5 first rows 
print(orders.head(5)) 
#find out if is vegan 
isVegan = lambda material: 'animal' if material ==  'leather' else 'vegan'
orders['shoe_source'] =  
orders.shoe_material.apply(isVegan) 
#find out salutation 
whichSalutation = lambda row : 'Dear Ms. ' +  row.last_name if row.gender == 'female' else 'Dear Mr. '  + row.last_name 
orders['salutation'] = orders.apply(whichSalutation,  axis=1) 
print(orders) 
```
Out:
```
	id	first_name	last_name	gender	email	shoe_type	shoe_material	shoe_color
0	54791	Rebecca	Lindsay	female	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black
1	53450	Emily	Joyce	female	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy
2	91987	Joyce	Waller	female	Joyce.Waller@gmail.com	sandles	fabric	black
3	14437	Justin	Erickson	male	Justin.Erickson@outlook.com	clogs	faux-leather	red
4	79357	Andrew	Banks	male	AB4318@gmail.com	boots	leather	brown
```
```
	id	first_name	last_name	gender	email	shoe_type	shoe_material	shoe_color	shoe_source	salutation
0	54791	Rebecca	Lindsay	female	RebeccaLindsay57@hotmail.com	clogs	faux-leather	black	vegan	Dear Ms. Lindsay
1	53450	Emily	Joyce	female	EmilyJoyce25@gmail.com	ballet flats	faux-leather	navy	vegan	Dear Ms. Joyce
2	91987	Joyce	Waller	female	Joyce.Waller@gmail.com	sandles	fabric	black	vegan	Dear Ms. Waller
3	14437	Justin	Erickson	male	Justin.Erickson@outlook.com	clogs	faux-leather	red	vegan	Dear Mr. Erickson
4	79357	Andrew	Banks	male	AB4318@gmail.com	boots	leather	brown	animal	Dear Mr. Banks
```

The axis=1 is important because it lets the input of the lambda function be  an entire row.

### Calculating Column Statistics 
Aggregate functions summarize many data points (i.e., a column of a  dataframe) into a smaller set of values. 
Some examples of this type of calculation include: 
The DataFrame customers contains the names and ages of all of your  customers. You want to find the median age:print(customers.age) 
```
>> [23, 25, 31, 35, 35, 46, 62] 
print(customers.age.median()) 
>> 35 
```
The DataFrame shipments contains address information for all shipments that  you’ve sent out in the past year. You want to know how many different states  you have shipped to (and how many shipments went to the same  state).print(shipments.state) 
```
>> ['CA', 'CA', 'CA', 'CA', 'NY', 'NY', 'NJ', 'NJ',  'NJ', 'NJ', 'NJ', 'NJ', 'NJ'] 
print(shipments.state.nunique()) 
>> 3 
```
The DataFrame inventory contains a list of types of t-shirts that your company  makes. You want a list of the colors that your shirts come in. 
```
print(inventory.color) 
>> ['blue', 'blue', 'blue', 'blue', 'blue', 'green',  'green', 'orange', 'orange', 'orange'] 
print(inventory.color.unique()) 
>> ['blue', 'green', 'orange'] 
```
The general syntax for these calculations is: 
```
df.column_name.command() 
```
The following table summarizes some common commands:
```
Command	Description
mean	Average of all values in column
std	Standard deviation
median	Median
max	Maximum value in column
min	Minimum value in column
count	Number of values in column
nunique	Number of unique values in column
unique	List of unique values in column
```


### Calculating Aggregate Functions I 
When we have a bunch of data, we often want to calculate aggregate statistics  (mean, standard deviation, median, percentiles, etc.) over certain subsets of  the data. 
Suppose we have a grade book with columns student, assignment_name,  and grade. The first few lines look like this: 
```
Amy	Assignment 1	75
Amy	Assignment 2	35
Bob	Assignment 1	99
Bob	Assignment 2	35
…		
```

We want to get an average grade for each student across all assignments. We  could do some sort of loop, but Pandas gives us a much easier option: the  method .groupby. 
For this example, we’d use the following command: 
```
grades = df.groupby('student').grade.mean() 
```
The output might look something like this: 
```
student	grade
Amy	80
Bob	90
Chris	75
…	
```

In general, we use the following syntax to calculate aggregates: 
```
df.groupby('column1').column2.measurement() where: 
```

● column1 is the column that we want to group by ('student' in our example) 
● column2 is the column that we want to perform a measurement on  
(grade in our example) 
● measurement is the measurement function we want to apply (mean in  
our example) 

For more on the groupby method, review the pandas documentation.

### Calculating Aggregate Functions II 
After using groupby, we often need to clean our resulting data. As we saw in the previous exercise, the groupby function creates a new Series,  not a DataFrame. For our ShoeFly.com example, the indices of the Series were  different values of shoe_type, and the name property was price. 
Usually, we’d prefer that those indices were actually a column. In order to get  that, we can use reset_index(). This will transform our Series into a DataFrame  and move the indices into their own column. 
Generally, you’ll always see a groupby statement followed by reset_index: 
```
df.groupby('column1').column2.measurement()     .reset_index() 
```
When we use groupby, we often want to rename the column we get as a result.  For example, suppose we have a DataFrame teas containing data on types of  tea: 
```
id	tea	category	caffeine	price
0	earl grey	black	38	3
1	english breakfast	black	41	3
2	irish breakfast	black	37	2.5
3	jasmine	green	23	4.5
4	matcha	green	48	5
5	camomile	herbal	0	3
…				
```

We want to find the number of each category of tea we sell. We can use: 
```
teas_counts  
= teas.groupby('category').id.count().reset_index() 
```
This yields a DataFrame that looks like: 
```
	category	id
0	black	3
1	green	4
2	herbal	8
3	white	2
…		
```

The new column contains the counts of each category of tea sold. We have 3 
black teas, 4 green teas, and so on. However, this column is called id because  we used the id column of teas to calculate the counts. We actually want to call  this column counts. Remember that we can rename columns: 
```
teas_counts = teas_counts.rename(columns={"id":  "counts"}) 
```
Our DataFrame now looks like: 
```
	category	counts
0	black	3
1	green	4
2	herbal	8
3	white	2
…		
```

### Calculating Aggregate Functions III 
Sometimes, the operation that you want to perform is more complicated  than mean or count. In those cases, you can use the apply method and lambda  functions, just like we did for individual column operations. Note that the input  to our lambda function will always be a list of values. 
A great example of this is calculating percentiles. Suppose we have a  DataFrame of employee information called df that has the following columns: 
● id: the employee’s id number 
● name: the employee’s name 
● wage: the employee’s hourly wage 
● category: the type of work that the employee does 
Our data might look something like this: 
```
id	name	wage	category
10131	Sarah Carney	39	product
14189	Heather Carey	17	design
15004	Gary Mercado	33	marketing
11204	Cora Copaz	27	design
…			
```
If we want to calculate the 75th percentile (i.e., the point at which 75% of  employees have a lower wage and 25% have a higher wage) for each category,  we can use the following combination of apply and a lambda function: 
```
# np.percentile can calculate any percentile over an  array of values 
high_earners = df.groupby('category').wage 
    .apply(lambda x: np.percentile(x, 75))
    .reset_index() 
```
The output, high_earners might look like this: 
```
	category	wage
0	design	23
1	marketing	35
2	product	48
…		
```



### Calculating Aggregate Functions IV 
Sometimes, we want to group by more than one column. We can easily do this  by passing a list of column names into the groupby method. 
Imagine that we run a chain of stores and have data about the number of sales  at different locations on different days: 
```
Location	Date	Day of Week	Total Sales
West Village	February 1	W	400
West Village	February 2	Th	450
Chelsea	February 1	W	375
Chelsea	February 2	Th	390
			
```

We suspect that sales are different at different locations on different days of  the week. In order to test this hypothesis, we could calculate the average sales  for each store on each day of the week across multiple months. The code would  look like this: 
```
df.groupby(['Location', 'Day of Week'])['Total  Sales'].mean().reset_index() 
```
The results might look something like this: 
```

```

### Pivot Tables 
When we perform a groupby across multiple columns, we often want to change 
how our data is stored. For instance, recall the example where we are running a  chain of stores and have data about the number of sales at different locations  on different days: 
```
Location	Day of Week	Total Sales
Chelsea	M	402.50
Chelsea	Tu	422.75
Chelsea	W	452.00
…		
West Village	M	390
West Village	Tu	400
…		
```


We suspected that there might be different sales on different days of the week  at different stores, so we performed a groupby across two different columns  (Location and Day of Week). This gave us results that looked like this: 
```
Location	Day of Week	Total Sales
Chelsea	M	300
Chelsea	Tu	310
Chelsea	W	320
Chelsea	Th	290
…		
West Village	Th	400
West Village	F	390
West Village	Sa	250
...
```

In order to test our hypothesis, it would be more useful if the table was  formatted like this: 
```
Location	M	Tu	W	Th	F	Sa	Su
Chelsea	400	390	250	275	300	150	175
West Village	300	310	350	400	390	250	200
…							
```

Reorganizing a table in this way is called pivoting. The new table is called  a pivot table. 
In Pandas, the command for pivot is: 
```
df.pivot(columns='ColumnToPivot', 
         index='ColumnToBeRows', 
         values='ColumnToBeValues')
For our specific example, we would write the command like this: 
# First use the groupby statement: 
unpivoted = df.groupby(['Location', 'Day of Week']) ['Total Sales'].mean().reset_index() 
# Now pivot the table 
pivoted = unpivoted.pivot( 
    columns='Day of Week', 
    index='Location', 
    values='Total Sales') 
```
Just like with groupby, the output of a pivot command is a new DataFrame, but  the indexing tends to be “weird”, so we usually follow up with .reset_index(). 

### Introduction: Multiple DataFrames 
In order to efficiently store data, we often spread related information across  multiple tables. 
For instance, imagine that we own an e-commerce business and we want to  track the products that have been ordered from our website. We could have one table with all of the following information: 
order_id 
● 
customer_id 
● 
customer_name 
● 
customer_address 
● 
customer_phone_number 
● 
product_id 
● 
product_description 
● 
product_price 
● 
quantity 
● 
timestamp 
● 
However, a lot of this information would be repeated. If the same customer  makes multiple orders, that customer’s name, address, and phone number will  be reported multiple times. If the same product is ordered by multiple  customers, then the product price and description will be repeated. This will  make our orders table big and unmanageable. 
So instead, we can split our data into three tables: 
orders would contain the information necessary to describe an  
● 
order: order_id, customer_id, product_id, quantity, and timestamp products would contain the information to describe each  
● 
product: product_id, product_description and product_price customers would contain the information for each  
● 
customer: customer_id, customer_name, customer_address,  and customer_phone_number
### Inner Merge I 
Suppose we have the following three tables that describe our eCommerce  business: 
orders — a table with information on each transaction: ● 
```
order_id	customer_id	product_id	quantity	timestamp
1	2	3	1	2017-01-01
2	2	2	3	2017-01-01
3	3	1	1	2017-01-01
4	3	2	2	2017-02-01
5	3	3	3	2017-02-01
6	1	4	2	2017-03-01
7	1	1	1	2017-02-02
8	1	4	1	2017-02-02
```
products — a table with product IDs, descriptions, and prices: ● 
```
product_id	description	price
1	thing-a-ma-jig	5
2	whatcha-ma-call-it	10
3	doo-hickey	7
4	gizmo	3
```

customers — a table with customer names and contact information: ● 
```
customer_id	customer_name	address	phone_number
1	John Smith	123 Main St.	212-123-4567
2	Jane Doe	456 Park Ave.	949-867-5309
3	Joe Schmo	798 Broadway	112-358-1321
```

If we just look at the orders table, we can’t really tell what’s happened in each  order. However, if we refer to the other tables, we can get a more complete  picture. 
Let’s examine the order with an order_id of 1. It was purchased by Customer 2.  To find out the customer’s name, we look at the customers table and look for  the item with a customer_id value of 2. We can see that Customer 2’s name is  Jane Doe and that she lives at 456 Park Ave. 
Doing this kind of matching is called merging two DataFrames.

### Inner Merge II 
It is easy to do this kind of matching for one row, but hard to do it for multiple  rows. 
Luckily, Pandas can efficiently do this for the entire table. We use  the .merge() method. 
The .merge() method looks for columns that are common between two  DataFrames and then looks for rows where those column’s values are the same.  It then combines the matching rows into a single row in a new table. We can call the pd.merge() method with two tables like this: 
```
new_df = pd.merge(orders, customers) 
```
This will match up all of the customer information to the orders that each  customer made. 
Ex: 
You are an analyst at Cool T-Shirts Inc. You are going to help them analyze  some of their sales data. 
There are two DataFrames defined in the file script.py: 
sales contains the monthly revenue for Cool T-Shirts Inc. It has two  
● 
columns: month and revenue. 
targets contains the goals for monthly revenue for each month. It has  
● 
two columns: month and target. 
Create a new DataFrame sales_vs_targets which contains the merge  of sales and targets. 
Cool T-Shirts Inc. wants to know the months when they crushed their targets. Select the rows from sales_vs_targets where revenue is greater than target.  Save these rows to the variable crushing_it. 
```
import codecademylib3 
import pandas as pd 
sales = pd.read_csv('sales.csv') 
print(sales) 
targets = pd.read_csv('targets.csv') 
print(targets) 
sales_vs_targets = pd.merge(sales, targets) print(sales_vs_targets) 
crushing_it = sales_vs_targets[sales_vs_targets.revenue  > sales_vs_targets.target] 
```

```
month	revenue	
0	January	300
1	February	290
2	March	310
3	April	325
4	May	475
5	June	495
```
```
	month	target
0	January	310
1	February	270
2	March	300
3	April	350
4	May	475
5	June	500

```


sales_vs_targets 
```
	month	revenue	target
0	January	300	310
1	February	290	270
2	March	310	300
3	April	325	350
4	May	475	475
5	June	495	500

```

crushing_it 
```
month	revenue	target	
1	February	290	270
2	March	310	300
```

### Inner Merge III 
In addition to using pd.merge(), each DataFrame has its own .merge() method.  For instance, if you wanted to merge orders with customers, you could use: 
```
new_df = orders.merge(customers) 
```
This produces the same DataFrame as if we had called pd.merge(orders,  customers). 
We generally use this when we are joining more than two DataFrames together  because we can “chain” the commands. The following command would 
merge orders to customers, and then the resulting DataFrame to products: 
```
big_df = orders.merge(customers)\ 
    .merge(products) 
```
Ex: 
We have some more data from Cool T-Shirts Inc. The number of men’s and  women’s t-shirts sold per month is in a file called men_women_sales.csv. Load  this data into a DataFrame called men_women. 
Merge all three DataFrames (sales, targets, and men_women) into one big  DataFrame called all_data. 
Display all_data using print. 
Cool T-Shirts Inc. thinks that they have more revenue in months where they sell  more women’s t-shirts. 
Select the rows of all_data where: 
revenue is greater than target ● 
AND 
women is greater than men ● 
Save your answer to the variable results. 
```
import codecademylib3 
import pandas as pd 
sales = pd.read_csv('sales.csv') 
print(sales) 
targets = pd.read_csv('targets.csv') 
print(targets) 
men_women = pd.read_csv("men_women_sales.csv") all_data = sales.merge(targets).merge(men_women) print(all_data) 
results = all_data[(all_data.revenue > all_data.target)  & (all_data.women > all_data.men)] 
```
sales
```
month	revenue	
0	January	300
1	February	290
2	March	310
3	April	325
4	May	475
5	June	495
```

targets
```
	month	target
0	January	310
1	February	270
2	March	300
3	April	350
4	May	475
5	June	500
```

all_data
```
	month	revenue	target	men	women
0	January	300	310	30	35
1	February	290	270	29	35
2	March	310	300	31	29
3	April	325	350	32	28
4	May	475	475	47	50
5	June	495	500	49	45
```
results
```
	month	revenue	target	men	women
1	February	290	270	29	35
```

### Merge on Specific Columns 
In the previous example, the .merge() function “knew” how to combine tables  based on the columns that were the same between two tables. For  instance, products and orders both had a column called product_id. This won’t  always be true when we want to perform a merge. 
Generally, the products and customers DataFrames would not have the  columns product_id or customer_id. Instead, they would both be called id and it  would be implied that the id was the product_id for the products table  and customer_id for the customers table. They would look like this: 

Customers 
```
id	customer_name	address	phone_number
1	John Smith	123 Main St.	212-123-4567
2	Jane Doe	456 Park Ave.	949-867-5309
3	Joe Schmo	798 Broadway	112-358-1321

```

Products
```
id	description	price
1	thing-a-ma-jig	5
2	whatcha-ma-call-it	10
3	doo-hickey	7
4	gizmo	3
```

**How would this affect our merges?** 
Because the id columns would mean something different in each table, our  default merges would be wrong. 
One way that we could address this problem is to use .rename() to rename the  columns for our merges. In the example below, we will rename the  column id to customer_id, so that orders and customers have a common  column for the merge. 
```
pd.merge( 
    orders, 
    customers.rename(columns={'id': 'customer_id'})) 
```
Ex: 
Merge orders and products using .rename(). Save your results to the  variable orders_products. 
Display orders_products using print. 
```
import codecademylib3 
import pandas as pd 
orders = pd.read_csv('orders.csv') 
print(orders) 
products = pd.read_csv('products.csv') 
print(products) 
orders_products = pd.merge(orders,  
products.rename(columns={'id':'customer_id'})) print(orders_products) 
```
orders
```
id	product_id	customer_id	quantity	timestamp	
0	1	3	2	1	2017-01-01
1	2	2	2	3	2017-01-01
2	3	1	3	1	2017-01-01
3	4	2	3	2	2016-02-01
4	5	3	3	3	2017-02-01
5	6	4	1	2	2017-03-01
6	7	1	1	1	2017-02-02
7	8	4	1	1	2017-02-02
```
products 
```
	id	description	price
0	1	thing-a-ma-jig	5
1	2	whatcha-ma-call-it	10
2	3	doo-hickey	7
3	4	gizmo	3
```

orders_products 
```
	id	product_id	customer_id	quantity	timestamp	description	price
0	1	3	2	1	2017-01-01	whatcha-ma-call-it	10
1	2	2	2	3	2017-01-01	whatcha-ma-call-it	10
2	3	1	3	1	2017-01-01	doo-hickey	7
3	4	2	3	2	2016-02-01	doo-hickey	7
4	5	3	3	3	2017-02-01	doo-hickey	7
5	6	4	1	2	2017-03-01	thing-a-ma-jig	5
6	7	1	1	1	2017-02-02	thing-a-ma-jig	5
7	8	4	1	1	2017-02-02	thing-a-ma-jig	5
```

### Merge on Specific Columns II 
In the previous exercise, we learned how to use .rename() to merge two  DataFrames whose columns don’t match. 
If we don’t want to do that, we have another option. We could use the  keywords left_on and right_on to specify which columns we want to perform  the merge on. In the example below, the “left” table is the one that comes first  (orders), and the “right” table is the one that comes second (customers). This  syntax says that we should match the customer_id from orders to the id in  customers. 
```
pd.merge( 
    orders, 
    customers, 
    left_on='customer_id', 
    right_on='id') 
```
If we use this syntax, we’ll end up with two columns called id, one from the first  table and one from the second. Pandas won’t let you have two columns with the  same name, so it will change them to id_x and id_y. 
It will look like this: 
```
id_x	customer_id	product_id	quantity	timestamp	id_y	customer_name	address	phone_number
1	2	3	1	2017-01-01 00:00:00	2	Jane Doe	456 Park Ave	949-867-5309
2	2	2	3	2017-01-01 00:00:00	2	Jane Doe	456 Park Ave	949-867-5309
3	3	1	1	2017-01-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
4	3	2	2	2016-02-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
5	3	3	3	2017-02-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
6	1	4	2	2017-03-01 00:00:00	1	John Smith	123 Main St.	212-123-4567
7	1	1	1	2017-02-02 00:00:00	1	John Smith	123 Main St.	212-123-4567
8	1	4	1	2017-02-02 00:00:00	1	John Smith	123 Main St.	212-123-4567
```

The new column names id_x and id_y aren’t very helpful for us when we read  the table. We can help make them more useful by using the keyword suffixes.  We can provide a list of suffixes to use instead of “_x” and “_y”. For example, we could use the following code to make the suffixes reflect the  table names: 
```
pd.merge( 
    orders, 
    customers, 
    left_on='customer_id', 
    right_on='id', 
    suffixes=['_order', '_customer'] 
) 
```
The resulting table would look like this: 
```
id_order	customer_id	product_id	quantity	timestamp	id_customer	customer_name	address	phone_number
1	2	3	1	2017-01-01 00:00:00	2	Jane Doe	456 Park Ave	949-867-5309
2	2	2	3	2017-01-01 00:00:00	2	Jane Doe	456 Park Ave	949-867-5309
3	3	1	1	2017-01-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
4	3	2	2	2016-02-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
5	3	3	3	2017-02-01 00:00:00	3	Joe Schmo	789 Broadway	112-358-1321
6	1	4	2	2017-03-01 00:00:00	1	John Smith	123 Main St.	212-123-4567
7	1	1	1	2017-02-02 00:00:00	1	John Smith	123 Main St.	212-123-4567
8	1	4	1	2017-02-02 00:00:00	1	John Smith	123 Main St.	212-123-4567
```
