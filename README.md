#include <stdio.h>
typedef struct{
	int No;
}vertextype;
typedef struct{
	int edges[maxsize][maxsize];
	vertextype vex[maxsize];
	int n,e;
}MGraph;

typedef struct{
	int cidx;
	struct arcnode *next;
}arcnode;
typedef struct{
	int data;
	arcnode *first;
}vnode; 
typedef struct
{
	vnode adjlist[maxsize];
	int n,e;
}AGraph;

void Prim(MGraph g,int v0,int &sum)
{
	int i,v,k,min;
	int visit[maxsize];
	int lowcast[maxsize];
	
	for(i=0;i<g.n;++i)
	{
		lowcast[i]=g.edges[v0][i];
		visit[i]=0;
	}
	visit[v0]=1;
	v=v0;
	sum=0;
	for(i=0;i<g.n-1;++i)
	{
		min=INF;//N定义为无限大（比矩阵中所有边的权值都大）
		for(int j=0;j<g.n;++j)
		{
			if(visit[j]==0&&min>lowcast[j])
			{
				min=lowcast[j];
				v=j;
			}
		 } 
		visit[v]=1;
		sum+=min;
		for(int j=0;j<g.n;++j)
		{
			if(visit[j]==0&&lowcast[j]>g.edges[v][j])
			lowcast[j]=g.edges[v][j];
		}
		
	}
}# Data-Struct
Graduate student
