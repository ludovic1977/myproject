---
author: Ludovic Perruchoud
categories:
- Theme Features
- R
- package
date: "2022-05-10"
draft: false
excerpt: The first course (4 in all) of the introduction to programming in Python and Java specialization is offered by the University of Pennsylvania. In this project, I propose to share with you the week 2 of 4 exam and its code. This exam is about the properties of numbers. Have a good discovery!
layout: single
subtitle:
tags:
- hugo-site
title: Coursera- Introduction to Python programming (completed)
---

---

### The purpose of this project is multiple: First, I would like to introduce you to this exam on the properties of numbers and perhaps for some to re-discover numbers in math. Then, I would like to present you the code allowing to generate for example the prime numbers. 

---

### Context:

This exam was conducted on Jupyter Notebook as well as the grading. The correction is done by executing the part of the code that we want to test, either it is displayed "Success" or it is mentioned the kind of error.  

I would like to point out that depending on the error or the difficulties encountered to pass this exam, help from an instructor is present. This valuable help does not give an answer in the form of a code, but it helped me to find the right answer.  
Another important point for each statement in the exam. You are asked to define a function. This way of doing things allows you to perhaps use that function further in another exam statement.

### 1st state : Returns a list of factors of the given number x.
```toml
def getFactors(x):
    """Returns a list of factors of the given number x.
    Basically, finds the numbers between 1 and the given integer that divide the number evenly.

    For example:
    - If we call getFactors(2), we'll get [1, 2] in return
    - If we call getFactors(12), we'll get [1, 2, 3, 4, 6, 12] in return
    """
    # your code here
    # Creation an empty list
    list_factor = []
    
    # Loop for with range
    for i in range(1,x+1):         # for each i in range (beginning to 1 until the number chosen x by user + 1)
        if (x % i == 0):           # if modulo x (number chosen by user ) is zero 
            list_factor.append(i)  # so append to list_factor the number i
        
    return list_factor             # otherwise we return to list_factor
   
```
### 2nd states: Returns whether or not the given number x is prime.
```toml
def isPrime(x):
    
    A prime number is a natural number greater than 1 that cannot be formed
    by multiplying two smaller natural numbers.

    For example:
    - Calling isPrime(11) will return True
    - Calling isPrime(71) will return True
    - Calling isPrime(12) will return False
    - Calling isPrime(76) will return False
    """
    
    # your code here
    
    # First statement if-else
    if x < 2:        # the first prime number is 2. Therefore, all numbers below 2 return false
        return False
    else:
        for n in range(2,x):
            if(x % n ==0):
                return False
            
        return True

```

### 3rd states: Returns whether or not the given number x is composite.
```toml
def isComposite(x):

    A composite number has more than 2 factors.
    A natural number greater than 1 that is not prime is called a composite number.
    Note, the number 1 is neither prime nor composite.

    For example:
    - Calling isComposite(9) will return True
    - Calling isComposite(22) will return True
    - Calling isComposite(3) will return False
    - Calling isComposite(41) will return False
    """
    
    # your code here  
   
    result= getFactors(x)    # use function getFactors to store un number x into result
                             # For example (if x=2): factors are 1 and 2
                             # 1 and 2 are store into liste -> [1,2]
    
    # Loop for in result
    for factor in result:       # for each factor in result        
        if (factor == 1):       # if the factor is the number 1 (As a reminder, the number 1 is not a composite and prime                                    number)
            x = len(result)-1   # we remove 1 from the number of factors in the number x 
        
            if x < 2:           # if the number of factors is less than 2
                return False    # this is not a number composite -> False
            else:               # otherwise
                return True     # it is a number composite -> True
       
```
### 4th states:  Returns whether or not the given number x is perfect.
```toml
def isPerfect(x):
    
    A number is said to be perfect if it is equal to the sum of all its
    factors (for obvious reasons the list of factors being considered does
    not include the number itself).

    Example: 6 = 3 + 2 + 1, hence 6 is perfect.
    Example: 28 is another example since 1 + 2 + 4 + 7 + 14 is 28.
    Note, the number 1 is not a perfect number.
    """
    
    # your code here
    result= getFactors(x)    # use function getFactors to store un number x into result
                             # For example (if x=2): factors are 1 and 2
                             # 1 and 2 are store into liste -> [1,2]
    y = sum(result)-result[-1]

    if (y !=x):
        return False
    else:
        return True
   
```
### 5th states: Returns whether or not the given number x is abundant.
```toml
def isAbundant(x):
    
    A number is considered to be abundant if the sum of its factors
    (aside from the number) is greater than the number itself.

    Example: 12 is abundant since 1+2+3+4+6 = 16 > 12.
    However, a number like 15, where the sum of the factors.
    is 1 + 3 + 5 = 9 is not abundant.
    """
    
    # your code here
    
    result= getFactors(x)    # use function getFactors to store un number x into result
                             # For example (if x=2): factors are 1 and 2
                             # 1 and 2 are store into liste -> [1,2]
    y = sum(result)-result[-1]
   
    if (y > x):
        return True
    else:
        return False

```

### 6th states: Returns whether or not a given number x is triangular.
```toml
def isTriangular(x):
    
    The triangular number Tn is a number that can be represented in the form of a triangular 
    grid of points where the first row contains a single element and each subsequent row contains 
    one more element than the previous one.
    
    We can just use the fact that the nth triangular number can be found by using a formula: Tn = n(n + 1) / 2.
    
    Example: 3 is triangular since 3 = 2(3) / 2
    3 --> 2nd position: (2 * 3 / 2)
    
    Example: 15 is triangular since 15 = 5(6) / 2
    15 --> 5th position: (5 * 6 / 2)
    """
    
    # your code here  
    list=[]
    for n in range(1,22):
        y = int((n*(n+1))/2)
        list.append(y)
              
    if x in list:
        return True
    else:
        return False
       
```

### 7th states: Returns whether or not a given number is Narcissistic.

```toml
def isNarcissistic(x):

    A positive integer is called a narcissistic number if it
    is equal to the sum of its own digits each raised to the
    power of the number of digits.

    Example: 153 is narcissistic because 1^3 + 5^3 + 3^3 = 1 + 125 + 27 = 153.
    Note that by this definition all single digit numbers are narcissistic.
    """
    
    # your code here
    
    y = str(x)
    
    if (int(y) < 10):
        return True
    
    else:
        sum = 0
        
        for i in y:
            sum = sum + int(i)**3
            
        if (sum == x):
            return True
        else:
            return False
    
```
