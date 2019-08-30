# Exercise 6

### Exercise 6A

_Draw a stack diagram for the following program. What does the program print?_

```text
def b(z):
    prod = a(z, z)
    print(z, prod)
    return prod

def a(x, y):
    x = x + 1
    return x * y

def c(x, y, z):
    total = x + y + z
    square = b(total)**2
    return square

x = 1
y = x + 1
print(c(x, y+3, x+y))
```

### Exercise 6B

_The Ackermann function,_ A\(m, n\)_, is defined:_

![Ackermann function](../.gitbook/assets/image%20%281%29.jpeg)

_See_ [_http://en.wikipedia.org/wiki/Ackermann\_function_](http://en.wikipedia.org/wiki/Ackermann_function)_. Write a function named ackthat evaluates the Ackermann function. Use your function to evaluate ack\(3, 4\), which should be 125. What happens for larger values of m and n? Solution:_ [_http://thinkpython2.com/code/ackermann.py_](http://thinkpython2.com/code/ackermann.py)_._

### Exercise 6_C_

_A palindrome is a word that is spelled the same backward and forward, like “noon” and “redivider”. Recursively, a word is a palindrome if the first and last letters are the same and the middle is a palindrome._

_The following are functions that take a string argument and return the first, last, and middle letters:_

```text
def first(word):
    return word[0]

def last(word):
    return word[-1]

def middle(word):
    return word[1:-1]
```

_We’ll see how they work in Chapter_ [_8_](http://greenteapress.com/thinkpython2/html/thinkpython2009.html#strings)_._

1. _Type these functions into a file named palindrome.py and test them out. What happens if you call middle with a string with two letters? One letter? What about the empty string, which is written `''` and contains no letters?_
2. _Write a function called `is_palindrome` that takes a string argument and returns Trueif it is a palindrome and False otherwise. Remember that you can use the built-in function len to check the length of a string._

### Exercise 6D

_A number,_ a_, is a power of_ b _if it is divisible by_ b _and_ a/b _is a power of_ b_. Write a function called `is_power` that takes parameters a and b and returns True if a is a power of b. Note: you will have to think about the base case._Exercise 5  

_The greatest common divisor \(GCD\) of_ a _and_ b _is the largest number that divides both of them with no remainder._ 

_One way to find the GCD of two numbers is based on the observation that if_ r _is the remainder when_ a _is divided by_ b_, then_ gcd\(a, b\) = gcd\(b, r\)_. As a base case, we can use_ gcd\(a, 0\) = a_._

_Write a function called `gcd` that takes parameters a and b and returns their greatest common divisor._

_Credit: This exercise is based on an example from Abelson and Sussman’s_ Structure and Interpretation of Computer Programs_._

