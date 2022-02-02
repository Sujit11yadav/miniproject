#include<stdio.h>
#include<conio.h>

void main()
{
	int i,n,sum=0,count=0,qunt, x,s=0,t=0,a[10],b[10],temp[10];
 
	float avg_wt, avg_tat;
	printf("Total No of Cars:");
	scanf("%d", &n);
	x=n;
	
	for(i=0;i<n;i++)
	{
		printf("\n Enter the arrival Time and released time[%d]\n",i+1);
		printf("Arrival time :\t");
		scanf("%d", &a[i]);
		
		printf("Relesed time :\t");
		scanf("%d", &b[i]);
		temp[i]=b[i];
	}
		printf("Enter the time quantum for the process : \t");
		scanf("%d",&qunt);
		printf("\n Car NO \t\t Arrival Time \t\t TAT \t\t waiting time ");
		for(sum=0,i=0;x!=0; )
		{
			if(temp[i]<=qunt && temp[i]>0)
			{
				sum= sum +temp[i];
				temp[i]=0;
				count=1;			
			}
				else if(temp[i]>0)
				{
					temp[i]=temp[i]- qunt;
					sum=sum+qunt;
				}
				if(temp[i]==0 && count==1)
				{
					x--;
					printf("\n Process NO [%d] \t\t %d\t\t\t %d\t\t\t%d",i+1,b[i],sum-a[i],sum-a[i],b[i]);
					s=s+sum-a[i]-b[t];
					t=t+sum-a[i];
					count=0;
				}
				if(i==n-1)
				{
					i=0;
				}
				else if(a[i+1]<=sum)
				{
					i++;
				}
				else
				{
					i=0;
				}
				
				
		}
		
		avg_wt = s * 1.0/n;
		avg_tat = t * 1.0/n;
		printf("\n Avg Turn Around Time: \t%f",avg_wt);
		printf("\n Avg Waiting Time: \t%f ",avg_tat);
		getch();
	//	printf("\n Car No \t\t %d\t\t\t %d\t\t\t %d", i+1,b[i],);
	}
	
	
