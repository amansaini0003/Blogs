---
title: "Rearrange an array such that ‘arr[j]’ becomes ‘i’ if ‘arr[i]’ is ‘j’ using C++"
datePublished: Sat May 02 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluvem2o000d09mic2aqhqw6
slug: rearrange-an-array-such-that-arrj-becomes-i-if-arri-is-j-using-cpp
tags: cpp

---

Hello learners, today in this tutorial we will learn how to rearrange an array such that ‘arr\[j\]’ becomes ‘i’ if ‘arr\[i\]’ is ‘j’ in C++ using an easy and comprehensible example. Let’s start with an example it will be more clear.

Let’s say we have an array of size N which contains distinct elements between  0  to  ( N – 1). Our job is to rearrange the array elements so that array\[i\] = j is changed to arr\[j\] = i. Here is an example

 Input: arr\[ i \] = { 4, 1, 0, 2, 3, 6, 5 }. //  ‘ i ‘ will iterate from 0 – (n-1).  
Output: arr\[\] = { 2, 1, 3, 4, 0, 6, 5 }  
Explanation:

arr\[0\] = 4                                                              arr\[4\] = 0  
arr\[1\] = 1                                                               arr\[1\] = 1  
arr\[2\] = 0        After  rearranging               arr\[0\] = 2  
arr\[3\] = 2         =&gt;=&gt;=&gt;=&gt;=&gt;=&gt;                     arr\[2\] = 3  
arr\[4\] = 3                                                              arr\[3\] = 4  
arr\[5\] = 6                                                              arr\[6\] = 5  
arr\[6\] = 5                                                              arr\[5\] = 6

Firstly store all the elements of arr\[\] in another array using the code ”  j \[ arr \[ i \] \] = i ”. Now print all the elements of the array.

Here is the code:

```plaintext
#include<bits/stdc++.h>
#include<string>
#include<algorithm>

using namespace std;

        void rearrange(int arr[], int n )
        {
            int j[n];
            
            // store value of j
            
            for (int i = 0; i < n; i++) 
            {
                j[arr[i]] = i;
            }
            
            for(int i=0;i<n;i++)
            {
                arr[i] = j[i];
            }
            
            std::cout <<"\n"<< "After Rearrangement : { ";
            for (int i = 0; i < n; i++) {
                std::cout << arr[i] << ", ";
            }
              cout<<"}";
        }
        
        int main()
        {
            
           int arr[] = { 4, 1, 0, 2, 3, 6, 5 }; 
           // number of elements in arr[].
            int n = sizeof(arr) / sizeof(arr[0]); 
            
            std::cout << "Initially Array : { ";
            for (int i = 0; i < n; i++) {
                std::cout << arr[i] <<", ";
            }
            cout<<"}";
            rearrange( arr, n);
            
            return 0;     
        }
```

```plaintext
Output:
Initially Array : { 4, 1, 0, 2, 3, 6, 5, }
After Rearrangement : { 2, 1, 3, 4, 0, 6, 5, }
```

Hope this article was helpful to you. Keep Coding Keep Learning.