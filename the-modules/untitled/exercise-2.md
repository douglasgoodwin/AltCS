# TP Exercise 2

### **Exercise 2A**

Repeating my advice from the previous chapter, whenever you learn a new feature, you should try it out in interactive mode and make errors on purpose to see what goes wrong.

* We’ve seen that n = 42 is legal. What about 42 = n?
* How about x = y = 1?
* In some languages every statement ends with a semi-colon, ;. What happens if you put a semi-colon at the end of a Python statement?
* What if you put a period at the end of a statement?
* In math notation you can multiply x and y like this: x y. What happens if you try that in Python?
* 
```python
# try this out in Colab
n = 42
42 = n
x = y = 1

x = y = 1;
x = y = 1.
x y
```

### **Exercise 2B**

Practice using the Python interpreter as a calculator: 

1. The volume of a sphere with radius r is 4/3 π r3. What is the volume of a sphere with radius 5?
2. Suppose the cover price of a book is $24.95, but bookstores get a 40% discount. Shipping costs $3 for the first copy and 75 cents for each additional copy. What is the total wholesale cost for 60 copies?
3. If I leave my house at 6:52 am and run 1 mile at an easy pace \(8:15 per mile\), then 3 miles at tempo \(7:12 per mile\) and 1 mile at easy pace again, what time do I get home for breakfast?

$$
Vol = 4/3  pi * (r^{3})
$$

```text
pi = 3.14159
r = 5
Vol = (4/3 * pi) * (r*r*r)
```

```python
# Suppose the cover price of a book is $24.95, 
# but bookstores get a 40% discount. 
# Shipping costs $3 for the first copy and 
# 75 cents for each additional copy. 
# What is the total wholesale cost for 60 copies?

coverprice = 24.95
discount = 0.4 * 24.95
firstcopy = discount + 3.00
addlcopy = discount + 0.75

# ship 60 wholesale copies
 firstcopy + (59 * addlcopy)
```



