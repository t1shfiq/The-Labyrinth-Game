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
