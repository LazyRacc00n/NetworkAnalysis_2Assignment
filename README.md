# Network Analysis: Assignment 2

Second assignment of the network analysis course

## Part 1

For the first part of the assignment we performed the experiments of the option number 1, which plans to perform *robustness* test on small graph.
The tests of the robustness are performed simulating different types of attack, turning off nodes with some critera:

- **Higest betweenness**.
- **Highest degree nodes**.
- **Higest pagerank**.
- **Random Nodes**.

For each of the above techniques is performed the test of the robustness as following: fixed one tecnique, is choosen the node and it is removed, and then is saved the current size of the giant componte and the diameter. After the execution of the tests for each technique, the results are plotted in order to compare the behavior of the networks with different types of attacks.

</br></br>

### Karate Club Graph
The first, showed in *figure 1*, is the already known **Zachary’s Karate Club** graph, which is a social network of a university karate club. This network is composed by 34 nodes ( member of a karate club ), and there are links between pairs of members who interacted outside the club.

<figure align=center>
    <img src="./images/graph1.png" width="50%" height="50%">
    <figcaption> <i> Figure 1 - Karate Club Graph </i> </figcaption>
  
</figure>

The figure below on the left shows the relative size of the giant component (computed by dividing the size of the giant component with the size of the original graph, since the such a network is connected) as the nodes of the graph are sequentially removed.
The networks is more robust against random failure, and in such case the critical threshold <img src="https://latex.codecogs.com/svg.image?\inline&space;f_c"/> is more and less 0.7. By contrast the network seems to be very vulnerable to all the target attacks with a <img src="https://latex.codecogs.com/svg.image?\inline&space;f_c =0.2"/>. With high degree attack and betweenness attack the behavior is the same, in fact are overlapped.
The figure on the right, instead, shows how the diameter changes depending on the type of network attack. Again, the trends of the high degree attack and the betweeness attack are overlapped. For this kind of attacks and also for the pagerank attack,  we have a small increase in diameter at the beginning, but then decrease at the critical threshold, 0.2, going from 6 to 0 very quickly. We have a similar situation also with the random attack, in which we have an increse of the diameter before the critical threshold, 0.7, and then a drastic decreasement of the diameter which goes rapidly to zero.
<table><tr>
<td> <img src="./images/Karate%20Club_giant_component_size.png"> </td>
<td> <img src="./images/Karate%20Club_diameter.png" /> </td>
</tr></table>

###  Erdős–Rényi Random Graph

The second graph we used is a random graph, generated with the the Erdős–Rényi model.

<figure align=center>
    <img src="./images/graph2.png" width="50%" height="50%">
    <figcaption> <i> Figure 2 - Erdős–Rényi Random Graph - N = 200, p = 0.1 </i> </figcaption>
</figure>

With this kind of network, the situation changes a lot respect to the preiovs network. Observing the graphic below of the giant-component, you can notice that the Erdős–Rényi random graph presents an not very robustness against failuers with all types of network attacks. In fact, with all the target attacks, but also with the random attack the size of the giant component decrease monotonically, untill they reach the critical threshold, and when this happens the giant component goes faster to 0. Again, as in the case of the Karate Club network, the network is more robust against the random attack with a critical threshold <img src="https://latex.codecogs.com/svg.image?\inline&space;f_c"/> equal to more or less 0.9. With the target attacks, instead, we have <img src="https://latex.codecogs.com/svg.image?\inline&space;f_c = 0.9"/>.
In the graphic on the left, i.e., the one representing the diamter variations, it is clear that this network is robust to random attack, in fact, the diameter does't change much, it oscillates in a small range ( roughly [ 0.4 - 0.5 ] ), untill to <img src="https://latex.codecogs.com/svg.image?\inline&space;f = 0.8"/>, where there is a small increase, and then, it decreases at the critical threshold 0.9. On the other hand, with the target attacks, instead, the diameter continues to increase untill the critical threshold 0.8, and then goes quickly to 0. This means that, the target attacks, attack the interconectedness of the netowk, and hence also the ability of two nodes to communicate with each other, by increasing the lengh of the path between two nodes that want communicate.

<table><tr>
<td> <img src="./images/Erdos%20Renyi%20Graph_giant_component_size.png"> </td>
<td> <img src="./images/Erdos%20Renyi%20Graph_diameter.png" /> </td>
</tr></table>

## Part 2

### Facebook Circles Combined

<table><tr>
<td> <img src="./images/Facebook%20Circles%20Combined_giant_component_size.png"> </td>
<td> <img src="./images/Facebook%20Circles%20Combined_diameter.png" /> </td>
</tr></table>





We performed the same experiments on the Facebook dataset we already used in the first assignment.