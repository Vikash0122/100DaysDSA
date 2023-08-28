# Non decreasing array

[Code Studio](https://parikh.club/parikh_arrays_3)

~~~
/*
consider three cases:

[1,6,3,4] Here, when i is at 2 arr[2]<arr[1], so violation, 
so we check if arr[i-2]≤arr[I] if yes we replace 6(i=1) with 3(i=2) 

[4,7,3,10] Here, violation occurs at i=2, here arr[i-2]>arr[i] so, 
we cant do arr[i-1]=arr[i], instead we can do arr[i]=arr[i-1]. 

[2,1,3,4] here at i=2, there is violation, here i-2 doesn't exist, 
so in case of i=1, we can simply do arr[i-1]=arr[i]

*/
#include <bits/stdc++.h> 
bool isPossible(int *arr, int n)
{
    int ans=0,pre=INT_MIN,curr=arr[0];
    for(int i=0;i<n-1;i++)
    {
        if(arr[i+1]>=curr)
        {
            pre=curr;curr=arr[i+1];
        }
        else{
            ans++;
            if(arr[i+1]>=pre){
                curr=arr[i+1];
            }
        }
        if(ans>1)
            return false;
    }
    return true;
}
~~~
