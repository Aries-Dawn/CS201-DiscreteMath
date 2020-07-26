# Lec 18 Graph

## Graph

### Definition:

​	A graph $G = (V, E)$ consists of a nonempty set ***V*** of vertices (or nodes) and a set ***E*** of edges. Each edge has either one or two vertices associated with it, called its endpoints. An edge is said to be incident to (or connect its endpoints.

### Simple graph vs. multi_graph pseudo_graph

​	A graph in which at most one edge joins each pair of distinct vertices (vs. multiple edges) and no edge joins a vertex to itself (= loop). 

### Complete graph ==Kn==

​	A graph with n vertices that ha s an edge between ==each pair== of vertices

## Graph Models

### Influence graphs

​	directed graphs where there is an edge from one person to another if the first person can influence the second one

### Collaboration graphs

​	undirected graphs where two people are connected if they collaborate in some way

## Undirected Graphs

### Definition:

​	Two vertices u; v in an undirected graph G are called adjacent (or neighbors) in G if there is an edge e between u and v. Such an edge e is called incident with the vertices u and v and e is said to connect u and v.

### Definition:

​	The set of all neighbors of a vertex v of G = (V; E), denoted by N(v), is called the neightborhood of v. If A is a subset of V, we denote by N(A) the set of all vertices in G that are adjacent to at least one vertex in A.

### Definition:

​	The ==degree== of a vertex in an undirected graph is the number of edges incident with it, except that a loop at a vertex contributes two to the degree of that vertex. The ei  degree of the vertex v is denoted by deg(v).

### Theorem 1 (Handshaking Theorem)

​	If $G = (V, E)$ is an undirected graph with m edges, then
$$
2m = \sum\limits_{v\in V}deg(v)
$$
***Proof :***

​	Each edge contributes 2 to $\sum deg$ .

​	$\Longrightarrow 2m=\sum\limits_{v\in V}deg(v)$ .

### Theorem 2

​	An undirected graph has an even number of vertices of odd degree.

***Proof :***

​	Let $V_1$ be the vertices of ***even*** degrees and $V_2$ be the vertices of ***odd*** degree.



![image-20200611234855821](C:\Users\30556\AppData\Roaming\Typora\typora-user-images\image-20200611234855821.png)
$$
2m\;is\;even\;number\\Then\;\sum\limits_{v\in V_1}deg(v)\; is\;an\;even\;number\\and\;deg(v)\;in\;V_1\;is\;even\;\Rightarrow|V_1|\;is\;even\\So\;\sum\limits_{v\in V_2}deg(v)\;must\;be\;a\;even\;number\;because\;sum\;is\;even\\But\;deg(v)\;in\sum\limits_{v\in V_2}deg(v)\;is\;odd\\So\;|V_2|\;is\;even\;number\\\Longrightarrow\;number\;of\;edge\;is\;|V|=\;|V_1|+|V_2|\;is\;even
$$


## Directed Graphs

### Definition:

​	An directed graph G = (V; E) consists of V, a nonempty set of vertices, and E, a set of directed edges. Each edge is an ordered pair of vertices. The directed edge (u; v) is said to start at u and end at v.

### Definition:

Let (u; v) be an edge in G. Then u is the initial vertex of the edge and is adjacent to v and v is the terminal vertex of this edge and is adjacent from u. The initial and terminal vertices of a loop are the same.

### Definition:

​	The in-degree of a vertex v, denoted by $deg^-(v)$, is the number of edges which terminate at v. The out-degree of v, denoted by$ deg^+(v)$, is the number of edges with v as their initial vertex. Note that a loop at a vertex contributes 1 to both the in-degree and the out-degree of the vertex.

### Theorem 3 

​	Let G = (V; E) be a graph with directed edges. Then

![image-20200612110938059](C:\Users\30556\AppData\Roaming\Typora\typora-user-images\image-20200612110938059.png)

## Complete Graphs

## N-dimensional Hypercube

​	An n-dimensional hypercube, or n-cube, $Q_n$ is a graph with $2^n$ vertices representing all bit strings of length n, where there is an edge between two vertices that differ in exactly
one bit position.

​	$|Q_n|=2^n$ 		$2m = \sum\limits_{v\in V}deg(v) = n$ 

## Bipartite Graphs

### Definition:

​	A simple graph G is bipartite if V can be partitioned into two disjoint subsets V1 and V2 such that every edge connects a vertex in V1 and a vertex in V2.