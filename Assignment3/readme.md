The BellmanFord algorithm is implemeted with the the help of dynamic programming approach.

Input: Graph and a source vertex src

Output: Shortest distance to all vertices from src. 

If there is a negative weight cycle, then shortest distances are not calculated, negative weight cycle is reported.

1) This step initializes distances from source to all vertices as infinite and distance to source itself as 0. Create an array dist[] of size |V| with all values as infinite except dist[src] where src is source vertex.

2) This step calculates shortest distances. Do following |V|-1 times where |V| is the number of vertices in given graph.
…..a) Do following for each edge u-v
………………If dist[v] > dist[u] + weight of edge uv, then update dist[v]
………………….dist[v] = dist[u] + weight of edge uv

3) This step reports if there is a negative weight cycle in graph. Do following for each edge u-v
……If dist[v] > dist[u] + weight of edge uv, then “Graph contains negative weight cycle”

The idea of step 3 is, step 2 guarantees shortest distances if graph doesn’t contain negative weight cycle.    If we iterate through all edges one more time and get a shorter path for any vertex, then there is a negative weight cycle

For some test-cases , the execution time is compared.

bellman-ford.jpg shows the graph of the vertices*edges vs running time 
