# Exercise 5

### Exercise 5A

_The time module provides a function, also named time, that returns the current Greenwich Mean Time in “the epoch”, which is an arbitrary time used as a reference point. On UNIX systems, the epoch is 1 January 1970._

```text
>>> import time
>>> time.time()
1437746094.5735958
```

_Write a script that reads the current time and converts it to a time of day in hours, minutes, and seconds, plus the number of days since the epoch._

### Exercise 5_B_

_Fermat’s Last Theorem says that there are no positive integers_ a_,_ b_, and_ c _such that_

| an + bn = cn  |
| :--- |


_for any values of_ n _greater than 2._

1. _Write a function named `check_fermat` that takes four parameters—a, b, c and n—and checks to see if Fermat’s theorem holds. If_ n _is greater than 2 and_ 

   | _an + bn = cn_  |
   | :--- |


   _the program should print, “Holy smokes, Fermat was wrong!” Otherwise the program should print, “No, that doesn’t work.”_

2. _Write a function that prompts the user to input values for a, b, c and n, converts them to integers, and uses `check_fermat` to check whether they violate Fermat’s theorem._

### Exercise 5C

_If you are given three sticks, you may or may not be able to arrange them in a triangle. For example, if one of the sticks is 12 inches long and the other two are one inch long, you will not be able to get the short sticks to meet in the middle. For any three lengths, there is a simple test to see if it is possible to form a triangle:_

> _If any of the three lengths is greater than the sum of the other two, then you cannot form a triangle. Otherwise, you can. \(If the sum of two lengths equals the third, they form what is called a “degenerate” triangle.\)_

1. _Write a function named `is_triangle` that takes three integers as arguments, and that prints either “Yes” or “No”, depending on whether you can or cannot form a triangle from sticks with the given lengths._
2. _Write a function that prompts the user to input three stick lengths, converts them to integers, and uses `is_triangle` to check whether sticks with the given lengths can form a triangle._

### Exercise 5_D_

_What is the output of the following program? Draw a stack diagram that shows the state of the program when it prints the result._

```text
def recurse(n, s):
    if n == 0:
        print(s)
    else:
        recurse(n-1, n+s)

recurse(3, 0)
```

1. _What would happen if you called this function like this: recurse\(-1, 0\)?_
2. _Write a docstring that explains everything someone would need to know in order to use this function \(and nothing else\)._

The following exercises use the turtle module, described in Chapter [4](http://greenteapress.com/thinkpython2/html/thinkpython2005.html#turtlechap):

### Exercise 5E

_Read the following function and see if you can figure out what it does \(see the examples in Chapter_ [_4_](http://greenteapress.com/thinkpython2/html/thinkpython2005.html#turtlechap)_\). Then run it and see if you got it right._

```text
def draw(t, length, n):
    if n == 0:
        return
    angle = 50
    t.fd(length*n)
    t.lt(angle)
    draw(t, length, n-1)
    t.rt(2*angle)
    draw(t, length, n-1)
    t.lt(angle)
    t.bk(length*n)
```

> ![](http://greenteapress.com/thinkpython2/html/thinkpython2006.png)
>
> | Figure 5.2: A Koch curve. |
> | :--- |

### Exercise 5F

_The Koch curve is a fractal that looks something like Figure_ [_5.2_](http://greenteapress.com/thinkpython2/html/thinkpython2006.html#fig.koch)_. To draw a Koch curve with length_ x_, all you have to do is_

1. _Draw a Koch curve with length_ x/3_._
2. _Turn left 60 degrees._
3. _Draw a Koch curve with length_ x/3_._
4. _Turn right 120 degrees._
5. _Draw a Koch curve with length_ x/3_._
6. _Turn left 60 degrees._
7. _Draw a Koch curve with length_ x/3_._

_The exception is if_ x _is less than 3: in that case, you can just draw a straight line with length_ x_._

1. _Write a function called koch that takes a turtle and a length as parameters, and that uses the turtle to draw a Koch curve with the given length._
2. _Write a function called snowflake that draws three Koch curves to make the outline of a snowflake._

   _Solution:_ [_http://thinkpython2.com/code/koch.py_](http://thinkpython2.com/code/koch.py)_._

3. _The Koch curve can be generalized in several ways. See_[_http://en.wikipedia.org/wiki/Koch\_snowflake_](http://en.wikipedia.org/wiki/Koch_snowflake) _for examples and implement your favorite._

