# Path Finding Algorithm: Dijkstra's and A* with Obstacles

The included files and C++ code were part of my final project for Mechanical Engineering 555 taught by Genevieve Lipp. This program is an implementation of Dijkstra's and A* search, two path-finding algorithms.

Read about Dijkstra's algorithm here: https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm

Read about the A* search algorithm here: https://en.wikipedia.org/wiki/A*_search_algorithm

It is also capable of finding best paths, with either method, around obstacles.


## Quick Start
Download the mp_miniproject folder. Open in your IDE of choice and make. Run the following command to see a simple output for A*:

./path-step4 inputs3/trickyM.txt inputs3/TM.txt 0 3 -a



## Setup Files + Commands

You can either run the path finding algorithm as described in the unit test file TESTING.txt (described below), or can setup the required files yourself. The template for CL arguments is:

./path-step4 nodes_file.txt obstacles_file.txt start_node end_node -a

note: the -a is an optional command that request A* be used. Without -a, Dijkstra's is used.

### nodes and edges file
A node is defined as a point with a unique ID and a (x, y) coordinate. An edge connects two points. To create your own map, setup a text file with the following format. You can also view the inputs3 and inputs4 directory for examples.

$nodes
0 x_cord y_cord
1 x_cord y_cord
2 x_cord y_cord
(include as many nodes as desired)
$edges
0 1
1 2
(include as many edges as desired. Repeat edges are ignored.)

While the nodes do not need to be ordered, the IDs must start at 0 and be continuous (incorrect: 1, 0, 3). Only two edges may be given per line. In the above format example, the given edges indicate node 0 -> node 1 and node 1 -> node 2.

### Obstacles File
An obstacle is defined as any segment (2 nodes) or polygon (>2 nodes) that intersect an edge in the path. Note that an obstacle, by definition, cannot be less than 2 nodes. Any number of valid nodes can be labeled as obstacles with the following format:

$obstacles
0 1
1 2 3 4 5 6
(include as many obstacles as desired)

In the above template, an obstacle runs from node 0 -> 1, and another forms a hexagon via nodes 1 through 6. Note that the obstacles file does not add new nodes; it labels nodes from the nodes and edges file as obstacles.



## Test Cases
Extensive test cases, with CL inputs, outputs, and program design comments are included in TESTING.txt. If you simply wish to read about the overall implementation, skip to the section titled "step4."
