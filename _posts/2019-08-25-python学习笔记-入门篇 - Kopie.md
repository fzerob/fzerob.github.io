---
layout:     post
title:      python
subtitle:   学习笔记
date:       2019-08-25
author:     fzerob
header-img: img/post-bg-python.JPG
catalog: true
tags:
    - python
    - 学习笔记
    - PyCharm
---

> About python learning，basic

## Sourse： 
* youtube video course，Derek Banas，English [《Python Programming》](https://www.youtube.com/watch?v=N4mEzFDjqtA)

### Install and Basics
1. Software: PyCharm
2. For comment
	
	\#: a hash for a single line
	
	''': three single quotes for multiple lines

3. difference about ', ", '''/"""

about ' and "

	str1 = 'We all know that \'A\' and \'B\' are two capital letters.'
	str2 = "We all know that 'A' and 'B' are two capital letters."

about '''
	
	1. comment
	2. multiple line
 
4. Five main types inside of python: number, string, list, tuple, dictionary

5. seven math operators: +, -, *, /, %, **(exponential calculation), //(perform a division and then discard the remainder all together and rotate down)
#
	e.g.
	print("5 / 2 = ", 5 / 2)
	print("5 % 2 = ", 5 % 2)
	print("5 ** 2 = ", 5 ** 2)
	print("5 // 2 = ", 5 // 2)
	print("-5 // 2 = ", -5 // 2)

	print("1+2-3*2", 1 + 2 - 3 * 2)

### Strings (8:12)
#### 1. define a string
##### a single line
	e.g. 
	quote = "\" Always remember you are unique!"
	or
	quote = '" Always remember you are unique!'

##### a multiple line
	multi_line_quote = '''just

	like everyone else'''
		
	or
	
	str1 = "List of name:\nHua Li\nChao Deng"
	print(str1)

	or str1 = """List of name:
	Hua Li
	Chao Deng
	"""
	print(str1)
	
Attention:
	str1 = "blabla"
	str1 = "asdfg"
	
	# There will be a space before str2
	print(str1, '\n', str2)
	
	# use parameter sep to control, default sep = ' ' (a space)
	print(str1, str2, sep="\n")


#### 2. join two strings together
	new_string = quote + multi_line_quote

	or

	print("%s %s %s" % ('I like the quote', quote, multi_line_quote))

	or

	print('\n' * 5)
	print("I don't like ", end="          ")
	print("newlines")

### Lists / Arrays
a list of number, each number has a index, which starts with 0	

#### 1. define a list
	grocery_list = ['Juice', 'Tomatoes', 'Potatoes', 'Bananas']
	print('First Item', grocery_list[0])
#### 2. change the item
	grocery_list[0] = "Green Juice"
	print('First Item', grocery_list[0])

#### 3. print item 
	
	print(grocery_list[1:3])
Attention: [3] not included -> just to remember

#### 4. store different lists in one matrix-list
	other_events = ['Wash Car', 'Pick up Kids', 'Cash Check']
	to_do_list = [other_events, grocery_list]
	
	print(to_do_list)
	print("second item of the second list:", to_do_list[1][1])

#### 5. append items
	grocery_list.append('Onions')
	print("append an item:", to_do_list)

#### 6. insert an item in a very specific index
	grocery_list.insert(1, "Pickle")
	print("insert the item in second index", to_do_list)

#### 7. remove an item
	grocery_list.remove("Pickle")
	print("remove the item 'Pickle'", to_do_list)

#### 8. sort the list
	grocery_list.sort()
	print("Sort", to_do_list)

#### 9. reverse the list
	grocery_list.reverse()
	print("reverse the second list", to_do_list)

#### 10. delete an item
	del grocery_list[4]
	print("delete the 5th item", to_do_list)

#### 11. store two list in one list
	to_do_list2 = other_events + grocery_list

#### 12. the new one list
	print("the new list:", to_do_list2)
#### 13. length of the list
	print("the length of new list:", len(to_do_list2))

#### 14. last alphabetically /first alphabetically (min)
	print("last alphabetically item of the list:", max(to_do_list2))
	print("first alphabetically item of the list:", min(to_do_list2))


> close look at string (27:03)

	long_string = "I'll catch you if you fall - The Floor"

	# print first 4 characters
	print(long_string[0:4])

	# print last 5 characters
	print(long_string[-5:])

	# print until last 5 characters
	print(long_string[:-5])
	
	# concatenate or join two strings
	print(long_string[:4] + " be there")
	
	# c-> character, s-> string, d -> integer, f -> float
	# for strings: printf-style String Formatting
	print("%c is my %s letter and my number %d number is %.5f" %('X', 'favorite', 1, .14))

	# capitalize the first letter of a string
	print(long_string.capitalize())
	
	# find Floor, must be exactly the same
	print(long_string.find("Floor"))
	
	# all character have been entered in a string
	print("all alpahbete:", long_string.isalpha())
	
	# everthing is a alphanumeric ?
	print("is all alphanumeric ", long_string.isalnum())
	
	# length of string
	print(len(long_string))

	# replace a specific word to another word
	print(long_string.replace("Floor", "Ground"))
	
	# want a strip white space
	long_string = "      12 vhruf"
	print(long_string)
	print(long_string.strip())
	
	# want to split a string into a list
	quote_list = long_string.split(" ")
	print(quote_list)

### Tuples (12:26)
>Very similar to lists. The difference about tuples and lists is: we are not going to be able to change a tuple after is created. If you want to change tuple: convert it to list then change!
	
	# define a tupe
	pi_tuple = (3, 1, 4, 1, 5, 9)
	
	# c onvert to list
	new_tuple = list(pi_tuple)

	# convert to tuple
	new_list = tuple(new_tuple)

	# also same as list to get length, min, max


### Dictionary or Map (13:39)
> A dictionary gonna be made up of values with a unique key for each value you're gonna be storing and they're very similar to lists be you can't join dictionary together like you can with lists with plus sign.

#### 1. define a dictionary
> use curly brace, square brackets: key -> value


	super_villains = {
    'Fiddler': 'Isaac Bowin',
    'Captain Cold': 'Leonard Snart',
    'Weather Wizard': 'Mark Mardon',
    'Mirror Master': 'Sam Scudder',
    'Pied Piper': 'Thomas Peterson'}

	print(super_villains['Captain Cold'])

#### 2. delete an entry -> key
	del super_villains['Fiddler']

#### 3. replace
	super_villains['Pied Piper'] = 'Hartley Rathway'

#### 4. find the number or length
	print(len(super_villains))

#### 5. get the value by passing in a key
	print(super_villains.get('Pied Piper'))

#### 6. get all the keys/the values of dictionary
	print("all the keys of the dictionary", super_villains.keys())
	print("all the values of the dictionary", super_villains.values())

### Conditionals
> to remember: one condition met, not going to check another
	age = 21
	if age > 16:
    	print("You are old enough to drive")
	else:
    	print("You are not old enough to drive")

	if age >= 21:
    	print("1")
	elif age >= 16:
    	print("2")
	else:
    	print("3")

> combine with logical operators: and, or not

	if ((age >= 1) and (age <= 18)):
    	print("123")
	elif (age == 21 or age >= 65):
    	print("234")
	elif not (age == 30):
    	print("345")
	else:
    	print("456")

### Looping (19:44)
#### For Loop
> for start from 0, up tp but not to 10
	
	# a range
	for x in range(0, 10):
    	print(x, ' ', end="")

	print("\n")

	# a list (grocery_list is a defined list)
	for y in grocery_list:
    	print(y, end=" ")

	for x in [2, 4, 6, 8, 10]:
    	print(x)

	print("\n")

	# a list of list
	num_list = [[1, 2, 3], [10, 20, 30], [100, 200, 300]]
	for x in range(0, 3):
    	for y in range(0, 3):
    	    print(num_list[x][y], end=" ")
    	print(end="\n")

#### While Loop
> use while: have no idea a head of time how many times you're going to loog
	
	!!! Do not forget: import random

	random_num = random.randrange(0, 100)

	while (random_num != 15):
    	print(random_num, end="*")
    	random_num = random.randrange(0, 100)

	i = 0
	while (i <= 20):
    	if (i % 2 == 0):
    	    print(i)
    	elif (i == 19):
    	    break
    	else:
    	    i += 1
    	    continue  # jump out of if, go back to while
    	i += 1

### Functions (19:44)
> Attention: parameter sumNum is out of the scope

	def addNumber(fNum, lNum):
    	sumNum = fNum + lNum
    	return sumNum


	print(addNumber(1, 4))
	string = addNumber(1, 4)


> system function

	print('What is your name?\n')
	
	# read from screen input
	!!! Do not forget: import sys
	name = sys.stdin.readline()
	print('Hello', name)

### File I/O or input/output

#### 1. creat and open a file
	# w for write
	test_file = open("test.txt", "wb")


#### 2. read the file mode
	print(test_file.mode)
	print(test_file.name)
	

#### 3. write sth in the file
	test_file.write(bytes("Write me to the file\n", 'UTF-8'))
	test_file.close()
	

#### 4. read the information from a file
	# r+ for read and write
	test_file = open("test.txt", "r+")
	test_in_file = test_file.read()
	print(test_in_file)
	

#### 5. delete the file
	!!! Do not forget: import os
	test_file.close()
	os.remove("test.txt")

### Classes / Objects include Constructors

> The concept of object oriented programming allows us to model real world things using code 
> 
> Real world object has attributes like color, height and weight.

> Real world object has abilities like walk talk and eat.

> Attributes using variables inside of things called classes

> Abilities are functions

	class Animal:
	    __name = None  # signifies a lack of a value or just quotes ""
	    __height = 0
	    __weight = 0
	    __sound = 0
	
	    # constructor: to set up or initialize an object
	    def __init__(self, name, height, weight, sound):
	        self.__name = name
	        self.__height = height
	        self.__weight = weight
	        self.__sound = sound
	
	    # __means they are private: if we want to change the value of this parameters
	    # we need to need a function inside of the class
	
	    # called encapsulation
	    def set_name(self, name):
	        self.__name = name
	
	    def set_height(self, height):
	        self.__height = height
	
	    def set_weight(self, weight):
	        self.__weight = weight
	
	    def set_sound(self, sound):
	        self.__sound = sound
	
	    def get_name(self):
	        return self.__name
	
	    def get_height(self):
	        return self.__height
	
	    def get_weight(self):
	        return self.__weight
	
	    def get_sound(self):
	        return self.__sound
	
	    def get_type(self):
	        print("Animal")
	
	    def toString(self):
	        return "{} is {} cm tall and {} kilograms and say {}".format(self.__name, self.__height, self.__weight, self.__sound)
	
	
	cat = Animal('Whiskers', 33, 10, 'Meow')
	
	print(cat.toString())
	
### Inheritance include "Overwriting Functions" and "Overloading Functions"
	class Dog(Animal):
    	__owner = ""

	    # overwrite
	    def __init__(self, name, height, weight, sound, owner):
	        super(Dog, self).__init__(name, height, weight, sound)
	
	        self.__name = name
	        self.__height = height
	        self.__weight = weight
	        self.__sound = sound
	        self.__owner = owner
	
	    def set_owner(self, owner):
	        self.__owner = owner
	
	    def get_owner(self):
	        return self.__owner
	
	    def get_type(self):
	        print("Dog")
	
	    def toString(self):
	        return "{} is {} cm tall and {} kilograms and say {} His owner is {}".format(self.__name, self.__height, self.__weight, self.__sound, self.__owner)
	
	    def multiple_sounds(self, how_many=None):
	        if how_many is None:
	            print(self.get_sound())
	        else:
	            print(self.get_sound() * how_many)
	

	spot = Dog("Spot", 53, 27, "Ruff", "Derek")
	print(spot.toString())

### Polymorphism
	
	class AnimalTesting:
	    def get_type(self, animal):
	        animal.get_type()
	
	test_animals = AnimalTesting()
	
	test_animals.get_type(cat)
	test_animals.get_type(spot)
	
	spot.multiple_sounds(4)
	spot.multiple_sounds()