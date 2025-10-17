#Read the contents of a file
```
with open("./sample_data/sample.txt", "r") as file:
    string = file.read()
    print(string)

```
#Read lines into a list
```
with open("./sample_data/sample.txt", "r") as file:
    string = file.readlines()
    print(string)

```
#Print the number of lines
```
with open("./sample_data/sample.txt") as file:
    string = file.readlines()
    total_line = len(string)
    print(total_line)

```

#Count the total number of words
```
from functools import reduce

with open("./sample_data/sample.txt", "r") as file:
    string = file.readlines()
    total_line = len(string)
    number_of_words = list(map(lambda x: len(x.split()), string))
    total_num_word = reduce(lambda x, y: x + y, number_of_words)
    print(total_num_word)

```
#Count the total number of characters (without spaces)
```
string = " Hello world "
print(string.strip())  # Output: Hello world

```
#Full Program:
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
