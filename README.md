# University of Michigan - Applied Social Network Analysis in Python - notes
University of Michigan - Applied Social Network Analysis in Python

## This note we aim to study the categorize problems with tree graph analysis, visualization for materials study, and verification of ideas. Some visualization presents you the velocity of nodes graph in a graphical mode that is faster to understand finding the center point and differentiate multiple path inputs.

### 🧸💬 Creating and manipulating graph

🦭💬 How to find the centre of the collection fastest way⁉️ </br>
🐑💬 ➰ Possible by visualization, this sense is processing when they create brain signals learning. </br>
🐯💬 From centre of the graph we can estimate transfer rates, and most frequent rates, add or delete nodes, and find neighbor nodes and branch nodes that we can interact with less effect overall. </br>
🐐💬 Andy's favorites movie is Mean Girl ⁉️ 🥺💬 Sometimes the girl is so mean and we talk in English.  </br>
```
answer = answer_one();                                                                 # 🧸💬 Output from "assets/Employee_Movie_Choices.txt". 

# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in answer.nodes};                                                 # 🧸💬 Create labels collection from output nodes.
nodes = pd.DataFrame( answer.nodes );                                                  # 🧸💬 Stored nodes and node property into a dataset.
nodes["Colours"] = nodes[0].apply( lambda x : "red" if x == "Employee" else "blue" );  # 🧸💬 Assign colour property to nodes property.
nx.draw(answer, with_labels=True, labels=labels, node_color=nodes.iloc[:,1]);          # 🧸💬 Draws nodes with label and property.
```

### 🧸💬 Output

🐑💬 ➰ #Employee is nodes when Movies is edges contain categorize that is interact by nodes. </br>
🧸💬 Edges had property but they do not interact, nodes need property to performance. </br>
```
Graph with 19 nodes and 24 edges
---
#Employee	Movie
Andy	        Anaconda
Andy	        Mean Girls
Andy	        The Matrix
Claude	        Anaconda
Claude	        Monty Python and the Holy Grail
Claude	        Snakes on a Plane
. . .
```

### 🧸💬 Visulaization

🐑💬 ➰ How do Andy to interact with Claude⁉️ </br>
🥺⁉️ Are they mercy the Mean girl⁉️ </br>
🐐💬️‼️ No, they are watching Anaconda️ the hands of the Jungle‼️ </br>
🦁💬️ Andy has the advantage of approximate nodes connected to overall nodes they are sorted by the input. If you want to know people you need to talk to Andy. </br>
🐑💬 ➰ This answer can is easy with graph mode, now try to do it with text mode in the text input format.  </br>

#### 🧸💬 Example of graph problem by finding communication nodes or connected nodes.

🐑💬 ➰ If Andy does not watch Anaconda then he does not have the same favorite movie as Claude but Frida, but Claude has his favorite movie Snakes on a Plane same as Georgia and Andy.  </br>
🐯💬 If Vincent does not watch The Godfather but he can still strongly interact with Frida with 2 commons sharing interest. </br>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/01.png">
</p>

### 🧸💬 Creating and manipulating graph with nodes property.

```
answer = answer_two();

# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in answer.nodes};
nodes = pd.DataFrame( answer.nodes );
nodes.columns = ["Node_name"]

types = nx.get_node_attributes(answer, "type");
print( types );

nodes["type"] = nodes["Node_name"].apply( lambda x : types[x] if x in types.keys() else np.NaN );
nodes["labels"] = nodes["Node_name"].apply( lambda x : types[x] if x in types.keys() else x );
nodes["colours"] = nodes["Node_name"].apply( lambda x : "red" if x in types.keys() else "blue" );

dict_label = { };
for idx, node in enumerate(labels) :
    dict_label[node] = nodes["labels"].iloc[idx];

# 🧸💬 I try to manage the property of the nodes graph, they are in dictionary. 
nx.draw(answer, with_labels=True, labels=dict_label, node_color=nodes["colours"].to_numpy() );
nodes.head( 5 )
```

### 🧸💬 Output

```
Graph with 19 nodes and 24 edges
{'Andy': 'employee', 'Anaconda': 'movie', 'Mean Girls': 'movie', 'The Matrix': 'movie', 'Claude': 'employee', 'Monty Python and the Holy Grail': 'movie', 'Snakes on a Plane': 'movie', 'Frida': 'employee', 'The Shawshank Redemption': 'movie', 'The Social Network': 'movie', 'Georgia': 'employee', 'Joan': 'employee', 'Forrest Gump': 'movie', 'Kung Fu Panda': 'movie', 'Lee': 'employee', 'Pablo': 'employee', 'The Dark Knight': 'movie', 'Vincent': 'employee', 'The Godfather': 'movie'}
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/02.png">
</p>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/03.png">
</p>
