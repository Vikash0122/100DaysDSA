# First Missing Positive

[CodeStudio](https://parikh.club/parikh_arrays_5)

~~~
#include <bits/stdc++.h> 
using namespace std;
int firstMissing(int arr[], int n)
{
    int maxi=0;
    unordered_map<int,int> mp;
     for (int i = 0; i < n; i++) {
        if (arr[i] > 0) {
            maxi = max(maxi, arr[i]);
            mp[arr[i]]++;
        }
    }

    for (int i = 1; i <= maxi + 1; i++) {
        if (mp.find(i) == mp.end()) {
            return i;
        }
    }

    return -1; // This line should not be reached
}
~~~

~~~
int firstMissingPositive(vector<int>& nums) {
       int n=nums.size();
        for(int i=0; i<n; i++){
            int element = nums[i];

            if(element>=1 && element <=n){
                int chair = element-1;
                if(nums[chair]!=element){
                    swap(nums[chair],nums[i]);
                    i--;
                }
            }
        }
        for(int i=0; i<n; i++){
            if(i+1!=nums[i]){
                return i+1;
            }
        }
        return n+1;
}
~~~
