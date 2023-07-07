---
tags: [recursion]
---
![tree](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Screenshot+2023-05-28+at+4.46.33+PM.png)
Picture 1, Tree  


![timeline](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Screenshot+2023-05-28+at+4.56.39+PM.png)
Picture 2, Timeline

if the above tree is traversed recursively using DFS, then order in which the nodes are processed is given in the second picture. In the timeline, the line at left of node indicates when the node is accessed and the line at the right indicates the time when its processing is complete. For example, node B is accesed first at time T=2 and its processing finishes at T=15.
Order of finish time for nodes are
T=5, node H,  
T=7, node I,  
T=8, node D,  
T=11, node J,  
T=13, node K,  
T=14, node E,    
T=15, node B,  
T=19, node L,  
T=21, node M  
T=22, node F,  
T=25, node N,  
T=27, node O,  
T=28, node G  
T=29, node C,  
T=30, node A.  

It becomes clear that the recurive processing finishes processing the nodes in the order H, I, D, J, K, E, B, L, M, F, N, O, G, C, A. In words, the recursive processing first goes to the bottom left to process node H and then procesees all children nodes before processing the parent node.

![Path](https://chaitanyavardhan-blog-assets.s3.amazonaws.com/Recursion+3.png) 
diagram 3 

The ugly looking diagram above shows the path envelope with arrows indicating the direction of travel. While traveling on the path, when two opposing sides of the nodes are touched then that node has been processed. So, the first turn at bottom left is when node H has been processed. The milestones on this crooked ugly path will be in the following order: start A, start B, start D, start H, finish H, start I(don't go up to D as there is a sibling node I), finish I, finish D, start E, start J, finish J, start K, finish K, finish E, finish B, start C, start F, start L, finish L, start M, finish M, finish F, start G, start N, finish N, start O, finish O, finish G, finish C and finally finish A. We are done!!!.  

Time Complexity: There are 15 nodes and 14 directed arrows between them. The node A is done only at time T = 30. So, time taken is BigOh(Vertex + Edges).  

Space Complexity: This one is clear from the diagram 2 that shows the disks stacked on top of one another. The maximum height of the disk is 4 during the entire processing. This is also the depth of the tree. So, space consumed is BigOh(Depth of Tree).