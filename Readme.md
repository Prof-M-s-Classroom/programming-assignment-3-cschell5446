[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/K_t6ffJX)
# Prim's Algorithm with Min Heap and Adjacency Matrix

## Author
Connor Schell 

## Description
Briefly describe what your program does and how the code is structured.

- This program implements Prim's Algorithm to compute the Minimum Spanning Tree(MST)
- It reads a graph from the main.cpp, runs Prim's Algorithm, and then prints the edges along with the total cost.
- The graph.h/graph.cpp define the graph class and implement addEdge() and primMST()
- The heap.h/heap.cpp implement a custom MinHeap for managing vertices and keys
- The main.cpp is used to build and test the MST using the graph function

## Files
- graph.h / graph.cpp
- heap.h / heap.cpp
- main.cpp (unchanged)
- README.md

## How to Compile and Run
This project was developed and tested in CLion.  
Run directly from the IDE.

## Time Complexity Analysis


| Operation            | Time Complexity |
|----------------------|-----------------|
| Insert in MinHeap    | O(log v)        |
| Extract Min          | O(log v)        |
| Decrease Key         | O(log v)        |
| Prim’s MST Overall   | O(V^2)          |

_Explain why your MST implementation has the above runtime._

- Insert in MinHeap: each insert requires bubbling the new element up the binary heap, which would take at most log V steps.
- Extract Min: Removing the smallest element from the heap requires pushing the new root down the keep the order, which takes up to log V steps.
- Decrease Key: When a vertex key gets updated, it may bubble up the heap, taking up to log V steps.
- Prim's MST Overall: Although the MinHeap operations are log V, using an adjacency matrix forces scanning all V neighbors for every vertex, taking a time complexity of O(V^2)

## Test Case Description

Input:  
- Vertices: 5
- Edges:
0 - 1 : 2
0 - 3 : 6
1 - 2 : 3
1 - 3 : 8
1 - 4 : 5
2 - 4 : 7
3 - 4 : 9

Output:
0 - 1 : 2
1 - 2 : 3
1 - 4 : 5
0 - 3 : 6
Total MST Cost: 16