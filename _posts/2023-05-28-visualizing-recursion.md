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
