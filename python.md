
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

