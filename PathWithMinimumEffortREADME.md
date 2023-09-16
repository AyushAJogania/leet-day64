# leet-day64

## Problem Statement

You are given a 2D grid representing a height map of cells. You are initially located in the top-left cell `(0, 0)` and want to reach the bottom-right cell `(rows-1, cols-1)`. Each cell has a height value representing the elevation of that point. The cost of moving from one cell to an adjacent cell is the absolute difference in height between the two cells.

You need to find the minimum effort required to travel from `(0, 0)` to `(rows-1, cols-1)` while moving only to adjacent cells.

## Approach

To solve this problem efficiently, we can use a binary search to find the minimum effort required. The binary search is conducted on the possible effort values, and we check if it is possible to reach the destination with an effort less than or equal to the current value.

Here are the main steps of the approach:

1. Set up a binary search with a lower bound (minimum effort) of 0 and an upper bound of the maximum possible effort (the maximum height difference in the grid).

2. In each iteration of the binary search, calculate the mid-value of the current lower and upper bounds.

3. Create a priority queue (min heap) to perform a breadth-first search (BFS) while considering only paths with efforts less than or equal to the current mid-value.

4. Start a BFS from the top-left cell `(0, 0)` and explore adjacent cells with efforts less than or equal to the mid-value.

5. If the BFS reaches the bottom-right cell `(rows-1, cols-1)`, it means that it is possible to reach the destination with an effort less than or equal to the current mid-value. In this case, update the upper bound of the binary search with the mid-value.

6. If the BFS does not reach the destination, it means that the mid-value is too high, and we need to reduce our effort. Update the lower bound of the binary search.

7. Repeat the binary search until the lower and upper bounds are very close (e.g., the difference is less than a small epsilon value). The final lower bound will be the minimum effort required.

8. Return the minimum effort as the answer.

## Complexity Analysis

The time complexity of this solution is O(rows * cols * log(max_height)), where:

- `rows` and `cols` are the dimensions of the grid.
- `max_height` is the maximum possible height difference in the grid.

The space complexity is O(rows * cols) for the effort matrix and the priority queue.

## Conclusion

This solution efficiently finds the minimum effort required to travel from the top-left cell to the bottom-right cell in a grid with height values. It utilizes a binary search approach to narrow down the effort range and employs BFS to explore paths within the current range. The final result is the minimum effort required to reach the destination.
