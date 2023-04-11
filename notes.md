# Knights Travails - Project Brief

## Stage 1: Function

A function that takes in two coordinates on a chess board, and returns an inclusive list of the moves needed to get a knight from the first coordinate to the second.

### How can this be achieved?

#### 1. Setup

- Initialize an 8x8 chess board - array(8) of array(8)
- Each square stores the positions of the possible moves that a knight can take from that square

```
Square(x, y)

[
  (x-1, y-2), (x-2, y-1),
  (x-1, y+2), (x-2, y+1),
  (x+1, y-2), (x+2, y-1),
  (x+1, y+2), (x+2, y+2)
]

where 0 <= (x+a) <= 8
and   0 <= (y+b) <= 8
```

- This will form a connected graph of all the squares on the board

#### 2. Traversal
**Goal:** Find the shortest route from square A to square B

A recursive function that keeps track of visited squares in a list, *Visited*
- Create a list, *Route*, that represents the route, and push the current square to *Route*
- If square B lies within the current squares *possibleMoves*, push square B to *Route* and return *Route*
- Otherwise, re-run the function for all squares in *possibleMoves* but not in *Visited*
- Compare all the routes returned by each square, and return the shortest route

## Stage 2: Visualization
