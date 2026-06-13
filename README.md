# Set-Matrix-Zeroes
Optimized C++ solution for LeetCode 73 - Set Matrix Zeroes using the first row and first column as markers to achieve O(1) extra space complexity.

Problem Statement

Given an m x n integer matrix, if an element is 0, set its entire row and column to 0. The operation must be performed in-place.

Example
Input
[
 [1,1,1],
 [1,0,1],
 [1,1,1]
]
Output
[
 [1,0,1],
 [0,0,0],
 [1,0,1]
]
Approach

The naive approach uses two extra arrays to keep track of rows and columns that need to be set to zero.

To optimize space, we use:

The first row as a column marker.
The first column as a row marker.
An additional variable col0 to track whether the first column should be zeroed.
Algorithm
Traverse the matrix.
Whenever a 0 is found:
Mark its row by setting matrix[i][0] = 0.
Mark its column by setting matrix[0][j] = 0.
Traverse the matrix again (excluding the first row and first column).
Set cells to 0 if their row or column is marked.
Handle the first row separately.
Handle the first column separately using col0.
