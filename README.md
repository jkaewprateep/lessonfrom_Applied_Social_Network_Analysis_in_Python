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

🐑💬 ➰ How do we select the correct action response to the target node for solving the tree graph problem? We can set the action node as centre node where next to our centre node is the property that matches our actions in the actions list or target estimation. </br>
🦭💬 Andy's can interact with friends through movies, what are movies Andy likes ⁉️ </br>
🐯💬 Anaconda, Mean Girls, and The Matrix. He had good spots about the movie selection when Adventure, Comedy, and Sci-fi are impact zones for peak lady somebody do that. </br>

```
answer = answer_two();

# 🧸💬 Define a graph from simple file, using file reader and Pandas.                 
labels = {n: n for n in answer.nodes};                                                 # 🧸💬 Create label array collection from nodes.
nodes = pd.DataFrame( answer.nodes );                                                  # 🧸💬 Saved nodes and property into a dataset.
nodes.columns = ["Node_name"]                                                          # 🧸💬 Reanme of the node column.

types = nx.get_node_attributes(answer, "type");                                        # 🧸💬 Find the node attributes.
print( types );                                                                        # 🧸💬 See nodes object type.

nodes["type"] = nodes["Node_name"].apply( lambda x : types[x] if x in types.keys() else np.NaN );   # 🧸💬 Convert and save type to column.
nodes["labels"] = nodes["Node_name"].apply( lambda x : types[x] if x in types.keys() else x );      # 🧸💬 Convert and save label to column.
nodes["colours"] = nodes["Node_name"].apply( lambda x : "red" if x in types.keys() else "blue" );   # 🧸💬 Convert and save colours to column.

dict_label = { };                                                                       # 🧸💬 Create new empty dictionary for plotting.
for idx, node in enumerate(labels) :                                                    # 🧸💬 Iterates node from a labels array.
    dict_label[node] = nodes["labels"].iloc[idx];                                       # 🧸💬 Convert of labels to dictionary for plotting. 

# 🧸💬 I try to manage the property of the nodes graph, they are in dictionary. 
nx.draw(answer, with_labels=True, labels=dict_label, node_color=nodes["colours"].to_numpy() );      # 🧸💬 Plotting.
nodes.head( 5 )                                                                                     # 🧸💬 Print out sample.
```

### 🧸💬 Output

👧💬 🎈 Who is the centre and who are the strongest connections⁉️ </br>
🦭💬 Find the most communication node and attach a new node to the strongest nearby connection node. A new node can communicate with centre node with a single property same as Vincent and had high selection scores when challenging centre node or a higher possibility for route selection. </br>

```
Graph with 19 nodes and 24 edges
{'Andy': 'employee', 'Anaconda': 'movie', 'Mean Girls': 'movie', 'The Matrix': 'movie', 'Claude': 'employee', 'Monty Python and the Holy Grail': 'movie', 'Snakes on a Plane': 'movie', 'Frida': 'employee', 'The Shawshank Redemption': 'movie', 'The Social Network': 'movie', 'Georgia': 'employee', 'Joan': 'employee', 'Forrest Gump': 'movie', 'Kung Fu Panda': 'movie', 'Lee': 'employee', 'Pablo': 'employee', 'The Dark Knight': 'movie', 'Vincent': 'employee', 'The Godfather': 'movie'}
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/02.png">
</p>

### 🧸💬 Creating and manipulating graph with nodes connections property.
💃( 👩‍🏫 )💬 Sorted of connections property can determine expecting node for the development of connectivity by adding a traversal node by passing the strong nodes so the graph can have more properties and shared connectivity. </br>
🦤💬 In the police investigation, the strongest connectivity is a special relationship because criminals are smart they select to create the most performance connectivity way to work with safe and edges reach communications. Attach and perform is one technique to protect and learn from network connectivity because it is human relationships. </br>

```
G = answer_three()
plot_graph(G, weight_name="weight")
G.edges(data = True)
```

### 🧸💬 Output

```
EdgeDataView([('Frida', 'Pablo', {'weight': 2}), ('Frida', 'Vincent', {'weight': 2}), ('Frida', 'Andy', {'weight': 1}), ('Georgia', 'Andy', {'weight': 1}), ('Georgia', 'Claude', {'weight': 3}), ('Lee', 'Andy', {'weight': 1}), ('Lee', 'Joan', {'weight': 3}), ('Vincent', 'Pablo', {'weight': 1}), ('Andy', 'Pablo', {'weight': 1}), ('Andy', 'Joan', {'weight': 1}), ('Andy', 'Claude', {'weight': 1})])
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/03.png">
</p>

- - -
## Networks connectivity, graph domain problem to solution precise identify of selection conditions by target properties, connectivity, and conditions.

```
print(ans_one)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_one.nodes};

nodes = pd.DataFrame( ans_one.nodes );

# EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
dataset = pd.DataFrame(ans_one.edges(data=True), columns=["Sender", "Recipient", "time"])
dataset["time"] = dataset["time"].map( lambda x : x["time"] );


colours = ["red", "green", "blue", "yellow", "brown"];
dataset["index_num"] = dataset.index;
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];
dataset = dataset.groupby(by="Sender").first();
nodes_colours = list(dataset.iloc[:, 0].to_numpy());
nodes_colours = nodes_colours + ( 167 - len(nodes_colours) ) * ["red"]

### drawings
nx.draw(ans_one, with_labels=True, labels=labels, node_color=nodes_colours);
```

```
MultiDiGraph with 167 nodes and 82927 edges
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/04.png">
</p>

```
print(ans_six)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_six.nodes};

nodes = pd.DataFrame( ans_six.nodes );
# # EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
dataset = pd.DataFrame(ans_six.edges(data=True), columns=["Sender", "Recipient", "time"])
dataset["time"] = dataset["time"].map( lambda x : x["time"] );

colours = ["red", "green", "blue", "yellow", "brown"];
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];
dataset = dataset.groupby(by="Sender").first();
nodes_colours = list(dataset.iloc[:, 0].to_numpy());
nodes_colours = nodes_colours + ( 167 - len(nodes_colours) ) * ["red"]

### drawings
nx.draw(ans_one, with_labels=True, labels=labels, node_color=nodes_colours);
```

```
MultiDiGraph with 126 nodes and 82130 edges
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/05.png">
</p>

```
print("***", ans_twelve)
print("***", ans_six)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_six.nodes};

nodes = pd.DataFrame( ans_six.nodes );

# # EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
dataset = pd.DataFrame(ans_six.edges(data=True), columns=["Sender", "Recipient", "time"])
dataset["time"] = dataset["time"].map( lambda x : x["time"] );

colours = ["red", "green", "blue", "yellow", "brown"];
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];
dataset = dataset.groupby(by="Sender").first();
nodes_colours = list(dataset.iloc[:, 0].to_numpy());

nodes_colours = nodes_colours;

### drawings
nx.draw(ans_six, with_labels=True, labels=labels, node_color=nodes_colours);
```

```
*** 1
*** MultiDiGraph with 126 nodes and 82130 edges
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/06.png">
</p>

```
print(ans_thirteen)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_thirteen.nodes};

nodes = pd.DataFrame( ans_six.nodes );

# # EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
dataset = pd.DataFrame(ans_thirteen.edges(data=True), columns=["Sender", "Recipient", "time"])
dataset["time"] = dataset["time"].map( lambda x : x["time"] );

colours = ["red", "green", "blue", "yellow", "brown"];
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];
dataset = dataset.groupby(by="Sender").first();
nodes_colours = list(dataset.iloc[:, 0].to_numpy());

nodes_colours = nodes_colours + (["red"] * 11 );

### drawings
nx.draw(ans_thirteen, with_labels=True, labels=labels, node_color=nodes_colours);
```

```
Graph with 126 nodes and 3107 edges
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/07.png">
</p>
