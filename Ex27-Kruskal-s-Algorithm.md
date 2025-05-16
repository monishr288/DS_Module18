# Ex27 Kruskal’s Algorithm
## DATE: 16.5.25
## AIM:
To write a C program to implement Kruskal's Algorithm for finding minimum cost

## Algorithm

1. Input the number of vertices and edges.
2. Input all the edges with their corresponding weights.
3. Sort all edges in ascending order based on weight.
4. Initialize a parent array for disjoint-set.
5. For each edge (u, v):
   - Find the roots of u and v.
   - If they belong to different sets, include the edge in MST and union their sets.
6. Repeat until (n-1) edges are selected.
7. Display the selected edges and total cost.

## Program:
```
/*
Program to implement Kruskal's Algorithm
Developed by: MONISH R
RegisterNumber:  212223220061
*/
#include <stdio.h>
    #include <stdlib.h>
    int i,j,k,a,b,u,v,n,ne=1;
    int min,mincost=0,cost[9][9],parent[9];
    int find(int);
    int uni(int,int);
    int main()
    {
          scanf("%d",&n);
          for(i=1;i<=n;i++)
     {
     for(j=1;j<=n;j++)
     {
     scanf("%d",&cost[i][j]);
     if(cost[i][j]==0)
     cost[i][j]=999;
     }
     }
         while(ne < n)
     {
     for(i=1,min=999;i<=n;i++)
     {
     for(j=1;j <= n;j++)
     {
     if(cost[i][j] < min)
     {
     min=cost[i][j];
     a=u=i;
     b=v=j;
     }
     }
     }
     u=find(u);
     v=find(v);
     if(uni(u,v))
     {
     printf("%d edge (%d,%d) =%d\n",ne++,a,b,min);
     mincost +=min;
     }
     cost[a][b]=cost[b][a]=999;
     }
     printf("Minimum cost = %d\n",mincost);
     return 0;
       }
    int find(int i)
    {
     while(parent[i])
     i=parent[i];
     return i;
    }
    int uni(int i,int j)
    {
     if(i!=j)
     {
     parent[j]=i;
     return 1;
     }
     return 0;
    }

```

## Output:

![Screenshot 2025-05-16 211120](https://github.com/user-attachments/assets/8083a0b0-a91c-405e-af35-b85f275c6d62)


## Result:
Thus, the C program to implement Kruskal's Algorithm for finding minimum cost is implemented successfully.
