#include<stdio.h>
#define maxsize 100 

//图的顺序存储结构 
typedef struct{
	int No;
}vertextype;

typedef struct{
	int edges[maxsize][maxsize];
	vertextype vex[maxsize];
	int n,e;
}MGraph;

int v[maxsize];
//取顶点 

int get_top(int p)
{
	while(p!=v[p])
	p=v[p];
	return p; 
 } 
 typedef struct{
 	int a,b;
 	int w;
 }Road;
 Road road[maxsize];
 
 void kruscal(Road road[],int &sum,MGraph g)
 {
 	int a,b;
	 sum=0;
	 for(int i=0;i<g.n;++i)
	 {
	 	v[i]=i;
	  } 
	  sort(road,g.e);//sort（）函数将road数组按照边权值进行从小到大排列 
	  for(int j=0;j<g.e;++j)
	  {
	  	a=get_top(road[i].a);
	  	b=get_top(road[i].b);
	  	if(a!=b)
	  	{
	  		v[a]=b;
	  		sum+=road[i].w;
		  }
	  }
	return;
 }
