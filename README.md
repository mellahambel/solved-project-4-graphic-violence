Download Link: https://assignmentchef.com/product/solved-project-4-graphic-violence
<br>
<h2>Introduction</h2>

An army of bellowing, enraged traveling salesmen are descending on Elizabethtown College! Their mission: To find tours that will allow them to visit all of their clients in the shortest amount of time. They don’t care if the problem is computationally infeasible to solve! They are willing to wait for a brute force solution. And, if you don’t give them a brute force solution, they are prepared to use brute force on you!




<h2>Overview</h2>

Your job is to write a class that can load an (undirected) graph from a file. Then, your class should support a number of options, all accessed through a text-driven menu. Your class should be called <code>Graphs</code> and stored in <code>Graphs.java</code>. You are permitted to create other helper classes if you think it would be useful. A separate class to hold the representation of a graph is not a bad idea.

Let’s list the things you’re going to need to be able to do.

<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#loading">Loading the Graph</a>You will need to open the file specified by the user and read in a representation of an undirected graph.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#menu">Display a Menu</a>Display a menu the user can make choices from. Each choice will either give information about the currently loaded graph or transform it in some way.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#connected">Is Connected</a>You will need to determine whether or not the graph is connected.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#mst">Minimum Spanning Tree</a>If the graph is connected, you will need to find a minimum spanning tree for the graph and print an error otherwise.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#shortest">Shortest Path</a>Prompt the user for a node. Then, print the lengths of the shortest paths from that node to all other nodes and the actual paths as well.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#ismetric">Is Metric</a>You will need to determine whether or not the graph is metric.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#makemetric">Make Metric</a>A graph that is not metric can be made metric by making it a complete graph and adjusting all of its edges so that every direct edge gives the shortest path between the two connected nodes.</li>

  </ol></li>

</ol>




<ol>

 <li style="list-style-type: none">

  <ol>

   <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#tsp">Traveling Salesman Problem</a>Use brute force to try all possible tours starting at node 0. Print the length of the shortest one and the sequence of nodes</li>

  </ol></li>

</ol>




<ol>

 <li><a href="http://users.etown.edu/w/wittmanb/cs221/projects/project4.aspx#approximate">Approximate TSP</a>If the graph is metric, use the doubled MST method of finding a 2-approximation to TSP. Otherwise, return an error.</li>

</ol>




<h2><a name="loading"></a>Loading the Graph</h2>

When your program starts, you must prompt the user for a graph file. This graph file will start with a number saying the number of nodes in the graph. Then, each line after that will correspond to a particular node. Each such line will start with a number specifying the number of edges connected to a node. The rest of the line will give a series of pairs of numbers. The first number in the pair gives the number of node that the current node is connected to. The second gives the length of the edge connecting them.

We will use the following graph for many of our examples.

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-graph.png?w=980" class="centered lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="centered" src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-graph.png?w=980" data-recalc-dims="1">

 </noscript>

The input file for this graph is as follows.

<pre>62 1 5 5 62 0 5 2 33 1 3 3 4 5 22 2 4 4 52 3 5 5 73 0 6 2 2 4 7</pre>




<h2><a name="menu"></a>Display a Menu</h2>

After the graph has been loaded, display a menu the user can make choices from. Each choice will either give information about the currently loaded graph or transform it in some way.

The choices for the menu are:

<ol>

 <li>Is Connected</li>

 <li>Minimum Spanning Tree</li>

 <li>Shortest Path</li>

 <li>Is Metric</li>

 <li>Make Metric</li>

 <li>Traveling Salesman Problem</li>

 <li>Approximate TSP</li>

 <li>Quit</li>

</ol>

The user should be able to pick any sequence of choices repeatedly until finally selecting Quit (8).

Sample output for the menu is as follows.

<pre>1. Is Connected2. Minimum Spanning Tree3. Shortest Path4. Is Metric5. Make Metric6. Traveling Salesman Problem7. Approximate TSP8. QuitMake your choice (1 - 8):</pre>




<h2><a name="connected"></a>Is Connected</h2>

If the user selects choice 1, you will need to determine whether or not the graph is connected. If the graph is connected, print <code>Graph is connected.</code>Otherwise print <code>Graph is not connected.</code>

Output for the sample graph is as follows.

<pre>Graph is connected.</pre>




<h2><a name="mst"></a>Minimum Spanning Tree</h2>

If the graph is connected, you will need to find a minimum spanning tree for the graph. Otherwise, print <code>Error: Graph is not connected</code>. Print the MST in the same general format that is used for the graph input file.

The MST for the sample graph is as follows.

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-mst.png?w=980" class="centered lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="centered" src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-mst.png?w=980" data-recalc-dims="1">

 </noscript>

Output for the sample graph is as follows.

<pre>61 1 52 0 5 2 33 1 3 3 4 5 22 2 4 4 51 3 51 2 2</pre>




<h2><a name="shortest"></a>Shortest Path</h2>

Prompt the user for a node. Then, print the lengths of the shortest paths from that node to all other nodes in parentheses. For the starting node, print <code>(0)</code>. For unreachable nodes, print <code>(Infinity)</code>. After the length of each shortest path, print a tab and then the nodes visited in the path itself, separated by arrows. Note that you will need to keep a back pointer giving the previous node in the path as well as the best distance found so far in order to produce each shortest path.

If a user entered node 0 for this choice, the output for the sample graph would be as follows. User input is shown in <code class="green">green</code>.

<pre>From which node would you like to find the shortest paths (0 - 5): <em>0</em>0: (0)	01: (5)	0 -&gt; 12: (8)	0 -&gt; 1 -&gt; 2	3: (12) 0 -&gt; 1 -&gt; 2 -&gt; 34: (13)	0 -&gt; 5 -&gt; 45: (6)	0 -&gt; 5</pre>




<h2><a name="ismetric"></a>Is Metric</h2>

You will need to determine whether or not the graph is metric. There are two conditions to be a metric graph:

<ol>

 <li>The graph must be completely connected</li>

 <li>The every edge in the graph must be obey the triangle inequality</li>

</ol>

There are three possible outputs. If the graph is not completely connected, print <code>Graph is not metric: Graph is not completely connected.</code> If the graph is completely connected but its edges do not obey the triangle inequality, print <code>Graph is not metric: Edges do not obey the triangle inequality.</code>

Output for the sample graph would be as follows:

<pre>Graph is not metric:  Graph is not completely connected.</pre>




<h2><a name="makemetric"></a>Make Metric</h2>

A graph that is not metric can be made metric by making it a complete graph and adjusting all of its edges so that every direct edge gives the shortest path between the two connected nodes.

This choice is the only choice that changes the structure of the graph. If the graph is connected, you must add edges between every node that does not already have an edge. Then, you must set every direct edge to have the cost of the shortest path between those edges. Afterwards, print the graph data as if it were a graph input file. If the graph is not connected, print <code>Error: Graph is not connected.</code>

For the sample graph, the resulting graph is below. Edge weights have been omitted for clarity, but they are listed in the sample output.

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-metric.png?w=980" class="centered lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="centered" src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-metric.png?w=980" data-recalc-dims="1">

 </noscript>

<pre>65 1 5 2 8 3 12 4 13 5 65 0 5 2 3 3 7 4 12 5 55 0 8 1 3 3 4 4 9 5 25 0 12 1 7 2 4 4 5 5 65 0 13 1 12 2 9 3 5 5 75 0 6 1 5 2 2 3 6 4 7</pre>




<h2><a name="tsp"></a>Traveling Salesman Problem</h2>

Use brute force to try all possible tours starting at node 0. Print the length of the shortest one and the sequence of nodes it takes.

There are two possible errors. If the graph is not connected, print <code>Error: Graph is not connected.</code> Remember that a TSP path can only cross an edge once. If there is no path that returns to the starting node without re-crossing an edge, print <code>Error: Graph has no tour.</code>

The sample graph has the following (obvious) TSP tour:

<img decoding="async" data-recalc-dims="1" data-src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-tsp.png?w=980" class="centered lazyload" src="data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw==">

 <noscript>

  <img decoding="async" class="centered" src="https://i0.wp.com/users.etown.edu/w/wittmanb/cs221/projects/images/sample-tsp.png?w=980" data-recalc-dims="1">

 </noscript>

For the sample graph, output is below. The length of the tour is given first, followed by a colon, followed by the sequence of nodes, separated by arrows.

<pre>30: 0 -&gt; 1 -&gt; 2 -&gt; 3 -&gt; 4 -&gt; 5 -&gt; 0</pre>

<p class="warning">Warning: If you try this on a large problem instance, you will be waiting for the Universe to grow cold. If you execute it efficiently, you should be able to run TSP on an instance with around 30 edges. Graph structure makes a big difference.




<h2><a name="approximate"></a>Approximate TSP</h2>

If the graph is metric, we can approximate the best TSP tour with the following steps:

<ol>

 <li>Find a minimum spanning tree for the graph</li>

 <li>Make a tour by doubling all the edges of the minimum spanning tree</li>

 <li>Convert the tour to a Hamiltonian tour by shortcutting past some nodes (sounds messy, but it’s really just a preorder walk, AKA depth-first traversal, of the MST)</li>

</ol>

Because the MST cannot be longer than the best TSP tour, and shortcutting past nodes in a metric graph will not increase the distance, a doubled MST means that the resulting tour is no more than twice the optimum TSP tour.

Other decent explanations of this algorithm are given <a href="https://en.wikipedia.org/wiki/Travelling_salesman_problem#Metric_TSP">here</a> and <a href="http://www.personal.kent.edu/~rmuhamma/Algorithms/MyAlgorithms/AproxAlgor/TSP/tsp.htm">here</a>.

If the graph is not metric, print <code>Error: Graph is not metric.</code>

For our unchanged sample graph, the output would be <code>Error: Graph is not metric.</code> However, if we had modified the graph so that it is metric, the result would be the same as the brute force TSP. In this case, the approximation gets the optimal tour.

Note: You can compare your results against the example on <a href="http://www.personal.kent.edu/~rmuhamma/Algorithms/MyAlgorithms/AproxAlgor/TSP/tsp.htm">this webpage</a>. An applet there will also do this approximation. You can compare your results, but it does not allow you to enter nodes at specific locations. So, you’ll have to approximate your graphs in the Euclidean plane to use it. Search around. There are probably other TSP applets out there.




<h2>Hints</h2>

<ul>

 <li style="list-style-type: none">

  <ul>

   <li>Start early. Try to work on the pieces in the order they are given to you. There is a natural dependence in many cases. For example, making the final TSP approximation is dependent on MST and making the graph metric. Making the graph metric is dependent on knowing whether or not the graph is connected.</li>

  </ul></li>

</ul>




<ul>

 <li style="list-style-type: none">

  <ul>

   <li>You are allowed to implement the graph with an adjacency matrix or with adjacency lists. It’s up to you.</li>

  </ul></li>

</ul>




<ul>

 <li style="list-style-type: none">

  <ul>

   <li>Think before you code. 1 minute of design == 10 minutes of coding == 100 minutes of debugging.</li>

  </ul></li>

</ul>




<ul>

 <li>You may use the Java Collection Framework if you need lists, queues, or stacks. Very little there is likely to help you much. You are (naturally) forbidden from using graph libraries such as <code>JGraph</code> and <code>JGraphT</code>.</li>

</ul>