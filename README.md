# MATLAB-ConnectedGraph
MatLab script that determines whether the specified subset of vertices in the given graph induces a connected graph

---

## Task analysis

A connected graph is a graph with a single connected component. A connected component of a graph, is a subgraph of a graph that includes all vertices that connect to each other.

The program will process the graph's edges, vertices that induce the graph and output a response indicating whether the induced subgraph is connected, together with the computation time and visualisation of the graph where the nodes and edges are highlighted to show the induced subgraph that the program is analysing.

First, the program will search for the edges of the induced subgraph using <i>GetInducedGraphEdges</i> function. This function loops through all the edges of the underlying graph and checks whether both vertices of an edge belong to vertices that induce a subgraph. 

When these edges are found, the program calls the <i>IsGraphConnected</i> function, which performs breadth-first search from one of the vertices of the induced subgraph and compares the number of vertices traversed in the breadth-first search with the number of vertices in the induced graph. If the numbers match, the subgraph is connected.

<p align="center">
  <img src="https://github.com/devJUKI/MATLAB-ConnectedGraph/blob/main/img1.png" alt="drawing" width="700"/>
</p>
  
The first figure shows an induced subgraph with vertices 3, 6 and 8, which in the given graph is not connected because vertex 3 does not belong to the same connected component as vertices 6 and 8, and the induced subgraph in the second figure is connected because vertices 3, 4, 6 and 8 are in the same subgraph. Vertex 4 allowed vertex 3 to connect to vertices 6 and 8, making the induced subgraph connected.

## Test samples

Here are 3 tests, to show how this program is working. In one of them, the program had to find, that the induced subgraph is connected and the other two are not connected.

### First test (not connected subgraph)

<p align="center">
  <img src="https://github.com/devJUKI/MATLAB-ConnectedGraph/blob/main/img2.png" alt="drawing" width="400"/>
</p>

#### Input:

Number of vertices

        n = 8;

Edge matrix

        U = [1 2; 1 3; 1 5; 2 4; 2 6; 3 7; 4 5; 4 8; 6 4; 6 8; 7 1];

Vertex set of the induced graph

        vi = [2 3 5];

#### Output (translated)

        The induced graph is not connected
        Calculation time:
        0.0014
        
### Second test (connected subgraph)

<p align="center">
  <img src="https://github.com/devJUKI/MATLAB-ConnectedGraph/blob/main/img3.png" alt="drawing" width="400"/>
</p>

#### Input:

Number of vertices

        n = 8;

Edge matrix

        U = [1 2; 1 3; 1 5; 2 4; 2 6; 3 7; 4 5; 4 8; 6 4; 6 8; 7 1];

Vertex set of the induced graph

        vi = [1 2 3 5 6 8];

#### Output (translated)

        The induced graph is connected
        Calculation time:
        0.0034

### Third test (not connected subgraph)

<p align="center">
  <img src="https://github.com/devJUKI/MATLAB-ConnectedGraph/blob/main/img4.png" alt="drawing" width="400"/>
</p>

#### Input:

Number of vertices

        n = 10;

Edge matrix

        U = [1 2; 1 5; 2 4; 3 7; 3 8; 4 5; 4 7; 4 9; 6 4; 6 8; 6 10; 7 1; 9 10];

Vertex set of the induced graph

        vi = [1 2 3 5 6 8];

#### Output (translated)

        The induced graph is not connected
        Calculation time:
        0.0033
