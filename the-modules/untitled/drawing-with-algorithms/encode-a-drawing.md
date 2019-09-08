---
description: This is Doug's example for the "Encode a Drawing" assignment
---

# Encode a drawing

## 1. draw a square in the center of the page

## 2. draw another square of the same size starting in the center of the first rectangle

## 3. draw a line from the NW corner of the first square to the NW corner of the second square

## 4. draw a third line from the NE corner of the first square to the NE corner of the second square

## 5. draw another line from the SW corner of the first squre to the SW corner of the second square

## 6. draw a final line from the SE corner of the first square to the SE corner of the second square

```python
# set the size of the window
size(350,350)
# set the background color to white
background(255)

# Don't will the shapes
noFill()
# Stroke with black
stroke(0)

# 1. draw a square in the center of the window
rect(100,100, 100,100)

# # 2. draw another square of the same size starting in the center of the first rectangle
rect(150,150, 100,100)

# # 3. draw a line from the NW corner of the first square to the NW corner of the second square
line(100,100, 150,150)

# # 4. draw a third line from the NE corner of the first square to the NE corner of the second square
line(200,100, 250,150)

# # 5. draw another line from the SW corner of the first squre to the SW corner of the second square
line(100,200, 150,250)

# # 6. draw a final line from the SE corner of the first square to the SE corner of the second square
line(200,200, 250,250)

# # 7. identify this object
fill(0, 102, 153)
text("Necker Cube", 140, 330)
```

