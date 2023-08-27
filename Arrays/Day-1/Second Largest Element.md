# Second Largest Element

[Code Studio](https://parikh.club/parikh_arrays_1)

~~~

#include <bits/stdc++.h> 
int findSecondLargest(int n, vector<int> &arr)
{
    int cur_max=arr[0];
    int prev_max=INT_MIN;
    for(int i=1; i<n; i++){
        if(arr[i]>prev_max && arr[i]<cur_max){
            prev_max=arr[i];
        }else if(arr[i]>cur_max){
            prev_max=cur_max;
            cur_max=arr[i];
        }else{
            continue;
        }
    }
    return prev_max==INT_MIN?-1:prev_max;
}

~~~
