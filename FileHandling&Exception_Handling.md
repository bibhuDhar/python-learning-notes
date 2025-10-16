# with open("./sample_data/sample.txt","r") as file:
  string = file.read();
  print(string)

This is read function which read the lines of sample.txt file and after printing it will show all the lines,suppose input is:

Hello World
Welcome to the Python World
File handling is easy and fun
Practice makes you a better coder
Good luck with your Python journey

after reading it will just print the lines as it is,

## with open("./sample_data/sample.txt","r") as file:
  string = file.readlines();
  print(string)

  readlines function just move the lines in a list and print them with \n

  output of the current file is: ['Hello World\n', 'Welcome to the Python World\n', 'File handling is easy and fun\n', 'Practice makes you a better coder\n', 'Good luck with your Python journey']


##print the number of line-
with open("./sample_data/sample.txt") as file:
  string = file.readlines()
  total_line = len(string)
  print(total_line)

  here it is printing the line number 5 because in the list it have stored five items 

##print the number of total words:


## Count the number of words
from functools import reduce
with open("./sample_data/sample.txt","r") as file:
  string = file.readlines()
  total_line = len(string)
  number_of_words = list(map(lambda x: len(x.split()),string))
  total_num_word = reduce(lambda x,y: x+y,number_of_words)
  print(total_num_word)
  

In string variable the file is stored as list 
For number of words we use map() that function every line in string after that len(x.split) return the numbers of word,after that to sum the list (to short the list) we reduce the list by summing

##Count the number of character in a word

str.strip() is used to remove the leading and trailling space from a string
suppose string = " Hello world "
print(string.strip()) : output = Hello world

from functools import reduce
with open("./sample_data/sample.txt","r") as file:
  string = file.readlines()
  string_list = list(map(str.strip,string))
  string_list = list(map(lambda x:x.replace(" ",""),string_list))
  print(string_list)
  number_char = list(map(lambda x: len(x),string_list))
  print(number_char)
  total_num = reduce(lambda x,y: x+y,number_char)
  print(total_num)

  Steps->
  1. use readlines() to make the lines item of list
  2. remove the newline character from each item by using strip
  3. remove the whispaces by using replace
  4. By using a function count the len of every item
  5. Finally use reduce function to add the numbers of the list

## There is a mode called w+,which can do read and write both.

with open("./sample_data/write_read.txt","w+") as file:
  file.write("Hello World")
  print(file.tell()) #file.tell() is indicating where the cursor is reading
  file.seek(0) #Moves the file pointer (cursor) to a specific position.
  print(file.read()) #Reads the contents of a file.
  print(file.tell())
  file.seek(0)
  print(file.tell())
  file.truncate(5)
  print(file.read())
