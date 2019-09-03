---
layout:     post
title:      python
subtitle:   study notes
date:       2019-08-25
author:     fzerob
header-img: img/post-bg-python.JPG
catalog: true
tags:
    - python
    - study notes
    - PyCharm
---

> About python learning，basic

## Source 1

* youtube video course，Derek Banas，English
* [< Python Programming >](https://www.youtube.com/watch?v=N4mEzFDjqtA)

## Source 2

* youtube video course，Derek Banas，English
* [< Python Tutorial 2019 >](https://www.youtube.com/watch?v=H1elmMBnykA&t=3988s)

## Introduction

1. Software: PyCharm / VSCode
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

## Data Types

Basic types inside of pyhton is going to be:

1. integers
2. floats
3. complex numbers
4. strings
5. booleans

### integers and floats

> To get the type of data

    print(type(10))

    a = "hello"
    print(type(a))

> There is no limit to the size of integers. But if you want to get a typical max size for integers

    print(sys.maxsize)

> float: to get a maximum size for a float

    print(sys.float_info.max)

> One thing important to be understood: floats are only going to be accurate up 15 digits

    f1 = 1.1111111111111111111
    f2 = 1.111111111111111111111

    f3 = f1+ f2
    print(f3)

### complex numbers

>complex numbers are going to be made up of a real part and a imaginary part: real part + imaginary part

    cn = 5 + 6j
    print(cn)

### booleans

    bl1 = True
    bl2 = False

### strings

    str1 = "use \" or '"
    print(str1)

> Strings are going to have things called escape sequences

    str1 = '\', ", \t, \\, \n'
    str2 = '''Trip quoted ' '' '''

    print('str1 = ',str1, '\nstr2 = ',str2)

> There is no character type inside python.

    print("Cast", type(int(4.5)))
    print("Cast", type(str(4.5)))

    # this output will be a string
    print("Cast", type(chr(97))) 
    print("Cast", type(ord('a')))

> We want to separate different parts with a forward slash.

    print(12, 21, 1974, sep = ' /')
    print("No Newline", end='')

> String formatting

    # decimal + leading zeros of at least four + string + flaoat, which has two decimal places precision + char

    print("\n%04d %s %.2f %c" % (1, "Derek", 1.234, 'A'))

## Math

Seven math operators: +, -, *, /, ** (exponential calculation), // (perform a division and then discard the remainder all together and rotate down)

    print("5 / 2 = ", 5 / 2)
    print("5 % 2 = ", 5 % 2)
    print("5 ** 2 = ", 5 ** 2)
    print("5 // 2 = ", 5 // 2)
    print("-5 // 2 = ", -5 // 2)

    print("1+2-3*2", 1 + 2 - 3 * 2)

> Different ways of performing calculations in a shortcut manner

    i1 = 2
    i1 +=1

    print("i1 = ", i1)

> *import math*: A ton of built-in math functions
> This module privided access to the math. functions defined by the C standard.
>  
> These functions cannot be used with complex numbers -> if you need, them module cmath.

### Random Values

    # creat a random value
    print("Random Integer", random.randint(0,100))

### Nan & Inf

> Infinity is just the infinity that you're used to math.inf: a floating-point positive infinity for negative use -math.inf

    print(math.inf > 0)

> NaN: not a number

    print(math.inf - math.inf)

## Strings

### 1. define a string

> a single line

    e.g. 
    quote = "\" Always remember you are unique!"
    # or
    quote = '" Always remember you are unique!'

> multiple lines

    multi_line_quote = '''just
    blabla
    like everyone else'''

    # or

    str1 = "List of name:\nHua Li\nChao Deng"
    print(str1)

    #or 
    str1 = """List of name:
    Hua Li
    Chao Deng
    """
    print(str1)

### 2. join two strings together

> Methode 1

    str1 = "blabla"
    str1 = "asdfg"
 
    # There will be a space before str2
    print(str1, '\n', str2)
    
    # use parameter sep to control, default sep = ' ' (a space)
    print(str1, str2, sep="\n")

> Methode 2

    new_string = quote + multi_line_quote

    # or

    print("%s %s %s" % ('I like the quote', quote, multi_line_quote))

    # or

    print('\n' * 5)
    print("I don't like ", end="          ")
    print("newlines")

### 3. functions for strings

> length

    str3 = 'Hello You'
    print("Length", len(str3))

> change index value

    # 0 for first
    # -1 for last
    # 0:3 for first three 
    # 0:-1 for from the first to the last
    # 0:-1:2 for skip 1
    
    print("1st", str3[-1])

> Attention: you can't change an index value by str3[0] = 'e', but you can use:

    str3 = str3.replace("Hello", "Goodbye")

> change the value of index 8

    str3 = str3[:8] + "y" + str3[9:]
    print(str3)

> test if a string in or not in a string

    print("you" in str3)
    print("You" not in str3)

> find the first index for a match

    print("You index", str3.find("you"))

> trim white space (both sides)

    # if cannot find, will print -1
    print("      Hello   ", str3.strip("You")) 

    # left trim lstrip or right trim rstrip

> convert a list into a string and then separate it with spaces

    print("#".join(["Some", "Words"]) )

> convert a string into a list, define a separator or delimiters

    print("a string".split(" "))

> format the output with sth called f-Format

    int1 = int2 = 5
    print(f'{int1} + {int2} = {int1 + int2}')

> convert form uppercase to lowercase

    print("A string".upper())
    print("A string".lower())

> check items

    print("A string123".isalnum())
    print("A string".isalpha())
    print("A string".isdigit())

## Lists / Arrays

Lists contain mutable pieces of data of varying data types or even functions: mutable/immutable

Each number has a index, which starts with 0.

### 1. define a list

    # e.g. 1: only strings
    grocery_list = ['Juice', 'Tomatoes', 'Potatoes', 'Bananas']

    print('First Item', grocery_list[0])

    # e.g. 2: a mixture
    l1 = [1, 3.14, "Derek", True]

    print("length", len(l1))
    print("1st:", l1[0])
    print("last:", l1[-1])

    # e.g.3 use Ranges

    # to create a list
    print(list(range(0,5)))

    # add a step
    print(list(range(0, 10, 2)))

### 2. change the item

    # e.g. 1
    grocery_list[0] = "Green Juice"
    print('First Item', grocery_list[0])

    #e.g.2
    l1[0] = 2
    l1[2:4] =  ["Bob", False]

    print(l1)

### 3. print item

> Attention: [3] not included -> just to remember

    print(grocery_list[1:3])

### 4. store different lists in one matrix-list

    other_events = ['Wash Car', 'Pick up Kids', 'Cash Check']
    to_do_list = [other_events, grocery_list]

    print(to_do_list)
    print("second item of the second list:", to_do_list[1][1])

### 5. append items

    grocery_list.append('Onions')
    print("append an item:", to_do_list)

### 6. insert an item in a very specific index

    # e.g.1
    grocery_list.insert(1, "Pickle")
    print("insert the item in second index", to_do_list)

    # e.g.2
    ## insert an index without deleting
    l1[2:2] = ["Paul", 9, "ANna"]
    print(l1)

    l1.insert(2, "Paul") # only one
    print(l1)

    # add new list at the end of the list
    l2 = l1 + ["Egg", 4]
    print(l2)

    # add to the beginning
    l2 = ["Egg", 4] + l1
    print(l2)

### 7. remove an item

    e.g.1
    grocery_list.remove("Pickle")
    print("remove the item 'Pickle'", to_do_list)

    e.g.2
    l2.remove("Paul" )
    print(l2)

    # remove at in index
    l2.pop(0)
    print(l2)

### 8. sort the list

    grocery_list.sort()
    print("Sort", to_do_list)

### 9. reverse the list

    grocery_list.reverse()
    print("reverse the second list", to_do_list)

### 10. delete an item

    del grocery_list[4]
    print("delete the 5th item", to_do_list)

### 11. store two list in one list

    to_do_list2 = other_events + grocery_list
    print("the new list:", to_do_list2)

### 13. length of the list

    print("the length of new list:", len(to_do_list2))

### 14. last alphabetically /first alphabetically (min)

    # e.g.1
    print("last alphabetically item of the list:", max(to_do_list2))
    print("first alphabetically item of the list:", min(to_do_list2))

    # e.g.2
    print("Min: ", min([1, 2, 3]))
    print("Max: ", max([1, 2, 3]))
    print("1st 2: ", l1[0:2])
    print("Every Other: ", l1[0:-1:2]) # this one is good
    print("Reverse: ", l1[::-1])

### 15. close look at string (27:03)

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

    # check if a value exists (multiple doesn't work)
    print("1 exists", (1 in l1))
    
    # whiele loop
    l4 = [1,2,5,"Derek"]
    while len(l4):
        print(l4.pop(0))

    # for loops
    for x in range(0, 10):
        print(x, " ", end = "")

    l4 = [1,2,5,"Derek"]

    for x in l4:
        print(x)

### interators

Python allow you to pass an object to a function called ITER. Iterator, which return an interator which is going t oallow you to cycle through values

    # not really understand
    l5 = [6, 9, 12]
    itr = iter(l5) 

    print(next(itr))
    print(next(itr))

## Tuples

Tuples are just like lists except they are immutable. Anything you can do with lists you can du with tuples. If you want to change tuple: convert it to list then change!

    # define a tupe
    pi_tuple = (3, 1, 4, 1, 5, 9)
    
    # convert to list
    new_tuple = list(pi_tuple)

    # convert to tuple
    new_list = tuple(new_tuple)

    # also same as list to get length, min, max

## Dictionary or Map

A dictionary gonna be made up of values with a unique key for each value you're gonna be storing and they're very similar to lists be you can't join dictionary together like you can with lists with plus sign.

### 1. define a dictionary

> Way 1:

    super_villains = {
    'Fiddler': 'Isaac Bowin',
    'Captain Cold': 'Leonard Snart',
    'Weather Wizard': 'Mark Mardon',
    'Mirror Master': 'Sam Scudder',
    'Pied Piper': 'Thomas Peterson'}

    print(super_villains['Captain Cold'])

    # or
    heroes = {
        "superman": "Clark Kent",
        "batman": "Bruce Wayne"
    }

> Way 2:

    #https://www.programiz.com/python-programming/dictionary
    # empty dictionary
    my_dict = {}
    # dictionary with integer keys
    my_dict = {1: 'apple', 2: 'ball'}
    # dictionary with mixed keys
    my_dict = {'name': 'John', 1: [2, 4, 3]}
    # using dict()
    my_dict = dict({1:'apple', 2:'ball'})
    # from sequence having each item as a pair
    my_dict = dict([(1,'apple'), (2,'ball')])

### 2. delete

    # use key 
    del super_villains['Fiddler']

    # delete and return
    print(heroes.pop("batman"))

### 3. add new key

    heroes["Flash"] = "Barry Allan"

### 4. replace/change the value

    super_villains['Pied Piper'] = 'Hartley Rathway'

### 5. find the number or length

    print(len(super_villains))

### 6. get the value by passing in a key

    print(super_villains.get('Pied Piper'))

### 7. get all the keys/the values of dictionary

    print("all the keys of the dictionary", super_villains.keys())
    print("all the values of the dictionary", super_villains.values())

    # get the keys or values
    print(list(heroes.keys()))
    print(list(heroes.values()))

    # get a list of tuples from a dictionary
    print(list(heroes.items()))

### 8. search, to see if a key is included

    print("superman" in heroes)

### 9. print

    for k in heroes:
        print(k)


    for k in heroes.values():
        print(k)

> formatted printing with sth called dictionary mapping

    d1 = {
        "name": "Bread",
        "price": .88
    }

    print("%(name)s costs $%(price).2f" % d1) # important

## set

A set is going to be a list that is unordered, only has unique values and while values can change those values themselfves must be immutable.

### 1. Define

    s1 = set(["Derek", 1])
    s2 = {"Paul", 1}

### 2. size

    print("Length", len(s1))

### 3. join set

    s3 = s1 | s2
    print(s3)

    s3.add("Doug")

### 4. remove value

    s3.discard("Derek")

> remove a random value, because it is an unordered list

    print("Random", s3.pop()) 
    print(s3)

> please remember, that everything is going to be unique

    s3 |= s2

> be able to come in and return common values

    print(s1.intersection(s2))

### 5. get all unique values

    print(s1.symmetric_difference(s2))

### 6. get values in s1 but not in s2

    print(s1.difference(s2))

### 7. clear the set

    s3.clear()
    print("after clear", s3)

### 8. a frozen set: cannot be change in any way

    s4 = frozenset(["Paul",7])

## Conditionals

> to remember: one condition met, not going to check another

    e.g.1
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

    e.g.2
    age = 19
    canVote = True if age >= 18 else False
    print(canVote)

> combine with logical operators: and, or not

    if ((age >= 1) and (age <= 18)):
        print("123")
    elif (age == 21 or age >= 65):
        print("234")
    elif not (age == 30):
        print("345")
    else:
        print("456")

## Looping

### For Loop

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

### While Loop

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

## Functions

> Attention: parameter sumNum is out of the scope

    e.g.1
    def addNumber(fNum, lNum):
        sumNum = fNum + lNum
        return sumNum

    print(addNumber(1, 4))
    string = addNumber(1, 4)

    e.g.2
    # num1:int: function annotation, no need
    # int = i: to provide a default value, no need
    def get_sum(num1: int = 1, num2: int = 1):
        return num1 + num2

    print(get_sum(5, 4))

> accept multiple values in which we have no idea how many there is gonna be

    def get_sum2(*args):
        sum = 0
    
        for arg in args:
            sum += arg
        return sum

    print(get_sum2(1,2,3,4))

> return multiple values

    def next_2(num):
        return num+1, num +2

    i1, i2 =  next_2(5)
    print(i1, i2)

> make a function that makes a function that multiplies by a given value

    def mult_by(num):
        #anonymous or an unnamed function
        return lambda x: x - num

    print("3*5=", mult_by(3)(5))

> pass a function to a function

    def mult_list(list, func):
        for x in list:
            print(func(x))

    mult_by_4 = mult_by(4)
    mult_list(list(range(0,5)), mult_by_4)

> a lsit of function

    power_list = [lambda x: x**2,
                lambda x: x**3,
                lambda x: x**4]

> system function

    print('What is your name?\n')
    
    # read from screen input
    !!! Do not forget: import sys
    name = sys.stdin.readline()
    print('Hello', name)

### Map

you can use a map to execute a function on a list

    one_to_4 = range(1,5)
    times2 = lambda x: x*2
    print(list(map(times2, one_to_4))) # not really understand

### Filter

allow you to select items based of a function or a condition

> print out the even values from a list

    print(list(filter((lambda x: x%2 == 0), range(1, 11))))

### Reduce

receive a list and return a single result

    print(reduce((lambda x, y: x+y), range(1,6)))

## Exception Handling

going to handle errors that would otherwise crash your program

    while True:
        try:
            number = int(input("Please enter a number: "))
            break
        except ValueError:
            print("You didn't enter a number")
        except:
            print("An unknown error occurred")
    print("Thank you")

## File I/O or input/output

### 1. creat and open a file

    # w for write
    test_file = open("test.txt", "wb")

### 2. read the file mode

    print(test_file.mode)
    print(test_file.name)

### 3. write sth in the file

    test_file.write(bytes("Write me to the file\n", 'UTF-8'))
    test_file.close()

### 4. read the information from a file

    # r+ for read and write
    test_file = open("test.txt", "r+")
    test_in_file = test_file.read()
    print(test_in_file)

### 5. delete the file

    !!! Do not forget: import os
    test_file.close()
    os.remove("test.txt")

### e.g.2

    with open("mydata.txt", mode = "w", encoding="utf-8") as my_file:
        my_file.write("Some random text\nMore random text\nand more")

    with open("mydata.txt", encoding="utf-8") as my_file:
        print(my_file.read())

    print(my_file.closed)

## Classes / Objects include Constructors

The concept of object oriented programming allows us to model real world things using code.
Real world object has attributes like color, height and weight. Real world object has abilities like walk talk and eat. Attributes using variables inside of things called classes. Abilities are functions

    e.g.1
    class Square:
        # create the initiation function and this is going to be called
        # every single time you try to call or create a new
        # square object 
        # put 0 there as default just in case the user does not
        # enter anything
    
        def __init__(self, height="0",width="0"):

        # if we want to refer to our object
        # because we create square objects we don't know what 
        # the user is going to name them
        # so if you want to refer to the object itself, 
        # you use the word "self"
            self.height = height
            self.width = width
        
        # if we want to protect or provide some type of special
        # output every time the user tries to get information 
        # create a getter function
        @property
        def height(self):
            print("Retrieving the height")
            return self.height

        # Getters / Setters    
        @height.setter
        def height(self, value):
            if value.isdigit():
                self.__height = value
            else:
                print("Please only enter numbers for height.")
        
        @property
        def width(self):
            print("Retrieving the width")
            return self.width
        
        @width.setter
        def width(self, value):
            if value.isdigit():
                self.__width = value
            else:
                print("Please only enter numbers for height.")

        def get_area(self):
            return int(self.__width) * int(self.__width)

    square = Square()

    square.height = "10"
    square.width = "10"

    print(square.get_area())

### Inheritance & Polymorphism

    class Animal:
        def __init__(self, name = "unknown", weight = 0):
            self.__name = name
            self.__weight = weight

        @property
        def name(self, name):
            self.__name = name
        
        def make_noise(self):
            return "Grrrrr" # as default
        
        # cast a object to a string type you can define
        def __str__(self):
            return "{} is a {} and says {}".format(self.__name, type(self).__name__, self.make_noise())

    # magic methods used for operator overloading which
        # how to evaluat a animal objectis greater than another animal object

        def __gt__(self, animal2):
            if self.__weight > animal2.__weight:
                return True
            else:
                return False

    class Dog(Animal):
        def __init__(self, name = "unknown", owner = "unknown", weight = 0):
            Animal.__init__(self, name, weight)
            self.__owner = owner
        
        # overwirte the string function
        def __str__(self):
            return super().__str__() + " and is owned by " + \
                self.__owner

    animal = Animal("Spot", 100)
    print(animal)

    dog = Dog("Bower", "Bob", 150)
    print(dog)

    print(animal > do

### e.g.2

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

### Threads

A thread is just a block of code and whenever we are going to be using them way
need the module random and threading

    # a function
    def execute_thread(i):
        # a function called string F time or string
        # formatted time
        # allow you to define how time is going to be 
        # displayed
        # strftime("%Y-%m-%d %H:%M:%S", time.gmtime())
        print("Thread {} sleeps at {}.".format(i, time.strftime("%Y-%m-%d %H:%M:%S", time.gmtime())))

        random_sleep_time = random.randint(1, 5)
        time.sleep(random_sleep_time)

        print("Thread {} stops sleeping at {}".format(i, time.strftime("%Y-%m-%d %H:%M:%S", time.gmtime())))

    for i in range(10):
        # here must be a comma, because the arguments passed in must be a sequence
        thread = threading.Thread(target = execute_thread, args = (i,))
        thread.start()
        print("Active Thread:", threading.activeCount())
        print("Thread Objects: ", threading.enumerate())

> the thread is going to be opened in order and they are going to sleep for a random period of time

### Regular Expressions

allow you to locate and change strings in ridiculously powerful ways almost every programming language same

    import re

    # 
    if re.search("ape", "The ape at the apex"):
        print("There is an ape")

    # want to get every single match
    allApes = re.findall("ape", "The ape at apex")

    for i in allApes:
        print(i)

    # get an interator for all of the matching
    # objects

    the_str = "The ape at the apex"
    # . means I'm looking for for a followed by
    # a single character
    for i in re.finditer("ape.", the_str):
        # return the tuple
        loc_tuple = i.span()
        print(loc_tuple)
        print(the_str[loc_tuple[0]:loc_tuple[1]])

## Connect to Databases

interact with an SQL light 3 database using python a database is even better than storing a simple file because it's gonna make it very easy for you to organize your data for storage as well as fast searching we're gonna need

    # a couple more modules here
    import sqlite3
    import csv

    # function, retrieve data from a table using select
    # another tutorial for DB
    def print_DB():
        try:
            result = theCursor.execute("SELECT id, Fname, LName, Age, Address, Salary, HireDate FROM Employees")
            for row in result:
                print("ID: ", row[0])
                print("FName: ", row[1])
                print("LName: ", row[2])
                print("Age: ", row[3])
                print("Address: ", row[4])
                print("Salary: ", row[5])
                print("HireDate: ", row[6])
        except sqlite3.OperationalError:
            print("The table doesn't exist")
        except:
            print("Couldn't get data")

    # create the db 
    # db name: if it doesn't exist, it will be created
    # file is going to be stored in the same directory
    db_conn = sqlite3.connect('test.db')
    print("Database Created")

    #cusor is gonna be used to traverse the records of a result
    theCursor = db_conn.cursor()

    # add a new employee to our database
    #first to do is to create a table
    try:
        db_conn.execute("CREATE TABLE Employees(ID INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL, FName TEXT NOT NULL, LName TEXT NUT NULL, Age INT NOT NULL, Address TEXT, Salary REAL, HireDate TEXT);")    
        db_conn.commit()
        print("Table created")

    except sqlite3.OperationalError:
        print("Table Not Created")

    db_conn.execute("INSERT INTO Employees (FName, LName, Age, Address, Salary, HireDate)" "VALUES ('Derek', 'Banas', 41, '123 Main St', '500,000', date('now'))")
    db_conn.commit()
    print_DB()
    db_conn.close()

## Recursive Functions and Modules

    import myfunc
    # or
    # from myfunc import Development
    print(myfunc.factorial(4))

## GUI Development TkInter

    from tkinter import *
    from tkinter import ttk

    class Calculator:
        calc_value = 0.0

        div_trigger = False
        mult_trigger = False
        add_trigger = False
        sub_trigger = False

        # Called anytime a number button is pressed
        def button_press(self, value):
            
            # Get the current value in the entry
            entry_val = self.number_entry.get()
            
            # Put the new value to the right of it
            # If it was 1 and 2 is pressed it is now 12
            # Otherwise the new number goes on the left
            entry_val += value
            
            # Clear the entry box
            self.number_entry.delete(0, "end")
            
            # Insert the new value going from left to right
            self.number_entry.insert(0, entry_val)
        
        # Returns True or False if the string is a float
        def is_float(self, str_val):
            try:
                # If the string isn't a float float() will throw a
                # ValueError
                float(str_val)
                return True
            except ValueError:
                return False
        
        # Handles logic when math buttons are pressed
        def math_button_press(self, value):

            if self.is_float(str(self.number_entry.get())):
            
                self.add_trigger = False
                self.sub_trigger = False
                self.mult_trigger = False
                self.div_trigger = False
                self.calc_value = float(self.entry_val.get())

                if value == "/":
                    print("/ Pressed")
                    self.div_trigger = True
                elif value == "*":
                    print("* Pressed")
                    self.mult_trigger = True
                elif value == "+":
                    print("+ Pressed")
                    self.add_trigger = True
                else:
                    print("- Pressed")
                    self.sub_trigger = True
                
                # clear the entry box
                self.number_entry.delete(0, "end")

        # Performs a mathematical operation by taking the value before
        # the math button is clicked and the current value. Then perform
        # the right calculation by checking what math button was clicked
        # last
        def equal_button_press(self):

            # Make sure a math button was clicked
            if self.add_trigger or self.sub_trigger or self.mult_trigger or self.div_trigger:
                if self.add_trigger:
                    solution = self.calc_value + float(self.entry_val.get())
                elif self.sub_trigger:
                    solution = self.calc_value - float(self.entry_val.get())
                elif self.mult_trigger:
                    solution = self.calc_value * float(self.entry_val.get())
                else:
                    solution = self.calc_value / float(self.entry_val.get())
                
                print(self.calc_value, " ", float(self.entry_val.get()), " ", solution)

                # clear the entry box
                self.number_entry.delete(0, "end")
                self.number_entry.insert(0, solution)
            
        def __init__(self, root):

            # Will hold the changing value stored in the entry
            self.entry_val = StringVar(root, value="")

            # define the title for the app
            root.title("Caculator")

            # define the size of the window
            root.geometry("530x220")
            
            # Block the resizing of window
            root.resizable(width = False, height = False)

            # Customize the styling for the buttons and entry
            style = ttk.Style()
            style.configure("TButton",
                            font="Serif 15",
                            padding = 10)

            style.configure("TEntry",
                            font="Serif 18",
                            padding = 10)
            
            # Create the text entry box
            self.number_entry = ttk.Entry(root,
                            textvariable=self.entry_val,width = 50)
            
            self.number_entry.grid(row=0, columnspan=4)
            
            # 1st Row
            self.button7 = ttk.Button(root, text="7", command = lambda: self.button_press('7')).grid(row=1, column = 0)
            self.button8 = ttk.Button(root, text="8", command = lambda: self.button_press('8')).grid(row=1, column = 1)
            self.button9 = ttk.Button(root, text="9", command = lambda: self.button_press('9')).grid(row=1, column = 2)
    
            self.button_div = ttk.Button(root, text="/", command=lambda: self.math_button_press('/')).grid(row=1, column=3)
    
            # ----- 2nd Row -----
    
            self.button4 = ttk.Button(root, text="4", command=lambda: self.button_press('4')).grid(row=2, column=0)
    
            self.button5 = ttk.Button(root, text="5", command=lambda: self.button_press('5')).grid(row=2, column=1)
    
            self.button6 = ttk.Button(root, text="6", command=lambda: self.button_press('6')).grid(row=2, column=2)
    
            self.button_mult = ttk.Button(root, text="*", command=lambda: self.math_button_press('*')).grid(row=2, column=3)
    
            # ----- 3rd Row -----
    
            self.button1 = ttk.Button(root, text="1", command=lambda: self.button_press('1')).grid(row=3, column=0)
    
            self.button2 = ttk.Button(root, text="2", command=lambda: self.button_press('2')).grid(row=3, column=1)
    
            self.button3 = ttk.Button(root, text="3", command=lambda: self.button_press('3')).grid(row=3, column=2)
    
            self.button_add = ttk.Button(root, text="+", command=lambda: self.math_button_press('+')).grid(row=3, column=3)
    
            # ----- 4th Row -----
    
            self.button_clear = ttk.Button(root, text="AC", command=lambda: self.button_press('AC')).grid(row=4, column=0)
    
            self.button0 = ttk.Button(root, text="0", command=lambda: self.button_press('0')).grid(row=4, column=1)
    
            self.button_equal = ttk.Button(root, text="=", command=lambda: self.equal_button_press()).grid(row=4, column=2)
    
            self.button_sub = ttk.Button(root, text="-", command=lambda: self.math_button_press('-')).grid(row=4, column=3)

    # Get the root window object
    root = Tk()

    # Create the calculator
    calc = Calculator(root)

    # Run the app until exited
    root.mainloop()
