# Sum-of-pairs

/**

We call an array of integers X of size N good if it can be partitioned into 2 arrays of size n/2, say p1[ ] and p2[ ], such that p1[0] + p2[0] = p1[1] + p2[1] = p1[2] + p2[2] = ... . Given an array Y, determine the size of its largest subset which is a good array.
Input

The first line contains the integer N ( 100). The next line contains N space separated integers, which are the elements of the array X.
Output

One number which is the size of the greatest subset as mentioned in the problem statement.
Logic Test Case 1

Input (stdin)
6

1 4 2 3 8 10

Expected Output

4
Logic Test Case 2

Input (stdin)
6

1 4 2 3 8 10

Expected Output

4
*/




#include<stdio.h>
int main()
{
int input,i,j,count=0,k=0,max,l,count1=0;
scanf("%d",&input);
if(input>=4){
int a[input],b[input][input];
//int check(int input,int b[input][input],int c,int d,int g);
for(i=0;i<input;i++)
scanf("%d",&a[i]);
for(i=0;i<input;i++){
for(j=i+1;j<input;j++)
{b[i][j]=a[i]+a[j];
//printf("%d\t",b[i][j]);
count++;}
//printf("\n");
}
int c[2*count],d[2*count];
k=0;
for(i=0;i<input;i++)
for(j=i+1;j<input;j++){
c[k]=b[i][j];
//printf("%d\t",c[k]);
k++;}
//printf("%d\t",c[i]);
//}
//printf("\n");
k=0;l=0;count1=0;
while(l<count){
//printf("%d\t",c[l]);
if(c[l]!=0){
d[k]=c[l];
for(i=l;i<count;i++){
if(d[k]==c[i]){
c[i]=0;
count1++;}}}
d[k+1]=count1;
//printf("%d\t",d[k+1]);
count1=0;
k+=2;
l++;}
//printf("\n");
max=d[1];
for(i=3;i<(2*count);i+=2)
{
if(max<d[i])
max=d[i];}
printf("%d\n",2*max);}
return 0;
}
/*int check(int input,int b[input][input],int c,int d,int g)
{
int count=0,i,j;
for(i=d;i<input;i++)
for(j=g;j<input;j++)
{
if(c==b[i][j])
count++;
}
return count;}*/
