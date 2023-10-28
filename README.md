# 19AI405 FUNDAMENTALS OF ARTIFICIALINTELLIGENCE 
# Laboratory Experiments

## Exp 1 : Implement Depth First Search Traversal of a Graph

```py
Developed by : Sri Varshan P
Register no. : 212222240104
```

### Aim

To Implement Depth First Search Traversal of a Graph using Python 3.

#### Theory

Depth First Traversal (or DFS) for a graph is like Depth First Traversal of a tree. The only catch here is that, unlike trees, graphs may contain cycles (a node may be visited twice). Use a Boolean visited array to avoid processing a node more than once. A graph can have more than one DFS traversal. Depth-first search is an algorithm for traversing or searching trees or graph data structures. The algorithm starts at the root node (selecting some arbitrary node as the root node in the case of a graph) and explores as far as possible along each branch before backtracking.

#### Steps of implementation :

##### Step 1 :

Initially, stack and visited arrays are empty.
Queue and visited arrays are empty initially. Stack and visited arrays are empty initially.

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/7ae1fe52-7cf7-452b-8439-4f2b7bf67b74)

##### Step 2 :
Visit 0 and put its adjacent nodes which are not visited yet into the stack.
Visit node 0 and put its adjacent nodes (1, 2, 3) into the stack.

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/82e90863-9ea1-44cb-96e8-95129a313782)

##### Step 3 :
Now, Node 1 at the top of the stack, so visit node 1 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/0e15eb91-e0a7-40d9-9bc5-f0b95753cb86)

##### Step 4 :
Now, Node 2 at the top of the stack, so visit node 2 and pop it from the stack and put all of its adjacent nodes which are not visited (i.e, 3, 4) in the stack.
Visit node 2 and put its unvisited adjacent nodes (3, 4) into the stack

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/9a4c3cde-89cf-4b37-9385-9968dd033e4b)

##### Step 5 :
Now, Node 4 at the top of the stack, so visit node 4 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
Visit node 4

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/55bf07c4-e04c-4ecf-bcb4-474a65abd2f3)

##### Step 6 :
 Now, Node 3 at the top of the stack, so visit node 3 and pop it from the stack and put all of its adjacent nodes which are not visited in the stack.
 Now, the Stack becomes empty, which means we have visited all the nodes, and our DFS traversal ends.

 ![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/0838aa06-b2ed-4ba5-9440-ea73f1106cbc)

#### Algorithm :
1. Construct a Graph with Nodes and Edges
2. Depth First Search Uses Stack and Recursion
3. Insert a START node to the STACK
4. Find its Successors Or neighbors and Check whether the node is visited or not
5. If Not Visited, add it to the STACK. Else Call The Function Again Until No more nodes needs to be visited.

#### Program :
```py
Developed by : Sri Varshan P
Register no. : 212222240104

from collections import defaultdict
def dfs(graph,start,visited,path):
   path.append(start)
   visited[start]=True
   for neighbour in graph[start]:
       if visited[neighbour]==False:
           dfs(graph,neighbour,visited,path)
           visited[neighbour]=True
   return path
graph=defaultdict(list)
n,e=map(int,input().split())
for i in range(e):
   u,v=map(str,input().split())
   graph[u].append(v)
   graph[v].append(u)
#print(graph)
start='A'
visited=defaultdict(bool)
path=[]
traversedpath=dfs(graph,start,visited,path)
print(traversedpath)
```
#### First Sample :

##### Input :

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/c31ddf74-c0b2-4de9-86d2-b97e54031b24)

##### Output :

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/a0a8f903-739a-4081-8827-bb9b6438d658)

#### Second Sample :

##### Input :

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/4d9af44e-52f7-41b6-954a-fa3d675d6c2c)

##### Output :

![image](https://github.com/PSriVarshan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/114944059/ba25ef9f-3f67-4593-ab91-1826816d6a3f)

#### Result :

Thus, a Graph was constructed and implementation of Depth First Search for the same graph was done successfully.
