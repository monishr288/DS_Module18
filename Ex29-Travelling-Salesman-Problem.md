# Ex29 Travelling Salesman Problem
## DATE: 16.5.25
## AIM:
To write a C Program to implement Travelling Salesman Problem for finding shortest path.
## Algorithm
1. Input the number of cities and the cost adjacency matrix.
2. Use a backtracking approach to generate all permutations of the cities.
3. For each permutation, calculate the cost of visiting cities in that order and returning to the starting point.
4. Track the minimum cost path.
5. Output the minimum cost of traversal and the corresponding path.
  

## Program:
```
/*
Program to implement Travelling Salesman Problem for finding shortest path
Developed by: MONISH R
RegisterNumber:  212223220061
*/
#include<stdio.h>
int a[10][10],visited[10],n,cost=0;

void get()
{
	int i,j;
		scanf("%d",&n);
	for(i=0;i < n;i++)
	{
			for( j=0;j < n;j++)
			scanf("%d",&a[i][j]);
		visited[i]=0;
	}
	}

void mincost(int city)
{
	int ncity;
	int least(int);
	visited[city]=1;	
	printf("%d -->",city+1);
	ncity=least(city);
	if(ncity==999)
	{
		ncity=0;
		printf("%d",ncity+1);
		cost+=a[city][ncity];
		return;
	}
	mincost(ncity);
}

int least(int c)
{
	int i,nc=999;
	int min=999,kmin;
	for(i=0;i < n;i++)
	{
		if((a[c][i]!=0)&&(visited[i]==0))
			if(a[c][i] < min)
			{
				min=a[i][0]+a[c][i];
				kmin=a[c][i];
				nc=i;
			}
	}
	if(min!=999)
		cost+=kmin;
	return nc;
}

void put()
{
	printf("\n\nMinimum cost:%d",cost);
	}

int main()
{
	get();
	mincost(0);
	put();
	return 0;
	}

```

## Output:


![Screenshot 2025-05-16 211513](https://github.com/user-attachments/assets/f25af754-d1dd-4633-a4ca-b1cbff1398e0)

## Result:
Thus, the C program to implement Travelling Salesman Problem for finding shortest path is implemented successfully.
