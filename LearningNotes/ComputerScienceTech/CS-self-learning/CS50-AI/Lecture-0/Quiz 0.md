# Question 1

**Between depth first search (DFS) and breadth first search (BFS), which will find a shorter path through a maze?**
## My Answer (Wrong)
- BFS will always find a shorter path than DFS. 
- BFS always search step by step, exploring every possible route. It will definitely find the shortest path even though it may take a long time when there are massive path in the maze. 
## Correct Answer
- BFS will sometimes, but not always, find a shorter path than DFS.
- BFS will always find the shortest path in terms of the number of edges in an unweighted graph because it explores all nodes at present depth level before moving on to the next level.
- However, **BFS does not account for weights on edges.** If the graph has weights, BFS does not guarantee finding the shortest path in terms of total weight. In contrast, DFS may accidentally find a path with a lower total weight due to the specific traversal order, thought it doesn't guarantee this.
# Question 2
**Consider the below maze. Grey cells indicate walls. A search algorithm was run on this maze, and found the yellow highlighted path from point A to B. In doing so, the red highlighted cells were the states explored but that did not lead to the goal.**
![[Pasted image 20240704134338.png]]
 **Of the four search algorithms discussed in lecture — depth-first search, breadth-first search, greedy best-first search with Manhattan distance heuristic, and A* search with Manhattan distance heuristic — which one (or multiple, if multiple are possible) could be the algorithm used?**

## My Answer (Correct)
- It could be DFS and It can not be BFS.
- It could not be A* or greedy best-first search. At point (7, 1), we will go up to (7, 2) when adapting the A* or GBFS, because the Manhattan distance is less if we go up. However the fact is that we go down at that point instead of going up.
# Question 3
**Why is depth-limited minimax sometimes preferable to minimax without a depth limit?**
## My Answer (Wrong)
Depth-limited minimax will achieve the same output as minimax without a depth limit, but can sometimes use less memory
## Correct Answer
Depth-limited minimax can arrive at a decision more quickly because it explores fewer states. It may not achieve the same output as minimax, for it ignored some states where we can get the best decision.
# Question 4
**Consider the Minimax tree below, where the green up arrows indicate the MAX player and red down arrows indicate the MIN player. The leaf nodes are each labelled with their value.**
![[Pasted image 20240704140255.png]]
**What is the value of the root node?**
## My Answer
5