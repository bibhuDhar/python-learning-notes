# Read the contents of a file
```
with open("./sample_data/sample.txt", "r") as file:
    string = file.read()
    print(string)

```
# Read lines into a list
```
with open("./sample_data/sample.txt", "r") as file:
    string = file.readlines()
    print(string)

```
# Print the number of lines
```
with open("./sample_data/sample.txt") as file:
    string = file.readlines()
    total_line = len(string)
    print(total_line)

```

# Count the total number of words
```
from functools import reduce

with open("./sample_data/sample.txt", "r") as file:
    string = file.readlines()
    total_line = len(string)
    number_of_words = list(map(lambda x: len(x.split()), string))
    total_num_word = reduce(lambda x, y: x + y, number_of_words)
    print(total_num_word)

```
# Count the total number of characters (without spaces)
```
string = " Hello world "
print(string.strip())  # Output: Hello world

```
# Full Program:
```
from functools import reduce

with open("./sample_data/sample.txt", "r") as file:
    string = file.readlines()
    string_list = list(map(str.strip, string))
    string_list = list(map(lambda x: x.replace(" ", ""), string_list))
    print(string_list)
    number_char = list(map(lambda x: len(x), string_list))
    print(number_char)
    total_num = reduce(lambda x, y: x + y, number_char)
    print(total_num)

```
Steps:

1.Use readlines() to read lines as list items.
2.Remove newline characters with strip().
3.Remove spaces with replace(" ", "").
4.Count the length of each string.
5.Use reduce() to add up all counts
#Read and Write using w+ mode
```
with open("./sample_data/write_read.txt", "w+") as file:
    file.write("Hello World")
    print(file.tell())   # Indicates current cursor position
    file.seek(0)         # Moves the cursor to the beginning
    print(file.read())   # Reads the content of the file
    print(file.tell())   # Shows new cursor position
    file.seek(0)
    print(file.tell())
    file.truncate(5)     # Trims file to 5 characters
    print(file.read())

```

# Exception
It is an error that occurs on run time
to solve this problem we use exception handling

#Exception Handling
Types of exception in python:
1.Arithmetic error (10/0)
By using try and accept block we can handle the problem dividing by zero:
```
a = int(input())
try:
  n = 10/0
except ZeroDivisionError:
  print("You can not divide a number by zero") 
```
here after taking input when we try to divide 10 by 0 the exception case except block handle the problem

# Handling Name error
``` 
try:
  x = y
except NameError as reason:
  print(reason)
```
Python first runs the code inside the try block.,But — y is not defined anywhere.
That means Python doesn’t know what y is.The except part catches that specific kind of error (NameError).as reason stores the error message inside the variable reason.This prints the error message that Python generated.

# Solving all exception with only Exception keyword

``` 
try:
  x = y
except Exception as reason:
  print(reason)
```
By using the Exception keyword we can handle all the exception cases whether we don't know the exception case

#Understanding try-except-else-finally in Python File Handling
``` 
try:
  file= open("./sample_data/data1.txt","r")
except Exception as reason:
  print(reason)
else:
  print(file.read())
finally:
  print("GPU is stopped")
```
In this code, Python first tries to open the file "./sample_data/data1.txt" in read mode inside the try block. If the file exists, no error occurs, so the else block runs and prints the file’s content. After that, the finally block executes, printing "GPU is stopped"—this block always runs, whether an error happens or not. However, if the file does not exist, Python raises an error (like FileNotFoundError), which is caught by the except Exception as reason block. That block prints the actual error message (stored in reason), and then, as always, the finally block still runs and prints "GPU is stopped".
