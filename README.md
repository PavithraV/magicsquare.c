# magicsquare.c
#include<stdio.h>
#include<math.h>
#define n 9
int magicsquare(int a[3][3],int i,int j,int count)
{
	  int k , m;
	  a[i][j] = count;
	  while(count<n)
	  {	
		    ++count;
		    k = 3- i-((i+1)%3);
		    m=(j+1)%3;
		    if(!a[k][m])
		    {
			       a[k][m] = count;
			       i = k;
             j = m;	
		    }
		    else
		    {
			       i = (i+1)%3;
			       a[i][j] = count;
			
		    }
		}
}

int main()
{
      int a[3][3]={0};
	    int i,j,n = 3;
	    magicsquare(a,0,1,1);
	    for(i=0;i<n;i++)
	    {
		      printf("\n");
		      for(j=0;j<n;j++)
          {
			         printf("%d\t",a[i][j]);
          }
    	}
}

