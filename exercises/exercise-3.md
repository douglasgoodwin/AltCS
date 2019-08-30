# Exercise 3

### Exercise 3A

_Write a function named `right_justify` that takes a string named s as a parameter and prints the string with enough leading spaces so that the last letter of the string is in column 70 of the display._

```text
>>> right_justify('monty')
                                                                 monty
```

_Hint: Use string concatenation and repetition. Also, Python provides a built-in function called len that returns the length of a string, so the value of `len('monty')` is 5._

### Exercise 3_B_

_A function object is a value you can assign to a variable or pass as an argument. For example, `do_twice` is a function that takes a function object as an argument and calls it twice:_

```text
def do_twice(f):
    f()
    f()
```

_Here’s an example that uses `do_twice` to call a function named `print_spam` twice._

```text
def print_spam():
    print('spam')

do_twice(print_spam)
```

1. _Type this example into a script and test it._
2. _Modify `do_twice` so that it takes two arguments, a function object and a value, and calls the function twice, passing the value as an argument._
3. _Copy the definition of `print_twice` from earlier in this chapter to your script._
4. _Use the modified version of `do_twice` to call `print_twice` twice, passing `'spam'` as an argument._
5. _Define a new function called `do_four` that takes a function object and a value and calls the function four times, passing the value as a parameter. There should be only two statements in the body of this function, not four._

_Solution:_ [_http://thinkpython2.com/code/do\_four.py_](http://thinkpython2.com/code/do_four.py)_._

### Exercise 3C

_Note: This exercise should be done using only the statements and other features we have learned so far._ 

1. _Write a function that draws a grid like the following:_

   ```text
   + - - - - + - - - - +
   |         |         |
   |         |         |
   |         |         |
   |         |         |
   + - - - - + - - - - +
   |         |         |
   |         |         |
   |         |         |
   |         |         |
   + - - - - + - - - - +
   ```

   _Hint: to print more than one value on a line, you can print a comma-separated sequence of values:_

   ```text
   print('+', '-')
   ```

   _By default, print advances to the next line, but you can override that behavior and put a space at the end, like this:_

   ```text
   print('+', end=' ')
   print('-')
   ```

   _The output of these statements is `'+ -'` on the same line. The output from the next print statement would begin on the next line._

2. _Write a function that draws a similar grid with four rows and four columns._

_Credit: This exercise is based on an exercise in Oualline,_ Practical C Programming, Third Edition_, O’Reilly Media, 1997._

