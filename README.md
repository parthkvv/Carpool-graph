# Car-pool-algorithm
This project designed a min matching algorithm to match riders requesting carpool in Manhattan in order to save total travel distance.

## Min Matching algorithm
We formed an undirected graph with nodes represent passengers and edges represent their sharing plan. Using maximum matching with minimum weight algorithm, we can find the best sharing plan with the minimum total distance.

### Distance between passengers
Based on Manhattan distance (π(π₯1, π₯2), π(π¦1, π¦2), π(π, π) = |π₯1 β π¦1| + |π₯2 β π¦2|), we defined the distance between each two passengers π(π, π)1 in five scenarios:

<br />a. Pick up π then pick up π then drop off π then drop up π: 
<br />β’ π(ππ)=π(1)=π(π1π1)+π(π1π2)+π(π2π2)
<br />b. Pick up π then pick up π then drop off π then drop up π:
<br />β’ π(ππ)=π(2)=π(π1π1)+π(π1π2)+π(π2π2)
<br />c. Pick up π then pick up π then drop off π then drop up π: 
<br />β’ π(ππ)=π(3)=π(π1π1)+π(π1π2)+π(π2π2)
<br />d. Pick up π then pick up π then drop off π then drop up π:
<br />β’ π(ππ)=π(4)=π(π1π1)+π(π1π2)+π(π2π2) 
<br />d.π and π travels on his/her own:
<br />β’ π(ππ)=π(5)=π(π1π2)+π(π1π2)

### Level of service
Passengers are not pooling with someone if the total travel distance he spends on a shared vehicle will exceed 25% more then traveling on his/her own. We call it βlevel of serviceβ to guarantee the quality of vehicle sharing.


For passenger(π):
<br />if π(π1π1)+ π(π1π2)>1.25π(π1π1):
<br /> set π(1) as +β
<br />if π(π1π1)+ π(π1π2)+ π(π2π2)>1.25π(π1π1): 
<br />set π(2) as +β
<br />if π(π1π2) + π(π2π2) > 1.25π(π1π1):
<br />set π(4) as +β

<br />Repeat it for all passengers and output all the distance. The weight of two passengers is defined as:
<br />π(ππ) = min{π(1), π(2), π(3), π(4), π(5)}.

### Min Matching
After defining all the weight of edges, we formed a complete graph to represent passengers and their best way of pooling with each other.

As shown in the figure below, there are four passengers π΄, π΅, πΆ and π· with weights and way of pooling marked on edges. The maximum matching of all passengers with a minimum total weight is pair π΄ with π· using scenario 1 and pair π΅ with πΆ using scenario a.

![alt text](https://github.com/Melody-Meng/Car-pool-algorithm/blob/master/figure1.png)
