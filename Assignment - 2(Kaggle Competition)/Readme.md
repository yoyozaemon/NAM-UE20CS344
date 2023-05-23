## Problem Statement
<p>The Education Minister of India has access to the data of all engineering students in India. They want to gain insights on which Branch of Engineering is popular and which branch of engineering a new student might choose (or might have more demand) so that you can accordingly increase the intake for that branch. Instead of gaining insights from a boring table, you're given a fancy graph of the interaction between all students in the country and the courses they take :)</p>

**Your task is to predict which branch of engineering a particular student in the graph has taken.**

### Description:
A social graph between students refers to a graphical representation of the relationships or connections that exist between students within a particular social network or community. This graph typically shows how students are connected to each other based on their interactions, communication, shared interests, and other social factors.
The graph is usually represented as a set of nodes or vertices (representing individual students) and edges (representing connections or relationships between the students).

The social graph can be used to gain insights into the social dynamics within a group of students. This information can be valuable for educational institutions, researchers, or social scientists who want to understand how students interact and collaborate with each other in various contexts.

You are given the social graph of students who attend an engineering college. Students attend courses provided by the engineering college. Two or more students/node can share/attend the same courses. Hence, each **node is a student labeled with their respective Stream of Engineering.** An **edge between two nodes/students will represent that those two students share/attend the same class.**

Visualizing this graph will be as per this image here. The legend provided in the top right gives the Streams for each student and how they are colored. The link between them shows that they share some same course.
![alt text] (./res/img.jpg)


### What you need to do
Considering the above mentioned graph, there are few nodes who have are not labeled to have a class (As shown in the image 20% didn't have labels). **You will have to predict the branch for the Node IDs present in** `sample_submission.csv`. You will have to make a graph from the nodes and edges list provided in Data, run Traditional ML and Graph Learning techniques to classify their Branch, based on some attributes of the nodes which describe their connectivity between other students.

General framework of steps to be followed:

Creating a networkx graph from a given edge list and node list
Generate features (ensure to save them as methods like node2vec, random walk etc. require high compute resources so you should not have to regenrate them)
Converting networkx graph to Pytorch geometric graph (or any other suitable format for your GNN)
For the pytorch geometric graph, add the features given in features.pt and concatenate any additional features you wish to generate
Use a GNN (ex: GCN) and train on the graph. Use the train and test masks as needed when defining the accuracy and to predict for the GNNs
The final output required is the prediction value of branch for the test nodes only
You are free to experiment with traditional ML using graph features as input, or using diff GNN architectures, etc.

### Deliverables
1. Submission file (.csv) with predictions (`submission.csv`)
2. Kaggle kernel notebook (with documentation)
