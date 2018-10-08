/*Christie Carranza*/

#include <stdio.h>

int majornum(int arr[], int n)
{
int index=0, value=1;
int i;
for (i=1; i<n; i++)
{
if (arr[index]==arr[i])
value++;
else value--;
if(value==0)
{
index=i;
value=1;
}}
return arr[index];
}

int checkmajor(int arr[], int n, int number)
{int i, c=0;
for(i=0; i<n; i++)
if (arr[i]==number)
c++;
if (c>n/2)
return 1;
else return 0;
}

void getmajor(int arr[], int n)
{
int major=majornum(arr, n);
if (checkmajor(arr, n, major))
printf("Majority = %d\n", major);
else
printf("No Majority\n");
}
int main()
{
int arr[7], i;
printf("Enter 7 elements of array:\n");
for (i=0; i<7; ++i)
scanf("%d", &arr[i]);
getmajor(arr, 7);
return 0;
}
