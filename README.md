# Graph Degree Sequence Checker

This C program generates a random degree sequence for a set of vertices, checks if the sequence is graphical (i.e., if it can represent a simple graph), and constructs the corresponding adjacency matrix if possible. The program is based on the Havel-Hakimi theorem for testing graphical degree sequences.

## Table of Contents
- [Features](#features)
- [How It Works](#how-it-works)
- [Prerequisites](#prerequisites)
- [Compilation and Execution](#compilation-and-execution)
  - [Compilation](#compilation)
  - [Running the Program](#running-the-program)
- [Example Output](#example-output)
- [Input Custom Degree Sequence](#input-custom-degree-sequence)
- [Hakimi Theorem Overview](#hakimi-theorem-overview)
- [Code Structure](#code-structure)
  - [Functions](#functions)
  - [Files](#files)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)

## Features
- **Generate Random Degree Sequence**: The program randomly generates a degree sequence for a specified number of vertices.
- **Check Degree Sequence Validity**: It checks whether the generated sequence can represent a valid simple graph using the Havel-Hakimi theorem.
- **Construct Graph**: If the degree sequence is valid, the program constructs an adjacency matrix representation of the graph.
- **Manual Input**: If the system fails to generate a valid sequence, the user can input their own sequence for verification and graph creation.

## How It Works

1. The user specifies the number of vertices (`n`), where `n >= 2`.
2. The program generates a random degree sequence for these vertices and checks if it's valid using the Havel-Hakimi algorithm.
3. If the sequence is valid, it constructs a graph in the form of an adjacency matrix.
4. If the sequence is invalid, the user is prompted to enter their own degree sequence.

## Prerequisites

- **C Compiler**: You need a C compiler like GCC installed to compile and run this program.
- **Basic C Knowledge**: Familiarity with C programming is helpful for understanding and modifying the code.

## Compilation and Execution
### Compilation
To compile the program, use the following command in your terminal (assuming you are using GCC):

```bash
gcc -o graph_degree_checker graph_degree_checker.c
```


## Running the Program

After compilation, run the program as follows:

```bash
./graph_degree_checker
```

You will be prompted to enter the number of vertices (nodes) in the graph. The program will then generate random degrees, check if the degree sequence is valid, and either generate the graph or allow you to input your own degree sequence if necessary.

## Example Output

Here is an example of the program's output:

Enter, the number of vertices: 
5
vert(0) has degree : 4
vert(1) has degree : 3
vert(2) has degree : 2
vert(3) has degree : 2
vert(4) has degree : 0
this sequence of degrees is a graphic! according to hakimi theorem.

```
PRINTING THE GRAPH:
           (0)           (1)           (2)           (3)           (4)
  
  (0)         0               1               1               1               1
  (1)         1               0               1               1               0
  (2)         1               1               0               0               0
  (3)         1               1               0               0               0
  (4)         1               0               0               0               0
```
## Input Custom Degree Sequence

If the program fails to generate a valid degree sequence, you will be asked to input one manually:

```
this sequence of degrees is not a graphic according to hakimi theorem.
Enter valid degrees for vertices!
Input Element 1: 4
Input Element 2: 3
Input Element 3: 2
...

```

## Hakimi Theorem Overview

The Havel-Hakimi theorem provides an algorithm to check whether a degree sequence can be represented by a simple graph. The idea is to repeatedly subtract 1 from the highest degrees and re-sort the sequence to see if a valid graph can be formed.

In this program, the algorithm is implemented through the graphExists() function.

## Code Structure

### Functions
- ```produceDegrees(int x)```: Generates a random degree sequence for x vertices.
- ```graphExists(int x, int *deg)```: Checks if the degree sequence is graphical using the Havel-Hakimi algorithm.
- ```createGraph(int vert, int *deg)```: Constructs the graph in an adjacency matrix if the degree sequence is valid.

### Files
- ```graph_degree_checker.c```: Main program file.

### Future Improvements
- **Optimize Sorting**: Replace the current sorting logic with a more efficient algorithm like qsort.
- **Graph Visualization**: Add graphical output or export to formats like Graphviz for better visualization of the generated graph.
- **Dynamic Memory Management**: Improve memory handling by avoiding static arrays and using dynamic memory (malloc).

## Contributing

If you find bugs or have suggestions for improvement, feel free to open an issue or submit a pull request. Contributions are welcome!