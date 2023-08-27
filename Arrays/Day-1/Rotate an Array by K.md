# Rotate an array by k

// Left Rotation
[Code Studio](https://parikh.club/parikh_arrays_2)
~~~
#include <bits/stdc++.h>
using namespace std;
vector<int> rotateArray(vector<int>arr, int d) {
    reverse(arr.begin(),arr.begin()+d);
    reverse(arr.begin()+d,arr.end());
    reverse(arr.begin(),arr.end());

    return arr;
}
~~~

// Right Rotation
[Leetcode](https://leetcode.com/problems/rotate-array/description/)
~~~
   void rotate(vector<int>& nums, int k) {
    int n = nums.size();
    k = k%n;
    k = nums.size()-k;
    if(nums.size()<=1)
    return;
    reverse(nums.begin(),nums.begin()+k);

    reverse(nums.begin()+k,nums.end());

    reverse(nums.begin(),nums.end());
}
~~~
