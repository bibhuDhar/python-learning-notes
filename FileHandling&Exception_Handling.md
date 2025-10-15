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
