---
title: "Collect all coins in minimum number of steps in C++"
datePublished: Sat May 02 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluujm2v000909l05ifa8ed4
slug: collect-all-coins-in-minimum-number-of-steps-in-c
tags: cpp

---

Hello learners, today in this tutorial we will learn how to collect all coins in the minimum number of steps in C++ using an easy and comprehensible example. Let’s say we have a stack of coins that are placed simultaneously and our job is to collect all coins in a minimum number of steps. But there is a rule to collect coins. In a single step, we can collect either one horizontal line of coins continuously or either one vertical line of coins continuously.

First of all, take an array in which each index of an array represents the height of a stack of coins.  
Example:  array =  {  3,  2,  7,  2,   3  }.  
As in the above array, the first stack has 3 coins, the second stack has 2 coins, similarly, the third stack has 7 coins, and so on.  
Output: 5

  
**Approach:** To solve the given problem we are using the Divide and Conquer technique. To minimize the number of steps firstly we have to remove all the horizontal lines. Now we have to work on the array from left index to right index.

1. Using recursion in each step we have to find the index of the stack having a minimum height to remove that many horizontal lines.
    
2. After that stack is divided into two parts left to mini & mini + 1 to right. Using recursion we will call those subarrays.
    
3. We also collect coins vertically continuously. So to find minimum steps choose minimum from :
    

* Vertically collected coins ( right-left )
    
* Lower Horizontally collected coins recursively
    
* Recursively collected coins on the left and right segments.
    

**Time Complexity:** O( N^2)

Here is the code:

```cpp
#include<bits/stdc++.h>
#include<string>
#include<algorithm>
using namespace std;

int recursive(int arr[], int left, int right, int height) {
        // base condition 
        if (left >= right) 
        return 0; 

            // to find the index of minimum height of stack of coin 
        int mini = left; 
        for (int i = left; i < right; i++) 
            if (arr[i] < arr[mini]) 
                mini = i; 

            // minimum of all recursive calls.
                return min( right - left, 
                recursive(arr, left, mini, arr[mini]) +        
                recursive(arr, mini + 1, right, arr[mini]) + 
                arr[mini] - height); 
} 
 
int Minimum_Steps(int arr[], int n) {        
    return recursive(arr, 0, n, 0); 
} 

int main(){            
    int arr[] = { 3, 2, 7, 2, 3 }; 
    
    // number of elements in arr[].
    int n = sizeof(arr) / sizeof(arr[0]);   
    cout <<" Minimum Steps are : "<< Minimum_Steps(arr, n) << "\n"; 
    return 0;     
}
```

```plaintext
Output:
Minimum Steps are : 5
```

  
Hope this article was helpful to you. Keep Coding Keep Learning.