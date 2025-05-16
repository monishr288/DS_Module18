# Ex28 Dijkstra’s Algorithm
## DATE: 16.5.25
## AIM:
To write a C Program to implement Dijkstra's Algorithm to find the shortest path

## Algorithm
1. Input the number of vertices and the graph as an adjacency matrix.
2. Choose a starting vertex (source).
3. Initialize the distance of source to 0 and all other vertices to infinity.
4. Mark all vertices as unvisited.
5. Repeat for all vertices:
   - Select the unvisited vertex with the smallest distance.
   - Update the distance of its adjacent vertices.
   - Mark the current vertex as visited.
6. Repeat until all vertices are visited.
7. Print the shortest distance from the source to each vertex.

## Program:
```
/*
Program to implement Dijkstra's Algorithm 
Developed by: MONISH R 
RegisterNumber:  212223220061
*/
#include<stdio.h>
#define INFINITY 9999
#define MAX 10
 
void dijkstra(int G[MAX][MAX],int n,int startnode);
 
int main()
{
int G[MAX][MAX],i,j,n,u;
scanf("%d",&n);
for(i=0;i<n;i++)
for(j=0;j<n;j++)
scanf("%d",&G[i][j]);
scanf("%d",&u);
dijkstra(G,n,u);
return 0;
}
 
void dijkstra(int G[MAX][MAX],int n,int startnode)
{
 
int cost[MAX][MAX],distance[MAX],pred[MAX];
int visited[MAX],count,mindistance,nextnode,i,j;
//pred[] stores the predecessor of each node
//count gives the number of nodes seen so far
//create the cost matrix
for(i=0;i<n;i++)
for(j=0;j<n;j++)
if(G[i][j]==0)
cost[i][j]=INFINITY;
else
cost[i][j]=G[i][j];
//initialize pred[],distance[] and visited[]
for(i=0;i<n;i++)
{
distance[i]=cost[startnode][i];
pred[i]=startnode;
visited[i]=0;
}
distance[startnode]=0;
visited[startnode]=1;
count=1;
while(count<n-1)
{
mindistance=INFINITY;
//nextnode gives the node at minimum distance
for(i=0;i<n;i++)
if(distance[i]<mindistance&&!visited[i])
{
mindistance=distance[i];
nextnode=i;
}
//check if a better path exists through nextnode
visited[nextnode]=1;
for(i=0;i<n;i++)
if(!visited[i])
if(mindistance+cost[nextnode][i]<distance[i])
{
distance[i]=mindistance+cost[nextnode][i];
pred[i]=nextnode;
}
count++;
}
 
//print the path and distance of each node
for(i=0;i<n;i++)
if(i!=startnode)
{
printf("Distance of node%d=%d\n",i,distance[i]);
printf("Path=%d",i);
j=i;
do
{
j=pred[j];
printf("<-%d",j);
}while(j!=startnode);
}
}

```

## Output:


![Screenshot 2025-05-16 211329](https://github.com/user-attachments/assets/c7dfbe06-6faf-42c7-a47a-8c157fcac988)

## Result:
Thus, the Program to implement Dijkstra's Algorithm to find the shortest path is implemented successfully.
