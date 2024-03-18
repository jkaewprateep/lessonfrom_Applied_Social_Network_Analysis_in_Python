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

🦭💬 In complex connectivity nodes, we find identical nodes for the presence of a group or category identification. There is some potential to create of the category when there are multiple of nodes that stand out for multiple times of selection and identification. That means they had property and their relationships can filter or work with conditions or rules. </br>
💃( 👩‍🏫 )💬 Identical identification, it is not necessary to select the peak values or identical nodes in somewhat matter of way but these identical nodes need to present in the same manner in samples and can vary by property or neighbors. </br>
🦤💬 External interactions and internal interactions, there are property selection and response reactions when the property is easy to identify but response feedback properties such as addition number, multiplication, and order in the sequences. In a vending machine for example summing up the condition of exchange Baht coins from remain amount from input and costs is not a direct response from the vending machine. Some questions such as why the vending machine always returns one Bath coin for exchange often than two Bath coins even re-programming that is because of a chance they are selected from one bath and two Bath are not too different and multiplication array can support the preference values. </br>    

### 🧸💬 Machine learning and vending machine, add preference to solved one Bath and two Bath coins exchange problem.

🐑💬 ➰ There are multiple answers for some set of answers or numbers to exchange returns, to solve this add the preference or pre-calculation value. </br>
🦭💬 If the exchange return is 5 Bath the vending machine should return you 5 Bath coin, or two of two Bath coins with one Bath coin or fives of one Bath coins or ... </br>
🦭💬 Preference is easy to solve this problem with the number of coin types remaining in the system, but it will create a predictable type machine which should be prevented by its design. </br>
🦭💬 An alternate way is machine learning, they had internal preferences and external preferences from setting with synchronization, do not generate a predictable response machine. </br>
🦤💬 There is a reason behind this condition, commercial and business are required to create of development in the same area but they cannot directly infer into rules but by each turn, they add creativity into requirements to create a good way of competition. They had high competitiveness business competitors but they turned into creative ways. </br>
💃( 👩‍🏫 )💬 In example, there are electronics detective hacks of bank account balance payment from new type of vending machines and they need to have the background of data integrations in financial banking business to use of its time exceed capable before updated the event callback. </br>
👧💬 🎈 My reporter says found one old lady try to do it near his school. 👵...💸 🥺💬 It is just a timeout aunties you cannot cancel because the machine does not have events try using next method to reset. ( Some bare foot guy finding for food found her ) </br>

<p align="center" width="100%">
    <img width="60%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/08.png">
</p>

```
print(ans_one)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_one.nodes};                             # 🧸💬 Create an array collection from nodes.

nodes = pd.DataFrame( ans_one.nodes );                              # 🧸💬 Stored nodes property into a dataset.

# EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
# 🧸💬 Stored node data output into a dataset with column names.
dataset = pd.DataFrame(ans_one.edges(data=True), columns=["Sender", "Recipient", "time"])
# 🧸💬 Transfrom first element array into value and stored into dataset filed.
dataset["time"] = dataset["time"].map( lambda x : x["time"] );

colours = ["red", "green", "blue", "yellow", "brown"];              # 🧸💬 Create colours array.
dataset["index_num"] = dataset.index;                               # 🧸💬 Create an index number column.
# 🧸💬 Create a Node column from object type, node, or else.
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
# 🧸💬 Create a Colours column and assign of colour name for node.
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];                           # 🧸💬 Select dataset fields.
# 🧸💬 Group by sender duplicated select first.
dataset = dataset.groupby(by="Sender").first();                     
nodes_colours = list(dataset.iloc[:, 0].to_numpy());                   # 🧸💬 Phase a list of sender.
nodes_colours = nodes_colours + ( 167 - len(nodes_colours) ) * ["red"] # 🧸💬 Padding for plots.

### drawings
# 🧸💬 Plotting with label and node colour.
nx.draw(ans_one, with_labels=True, labels=labels, node_color=nodes_colours);
```

### 🧸💬 Output

```
MultiDiGraph with 167 nodes and 82927 edges
```

### 🧸💬 Visualization
👧💬 🎈 One more example is event attention identification when you have a unique action from all events in the same property. Is there anyone or an external performance, and that can be used for system events investigation. </br>
🐑💬 ➰ How many times to perform money withdraws account balance request to success ⁉️ It can determine attention not only from a responsive feedback system but IT communication. </br>
🦭(1)💬 This kind of tracking can not be performed at the network level before node.js or pre-settings firewall rules or central logs services are available. Not only tracking by sequence number, authentication method and tokens, communication parameters, application ID, and application authentication but input sequence distribution value or prevent hacking system. </br>
🦭(2)💬 They are tracking at the communication level and application parameters level, because of attached internal application can create or reuse communication parameters. </br>
🐐💬 Seek attention actions sometimes is easy but finding the inattention function sometimes it is sometimes difficult example finding accident saved password in some class file of an application is harder than finding an application seeking a password by tracking and repeating the action. </br>

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/04.png">
</p>

```
print(ans_six)
# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in ans_six.nodes};                              # 🧸💬 Create an array collection from nodes.

nodes = pd.DataFrame( ans_six.nodes );                               # 🧸💬 Stored nodes property into a dataset.
# # EdgeDataView([('1', '2', {'time': 1285658811}), ('1', '3', {'time': 1285657801})
# 🧸💬 Stored node data output into a dataset with column names.
dataset = pd.DataFrame(ans_six.edges(data=True), columns=["Sender", "Recipient", "time"])
# 🧸💬 Transfrom first element array into value and stored into dataset filed.
dataset["time"] = dataset["time"].map( lambda x : x["time"] );

colours = ["red", "green", "blue", "yellow", "brown"];               # 🧸💬 Create colours array.
# 🧸💬 Create a Node column from object type, node, or else.
dataset["Node"] = dataset["Sender"].apply( lambda x : True if x in labels.keys() else False );
# 🧸💬 Create a Colours column and assign of colour name for node.
dataset["Colours"] = dataset["Sender"] .apply( lambda x : colours[ int(x) % 5] );

dataset = dataset[["Sender", "Colours"]];                            # 🧸💬 Select dataset fields.
# 🧸💬 Group by sender duplicated select first.
dataset = dataset.groupby(by="Sender").first();
nodes_colours = list(dataset.iloc[:, 0].to_numpy());                      # 🧸💬 Phase a list of sender.
nodes_colours = nodes_colours + ( 167 - len(nodes_colours) ) * ["red"]    # 🧸💬 Padding for plots.

### drawings
# 🧸💬 Plotting with label and node colour.
nx.draw(ans_one, with_labels=True, labels=labels, node_color=nodes_colours);
```

### 🧸💬 Output

```
MultiDiGraph with 126 nodes and 82130 edges
```

### 🧸💬 Visualization - strongly connected graph.
🐐💬 For experiment purposes, the selection of none strongly connected nodes is identification but selecting strongly connected nodes is to find relative groups or periods as in periodic tables. </br>
🐑💬 ➰ Node density is one property to identify its category and can be composed of identical elements for tasks </br>

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

### 🧸💬 Output

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

### 🧸💬 Output

```
Graph with 126 nodes and 3107 edges
```

### 🧸💬 Visulaization

<p align="center" width="100%">
    <img width="100%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/07.png">
</p>

- - -

## 🧸💬 Closeness centrality, and betweenness centrality. It is an adaptation to many problems for global and local communications level and ability, how the target nodes repeat the same property or generate the effects with the same amount of the inputs. In the assignment example of the email and social media message communications.

💃( 👩‍🏫 )💬 The graph nodes had property and they had velocity, this property is difficult to determine and conclude into a qualitative value but we can observe this property by closeness centrality and the betweenness centrality, the property is not changed when these relationships remain. </br>
🦤💬 External observation can find location, speed and velocity but internal observation finds the actions but momentum can be both. </br>
🐑💬 ➰ That is because property changes create some work. </br>

```
import pandas as pd;                                                     # 🧸💬 Import data manager library.

G1 = nx.read_gml('assets/friendships.gml')                               # 🧸💬 Import data from a dataset.

ans_one = answer_one();                                                  # 🧸💬 Instant variable and assigned value from question one.
print( ans_one )                                                         # 🧸💬 Print out the output return from the previous step.

# 🧸💬 Define a graph from simple file, using file reader and Pandas.
labels = {n: n for n in G1.nodes};                                       # 🧸💬 Create an array collection of node property from
                                                                         # impoort dataset.

nodes = pd.DataFrame( G1.nodes );                                        # 🧸💬 Create instant of dataframe with node property.

# 🧸💬 Create an instant of a data frame from all node values with columns id, label, and properties.
dataset = pd.DataFrame(G1.edges(data=True), columns=["id", "label", "properties"]);
dataset = dataset.reset_index();                                         # 🧸💬 Reset the index of data frame, and reflect the index as a column.
dataset = dataset[["index", "id", "label", "properties"]];               # 🧸💬 Selection of dataset columns by name.

colours = ["red", "green", "blue", "yellow", "brown"];                   # 🧸💬 Create an array of colours name.
# 🧸💬 Create a column Node and assigned property, true if it is node.
dataset["Node"] = dataset["id"].apply( lambda x : True if x in labels.keys() else False );
# 🧸💬 Create a column Colours and assigned colours property, by multiplication of 5 assigned node colours from the colours array.
dataset["Colours"] = dataset["id"] .apply( lambda x : "purple" if x == 100 else colours[ int(x) % 5] );

# 🧸💬 Sample of the dataset by head function.
dataset.head()

# 🧸💬 Select the dataset column, id and Colours.
dataset = dataset[["id", "Colours"]];
# 🧸💬 Aggregate data by groupby function target column id, select first if found duplicated.
dataset = dataset.groupby(by="id").first();
# 🧸💬 Select and transform the output from the dataset for colour property next use in the plotting function.
nodes_colours = list(dataset.iloc[:, 0].to_numpy());
# 🧸💬 Padding of nodes_colours array to have the same shape as graph value inputs.
nodes_colours = nodes_colours + ( 1133 - 762 ) * ["red"]

G1_100 = list( G1 )[0:101];                                              # 🧸💬 Scopes variances.
G1_100 = set( G1_100 );                                                  # 🧸💬 Simplify the output as a single format.

labels = set(list(labels)[0:101]);                                       # 🧸💬 Scopes variances.

# nx.draw(G1, with_labels=True, labels=labels, node_color=nodes_colours);
# 🧸💬 Draw the selected nodes with labels property and colours to display the velocity of the graph nodes.
nx.draw_networkx_nodes(G1_100, pos=nx.spring_layout(G1_100), label=labels, node_color=nodes_colours[0:101])
```

### 🧸💬 Output

```
🧸💬 ( centrality, closeness and betweenness )
(0.0026501766784452294, 0.2654784240150094, 7.142902633244772e-05)
🧸💬 Plotting object.
<matplotlib.collections.PathCollection at 0x7f465017fc70>
```

### 🧸💬 Visulaization
🐑💬 ➰ It is floating around and shining, they had velocity but had position value, colours, and the betweenness property from function. </br>
🧸💬 Flawness ⁉️ 🦭💬 Perfect ‼️ </br>

<p align="center" width="100%">
    <img width="70%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/09.png">
</p>

```
import matplotlib.pyplot as plt                                          # 🧸💬 Import visualization library.

ans_two = answer_two();                                                  # 🧸💬 Use the output answer from question #2.

# 🧸💬 Find the graph betweenness centrality of import graph from nx.betweenness_centrality function returns an array collection.
graph_betweenness_centrality = nx.betweenness_centrality(G1, k=None, normalized=True, weight=None, endpoints=False, seed=None);
# 🧸💬 Sorted previous step return list from array value in descending order for the first 5 nodes found in list.
list_two = sorted( graph_betweenness_centrality, key=lambda x: graph_betweenness_centrality[x], reverse=True )[0:5]; 

# 🧸💬 Extract value from G1 graph by item id from list_two found in the previous step.
selected_G1 = [];
for item in list_two :
    selected_G1.append( list( G1 )[item - 1] );

# 🧸💬 Reset the index and create an index column from the index value.
dataset = dataset.reset_index();
dataset = dataset[["id", "Colours"]];                                   # 🧸💬 Select column name id and Colours.
# 🧸💬  Re-assign of Colours value by the selected node, pink is select otherwise gray.
dataset["Colours"] = dataset["id"] .apply( lambda x : "pink" if x in selected_G1 else "gray" );

dataset = dataset[["id", "Colours"]];                                   # 🧸💬 Select column name id and Colours.
dataset = dataset.groupby(by="id").first();                             # 🧸💬 Groupby id select first if duplivated.
nodes_colours = list(dataset.iloc[:, 0].to_numpy());                    # 🧸💬 Transfrom to an array for plotting.
nodes_colours = nodes_colours + ( 1133 - 762 ) * ["gray"]               # 🧸💬 Padding value for plotting function.

G1_100 = list( G1 )[0:301];                                             # 🧸💬 Scopes variances.
G1_100 = set( G1_100 );                                                 # 🧸💬 Transfrom into single form.

# nx.draw(G1, with_labels=True, labels=labels, node_color=nodes_colours);

selected_G1 = [];                                                       # 🧸💬 Instant of new list variable.
# 🧸💬 Create an instant of list_two list from the graph_betweenness_centrality from the paragraph initial and sorted by sample value
# from its array value in descending order.
list_two = sorted( graph_betweenness_centrality, key=lambda x: graph_betweenness_centrality[x], reverse=True );

for i in range( 5 ):                                                    # 🧸💬 Iterations of five.
    
    # selected_G1 = [];
    selected_G1 = selected_G1 + list_two[ i * 10 : (i * 10) + 10];      # 🧸💬 Padding value for plot function.
    # print( selected_G1 )

    for item in selected_G1 :                                           # 🧸💬 Iterate for all items in the selected nodes list.
        # selected_G1.append( list( G1 )[item - 1] );
        if item < len( nodes_colours ) :                                # 🧸💬 If it is selected node.
            nodes_colours[item] == "pink";                              # 🧸💬 Assign Pink colours.

    # 🧸💬 Draws the selected nodes with position values, label property, and colours property.
    nx.draw_networkx_nodes(G1_100, pos=nx.spring_layout(G1_100), label=labels, node_color=nodes_colours[0:301]);
    plt.show();                                                         # 🧸💬 Flush memory.
```

<p align="left" width="100%">
    <img width="19%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/10.png">
    <img width="19%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/11.png">
    <img width="19%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/12.png">
    <img width="19%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/13.png">
    <img width="19%" src="https://github.com/jkaewprateep/lessonfrom_Applied_Social_Network_Analysis_in_Python/blob/main/14.png">
</p>

- - -

## 🧸💬 Graph and prediction problem, the prediction function can be performed in both condition and graph mode. In the graph mode prediction, the strongest node will be selected for communication and estimate value.

🧸💬 There should be multiple times of production output evaluation but thank you for the evaluation function for best path selection, strongest connection, and shared weight distribution </br> 
🐑💬 ➰ There is an estimation step before saving the trained model, in some experiment a small value changes very little depending on the machine and environment and does not effect of the prediction result because it is less than 0.0000001 sometimes as you see from the Applied machine learning course, you need to saved and load trained model to have the same value for the course assignment validation. If do not the answer still correct but the instructor shows you to identification and workload property ( In calculation workload property is reserved for work that does not effects the work results ). </br> 
💃( 👩‍🏫 )💬 In some work tasks, prediction probability is capable as a sample of the selection actions response when category and identification require precision and test function results. In prediction, results contain label target prediction and confidence scores or multiplication of the input and linear model weight matrix. In a real-time response system, evaluation helps select available functions reconcile same as transmission and some control devices for manual and communication. </br>
🦤💬 In n-grams speech recognition does not require prediction but an evaluation, prediction also can be performed to identify targets from categorized problems they are different methods but they can work on the same tasks. use evaluation to save process calculation and use prediction to determine and test training weight results. Evaluation use trained model weights same as prediction. </br>
💃( 👩‍🏫 )💬 ⁉️ Is it correct only ```eval()``` is enough for play AI cars racing games ⁉️  </br>
👨🏻‍🏫(1)💬 Possible and it is use ```eval()``` for responsive machine too. In some games, the evaluation method performs better not because of it is faster but it is game's player response to the environment.  </br>
👨🏻‍🏫(2)💬 We removed ```eval()``` function and should use ```prediction()``` function for evaluation results because of it does not effect the speed response but performs testing as well.  </br>
👨🏻‍🏫(1)💬 Yes, I am still use TF 1.x . </br>

### 🧸💬 Sample data query
```
list(G.nodes(data=True))[:5] 
```

### 🧸💬 Output
```
[(0, {'Department': 1, 'ManagementSalary': 0.0}),
 (1, {'Department': 1, 'ManagementSalary': nan}),
 (581, {'Department': 3, 'ManagementSalary': 0.0}),
 (6, {'Department': 25, 'ManagementSalary': 1.0}),
 (65, {'Department': 4, 'ManagementSalary': nan})]
```

### 🧸💬 Prediction example
🐑💬 ➰ Using linear model to predict target value from connectivity barrier. </br>
🧸💬 Review ```Applied Machine Learning in Python note``` for regression training. </br>

```
def salary_predictions():
    from sklearn.preprocessing import StandardScaler                    # 🧸💬 Import Scaler linear model.
    # 🧸💬 Import linear model classifier and Gradient Boosting classifier.
    from sklearn.ensemble import RandomForestClassifier, GradientBoostingClassifier
    
    # 🧸💬 Create instant of dataframe
    input_data = pd.DataFrame();
    target = nx.get_node_attributes(G, 'ManagementSalary');
    # 🧸💬 Return target node attributes from target node
    
    # 🧸💬 Calculation path, 🐑💬 ➰ The same ranges and possition in the networks and how it is close to central average?
    degree_centrality = nx.degree_centrality(G)                         # 🧸💬 Find degree of centrality.
    closeness_centrality = nx.closeness_centrality(G)                   # 🧸💬 Find closeness centrality.
    betweenness_centrality = nx.betweenness_centrality(G)               # 🧸💬 Find betweeness centrality.
    for node in target.keys():                                          # 🧸💬 Create data frame from target nodes.
        row_features = pd.DataFrame([[degree_centrality[node], closeness_centrality[node],
                                      betweenness_centrality[node], target[node]]], index=[node])
        input_data = pd.concat([input_data, row_features], axis=0)
    train_data = input_data[~input_data[3].isnull()]                    # 🧸💬 Create training input data reshape.
    test_data = input_data[input_data[3].isnull()]                      # 🧸💬 Cretaet testing input data array.
    GradientBoosting = GradientBoostingClassifier()                                  # 🧸💬 Create instant of Gradient Boosting classifier.
    GradientBoosting.fit(train_data[[0,1,2]].values, train_data[3].values)           # 🧸💬 Training GradientBoosting classifier.
    preds = GradientBoosting.predict_proba(test_data[[0,1,2]].values)[:,1]           # 🧸💬 Call prediction probability value function.
    return pd.Series(preds, index=test_data.index)                      # 🧸💬 Return as index and predictions prob. value.
```

## 🧸💬 New connections dataset, working with graph predictions.

```
future_connections = pd.read_csv('assets/Future_Connections.csv', index_col=0, converters={0: eval})
future_connections.head(10)
```
