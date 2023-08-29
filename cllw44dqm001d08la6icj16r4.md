---
title: "Find k maximum sum combinations from two arrays in C++"
datePublished: Tue Jun 02 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cllw44dqm001d08la6icj16r4
slug: find-k-maximum-sum-combinations-from-two-arrays-in-cpp
tags: cpp

---

Hello learners, today in this tutorial we will learn how to find ‘**k**‘ maximum sum combinations from two arrays in C++ using some easy and comprehensible examples. Let’s say we have two arrays arr\_1 and arr\_2 containing the m & n elements respectively and we have to find the ‘k’ max. sum combinations by adding the elements from arr\_1 and arr\_2. Let’s discuss this in more detail. 

## **k maximum sum combinations from two arrays  
**

Suppose we have two arrays arr\_1 & arr\_2 as shown:

```cpp
arr_1 = {1, 2, 5}
arr_2 = {4, 1, 6}
k = 3
```

So, we have to find **3** max. sum combinations from arr\_1 & arr\_2. Here is the max. combinations:

```cpp
6 + 5 = 11 
4 + 5 = 9
6 + 2 = 8
```

**Approach:**

1. Create a max heap using priority\_queue and push all the combinations of elements of the arr\_1 & arr\_2.
    
2. Now pop the top elements from priority\_queue and print on the screen.
    
3. Create count = 0. Repeat step 2 while(count &lt; k).
    
4. After every pop increase the counter variable.
    

Here is the code:

```cpp
#include<iostream>
#include<queue>
using namespace std;

    int main()
    {

        int arr1[] = {10, 20, 30, 40, 50};
        int arr2[] = {5, 4, 3, 22, 11};
        
        // int arr1[] = {1,2,5};
        // int arr2[] = {4,1,6};

        int n = sizeof(arr1)/sizeof(arr1[0]);

        // 'K' maximum sum combination
        // from two arrays

        const int k = 3;

        // Create Max Heap using priority_queue

        priority_queue<int> p_queue;

        for(int i=0; i<n ; i++)
        {
          for(int j=0; j<n ; j++)
          p_queue.push(arr1[i] + arr2[j]);

        }

        int count = 0;

        cout << k << " max sum combinations are:\n";

        while( count < k)
        {
          cout << p_queue.top() << "\n";
          p_queue.pop();

          count++;
        }

        return 0;
    }
```

```cpp
Output:
3 max sum combinations are:
72                                       
62                                     
61
```

I hope this article was helpful to you. Keep Coding Keep Learning.