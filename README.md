# The-Labyrinth-Game
Implement in Java a Graph<L> class to support undirected graphs. Vertices in a graph are to be distinctly labelled by labels of type L. It should provide a reasonable public interface that allows one to build an arbitrary (undirected) graph. Your Graph<L> class must implement AbsGraph<L> (i.e., class Graph<L> implements AbsGraph<L> …).

AbsGraph.java:

import java.util.Iterator;

public interface AbsGraph<L> {
    int  numVertices();
    
    int  numEdges();
    
    void addVertex(L key);
    
    void addEdge(L from, L to);
    
    Iterator<L> findPath(L from, L to);
    
}

Thus, it must implement (at least) the following.

int numVertices()

int numEdges()

void addVertex(L key)
void addEdge(L from, L to)

Iterator<L> findPath(L from, L to)
    

A graph class obviously needs a way to add vertices and to add edges. We assume here that a vertex needs to be added before any edge involving the vertex is added. Let addEdge just not do anything if called on, say, addEdge(1, 2), but 1 has not been added as an edge yet or but 2 has not been added as an edge yet.

Method findPath would not be necessary found in any given Graph ADT, but is requested here. A call to findPath(source, target) should return (an Iterator over) a valid, simple path from vertex source to vertex target in the graph, The returned iterator should walk the path from source to target.

You will need some bookkeeping internally to find a path. Be certain that Graph “cleans up” at the end of a findPath call. We should be able to call findPath a second time, and have it work properly.

We want your Graph class for driving a labyrinth (maze) solver! That is, your Graph class will be tested by a class Labyrinth. Labyrinth generates a random maze represented on an N×N grid. Each generated labyrinth is guaranteed to have a solution. Labyrinth has a public method void solution (Graph<L> G), which loads the “labyrinth” into G as vertices and edges, then calls G.findPath(entrance, exit) to get a solution path to the labyrinth, and finally displays the path in the labyrinth.

Note that this would not necessarily be the way one would implement Labyrinth in best practice. Labyrinth's solution method should take no arguments, and create its own new Graph to compute a solution path for it. We have set it up, however, the way that we have for the sake of the project.

The graphs that Graph needs to handle well for use with Labyrinth are sparse: the number of edges are on the order of the number of vertices ((n)); but there can be a large(-ish) number of vertices, say, 10,000. So implement accordingly.
