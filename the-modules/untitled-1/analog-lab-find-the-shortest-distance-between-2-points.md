# ANALOG LAB: Find the Shortest Distance between 2 Points

### Use these rules:

1. You can't walk through walls or locked doors

2. you may only walk on paths and crosswalks \(stay off grass and streets\)

After you identify the paths, place rings at points where paths cross or split. These decision points are called **nodes**. Now you may tie strings between the rings, these are called **edges** or **vertices**. Identify each **edge** with a unique label and mark the floor with the same label.

### Take a few minutes to guess which path will be shortest.

After all of the rings/nodes are placed and the strings/edges are string between your origin and destination it is time to do the calculation. Grab the origin and destination points and pull gently. The shortest path \(or paths!\) are made of the shortest aggregate of edges. Note the labels and check your theories. 

![pastedGraphic.png](blob:https://app.gitbook.com/950062ea-8561-4627-aff6-efdada8cd28e)

We will start working on programming graphs in Python, learn about Dijkstra's algorithm, and consider come applications for this approach including identifying friends and like-minded people on social media.

![Sam, Athena, Sumedha, Alyssa, and Zayn map out the pathways on the floor](../../.gitbook/assets/dscf2076.jpg)

![Place rings at each decision point \(or Node\)](../../.gitbook/assets/dscf2077.jpg)

![Paths, rings and string =&amp;gt; nodes and edges](../../.gitbook/assets/paths-and-strings.jpg)

![The final calculation](../../.gitbook/assets/thecalculation.jpg)

![Every path](../../.gitbook/assets/img_9797.jpg)

## What are the lengths of each segment?

```python
paths = [
   (A,B,C,D,E,O,P,Q),
   (A,B,C,K,Q),
   (A,B,C,D,E,F,G,H),
   (J,C,D,E,O,P,Q),
   (A,B,C,D,L,K,N,G,H),
   (A,B,C,D,L,R,N,G,H),
   (A,I,D,E,O,P,Q)
   ]

```

