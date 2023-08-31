# Equilibrium Index

(CodeStudio)[https://parikh.club/parikh_arrays_4]
~~~
#include <bits/stdc++.h> 
int findEquilibriumIndex(vector<int> &arr) {
   int sum=0;

   for(int i=0;i<arr.size();i++)
   {
       sum+=arr[i];
   }
   int l=0;

   for(int i=0;i<arr.size();i++)
   {
       sum-=arr[i];

       if(l==sum) return i;

       l+=arr[i];
   }
   return -1;
}

~~~
