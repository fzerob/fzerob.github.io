---
layout:     post
title:      julia
subtitle:   study notes
date:       2019-09-08
author:     fzerob
header-img: img/post-bg-python.JPG
catalog: true
tags:
    - julia
    - study notes
    - VSCode
---

> About julia learning，basic

## Source

* youtube video course，Derek Banas，English
* [< Julia Tutorial >](https://www.youtube.com/watch?v=sE67bP2PnOo&t=2667s)

## Introduction

1. compile:

    julia julia-tut.jl

2. For comment

    \#: a hash for a single line

3. using module

    using Printf
    using Statistics

## Variables

> dynamically assigned and can be changed

    # error message
    s = 0
    s = "Dog"
    println(s)

> be able to assert data types

    function changeNum()
        x::Int8 = 8
        x = "Dog"
    end

    changeNum()

## Data Types

> Int8, Int16, Int32, Int64, Float32, Float64, UInt8, UInt16, etc

### float

> the accuracy is about 14 digits.
>
> Or use another data type to increase the precision, like BigFloat, BigInt

    bF = 1.11111111111111111111111111
    println(bF + 0.11111111111111)

### char and string

> define char using ''
>
> define string using ""

## Casting

    # going to store utf-8 unicode
    c2 = Char(120) 
    println(c2)

### cast from floats into integer

    i1 = UInt8(trunc(3.14))
    println(i1)

### cast from strings to floats

    f1 = parse(Float64,"1")
    println(f1)

### cast from strings to integers

    i2 = parse(Int8,"1")
    println(i2)

## Strings

    s1 = "just some random words\n"

### get length

    println(length(s1))

### get the first item in string

> index starts from 1

    println(s1[1])
    println(s1[end])
    println(s1[1:4])

### create a new string

#### concatenation

    s2 = string("Yukiteru", "Amano")
    println(s2)

> use * Symbol to concatenation

    s3 = string("Yukite" * "Amano")
    println(s3)

#### perform interpolation

    i3 = 2
    i4 = 3
    println("$i3 + $i4 = $(i3+i4)")

#### multiline string """

    s3 = """ I 
    have
    many
    lines
    """
    println(s3)

### do string comparisions

    println("Takau" > "Hiyama")

### find index of character

    println(findfirst(isequal('i'), "Keigo"))

### find substring

    println(occursin("key", "monkey"))

## Conditionals

> \> < >= <= == !=
>
> && || !

    age = 12

    if age >= 5 && age <=6
        println("You are in Kindergarten")
    elseif age >= 7 && age <=13
        println("You are in Middle School")
    elseif age >=14 && age <= 18
        println("You are in high School")
    else
        println("Stay Home")
    end

> a cool example

    @printf("true || false = %s\n", true || false ? "true" : "false")
    @printf("!true = %s\n", !true ? "true" : "false")

## Looping

### while looping

    i = 1
    while i < 20
        if(i % 2) == 0
            println(i)
            global i+=1
            continue
        end
        global i+=1

        if i>=10
            break
        end
    end

### for looping

    for i = 1:5
        println(i)
    end

    for i in [2,4,6]
        println(i)
    end

    for i = 1:5, j = 2:2:10
        println((i, j))
    end

## Arrays

### create an Arrays

> all elements are 0

    a1 = zeros(Int32, 2, 2)

> Create array of Int32s

    a2 = Array{Int32}(undef, 5)

> or floats

    a3 = Float64[]

> or an normal array

    a4 = [1,2,3]

    println(a4[1])
    println(a4[end])
    println(5 in (a4))

### find

#### find 2 in a4

    println(findfirst(isequal(2), a4))

#### find all matches using a generic function

    f(a) = (a >= 2) ? true : false
    println(findall(f, a4))

#### find out how many times a item passes a test

    println(count(f, a4))

### come in and get a row as well as column size

    a4 = [1,2,3]
    println(size(a4))
    println(length(a4))
    println(sum(a4))

### insert values: put values at a starting index by using splice

    splice!(a4, 2:1, [8,9])
    println(a4)

### remove

    splice!(a4, 2:3)
    println(a4)

### min and max

    println(maximum(a4))
    println(minimum(a4))

### calculation

    println(a4 * 2)
    println(a4)

### store multiple different data types of an Array

    a5 = [1, 3.14, "Hello"]

### cool things: store functions inside of an Array

    a6 = [sin, cos, tan]

    for n in a6
        println(n(0))
    end

### multi-dimensional Arrays

    a7 = [1 2 3; 4 5 6]

    for n = 1:2, m = 1:3
        @printf("%d ", a7[n, m])
    end

    println()

    println(a7[:,2])
    println(a7[2,:])

### array from a range

    a8 = collect(1:5)

    a9 = collect(2:2:10)

    for n in a9 println(n) end

### create a array with comprehension

    a10 = [n^2 for n in 1:5]
    println(a10)

### add values in an array

    push!(a10, 36)

### create multi-demensional array

    a11 = [n * m for n in 1:5, m in 1:5]
    println(a11)

### generate 5 * 5 random array with all these between 0 and 9

    a12 = rand(0:9, 5, 5)

    for n = 1:5
        for m = 1:5
            print(a12[n, m])
        end
        println()
    end

## Tuples

> most of the real functions work with Tuples except that
>
> Tuples values cannot be changed once they are defined

    t1 = (1,2,3,4)
    println(t1)
    println(t1[1])

    for i in t1
        println(i)
    end

    t2 = ((1,2),(3,4))
    println(t2[1][1])

    t3 = (sue = ("Sue", 1000), paul = ("Paul", 23))
    println(t3.sue)

## Dictionaries

> key values pairs, where the keys must be unique

### define

    d1 = Dict("pi" => 3.14, "e" => 2.718)
    println(d1["pi"])

### add

    d1["golden"] = 1.618

### delete

    delete!(d1,"pi")

    println(haskey(d1, "pi"))

### check if in

    println(in("pi" => 3.14))

    println(keys(d1))

    println(values(d1))

    for kv in d1
        println(kv)
    end

    for(key, value) in d1
        println(key, " : ", value)
    end

## Sets

> very similar to array, except everything must be unique

    st1 = Set(["Jim", "Pam", "Jim"])
    println(st1)

### add items

    push!(st1, "Michael")

### check individuell values

    println(in("Dwight", st1))

### combine sets into new sets

    st2 = Set(["Stanley", "Meredith"])
    println(union(st1, st2))

### find iterms in both sets

    println(intersect(st1, st2))

### items in the first sets but not in second sets

    println(setdiff(st1, st2))

## Functions

> a simple example

    getSum(x,y) = x + y

    x, y = 1, 2

    @printf("%d + %d = %d\n", x,y, getSum(x,y))

> second example

    function canIVote(age = 16)
        if age > 18
            println("Can Vote")
        else
            println("Cannot Vote")
        end
    end

    canIVote(20)

### change value

> this cannot change

    v1 = 5
    function changeV1(vi)
        v1 = 10
    end

    changeV1(v1)
    println(v1)

> solution: change change it to global

    function changeV1()
        global    v1 = 10
    end

    changeV1()
    println(v1)

### we donot know how many different arguments a function may getSum

    # or x, y, args...
    function getSum2(args...)
        sum = 0

        for a in args
            sum += a
        end

        println(sum)
    end

    getSum2(1,2,3,4)

### to return multiple different values

    function next2(val)
        return (val+1, val +2)
    end

    println(next2(4))

### do function that return Functions

    function makeMultiplier(num)
        return function(x) return x * num end
    end

    mult3 = makeMultiplier(3)
    println(mult3(6))

### handle different types of arguments

    function getSum3(num1::Number, num2::Number)
        return num1 + num2
    end

    function getSum3(num1::String, num2::String)
        return parse(Int32, num1) + parse(Int32, num2)
    end

    println("5 + 4 = ", getSum3(5, 4))
    println("5 + 4 = ", getSum3("5", "4"))

## Anonymous Functions

> a function without name, use in line

### map: going to apply function in each item

    v2 = map(x -> x*x, [1,2,3])
    println(v2)

### add arrays

    v3 = map((x,y)-> x +y, [1,2], [3,4])
    println(v3)

### reduce: use a function multiple times to finnally get one result

    v4 = reduce(+, 1:100)
    println(v4)

### the longest word in a sentence

    sentence = "This is a string"
    sArray = split(sentence)
    longest= reduce((x,y) -> length(x) > length(y) ? x : y, sArray)
    println(longest)

## Math

> numerous different math functions

    x = 5
    println(2x)

### . -> perform operations on arrays

    a13 = [1,2,3]
    println(a13 .* 3)

## Enums

    @enum Color begin
        red = 1
        blue = 2
        green = 3
    end

    favColor = green::Color

    println(favColor)

## Symbols

> immutable strings that represent variable as data
:Derek

    println(:Derek)

> dictionary

    d2 = Dict(:pi => 3.14, :e => 2.718) 
    println(d2[:pi])

## Structs

> structs are composite types or specifically a type that can
>
> contain many different fields
>
> to remember: this trucks are going to be immutable

    struct Customer
        name::String
        balance::Float32
        id::Int
    end

### if want to be mutable then

    mutable struct Customer
        name::String
        balance::Float32
        id::Int
    end


    bob = Customer("Bob Smith", 10.50, 1243)
    println(bob.name)

## Abstract Types

> can be instantiated likes structs
> but they can have subtypes

    abstract type Animal end


    struct Dog <: Animal 
        name:: String
        bark::String
    end

    struct Cat <: Animal
        name::String
        bark::String
    end

    bowser = Dog("Bowser", "Ruff")
    muffin = Dog("Muffin", "Meow")

    function makeSound(animal::Dog)
        println("$(animal.name) says $(animal.bark)")
    end

    function makeSound(animal::Cat)
        println("$(animal.name) says $(animal.bark)")
    end

    makeSound(bowser)
    makeSound(muffin)

## Exception Handling / User Input

    print("Enter a number")
    num1 = chomp(readline())

    print("Enter a number")
    num2 = chomp(readline())

    try 
        val = (parse(Int32, num1))/(parse(Int32, num2))

        if(val == Inf)
            error("Can't Divide by Zero")
        else
            println(val)
        end
    catch e
        println(e)
    end

## File IO

    open("random2.txt", "w") do file
        write(file, "Here is some random text\nIt is great")
    end # will automatically close it


    open("random2.txt", "r") do file
        data = read(file, String)
        println(data)
    end # will automatically close it

    open("random2.txt") do file
        for line in eachline(file)
            println(line)
        end
    end # will automatically close it

## Macros

> generate code for you before a program is run
> quote is to represent is the beginnning and the ending of you

    macro doMore(n, exp)
        quote
            for i = 1:$(esc(n))
                $(esc(exp))
            end
        end
    end

    @doMore(3, println("Hello"))


    macro doWhile(exp)
        @assert exp.head == :while
        esc(quote
        $(exp.args[2])
        $exp
    end)
    end

    z = 0
    @doWhile while z < 10
        global z +=1
        println(z)
    end
