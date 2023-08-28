---
title: "make_heap() function in C++ STL"
datePublished: Fri May 15 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluxafcl000h09mghkt7akw3
slug: makeheap-function-in-c-stl
tags: cpp

---

Hello learners, today in this tutorial we will learn about the **make\_heap()** method of the STL library in C++. It is used to create a heap from an array or a sequence. A heap is a data structure that is used to point to the max or min element of an array or list and to make the access of that element in an O(1) time. Let’s understand this in more detail using easy and comprehensible examples.

 make\_heap() is used to create max-heap or min-heap from a sequence. It is defined in the algorithm header file in two ways as defined below:

1. make\_heap( IteratorFirst, IteratorLast )
    
    ```cpp
    template<class RandomAccessIterator>
    void make_heap(RandomAccessIterator first, RandomAccessIterator last);
    ```
    
2. make\_heap( IteratorFirst, IteratorLast, Comp )
    
    ```cpp
    template<class RandomAccessIterator, class Compare>
    void make_heap(RandomAccessIterator first, RandomAccessIterator last,Compare comp);
    ```
    

In the above syntax following terms are defined below:

**(First, Last):** First points to the beginning element of an array or sequence which is transformed into a heap. The range **\[first, last)**, is used to transform an array or sequence into a heap. Last Points to the next address to the last element of sequence  
it should be converted into a heap.

**Comp:** The comparison function is used to return the boolean value of each object compared. This can be a function pointer or a functional object (greater&lt;int&gt; ()), and it will not change values.

Let’s take the two examples to make things more clear, by using the first syntax we create the max-heap, and by using second we will create the min-heap and in the second example we are using,  greater&lt;int&gt;() (functional object) as a comparator.

Here is the code:

1. **Max Heap**
    

```cpp
#include<iostream>
#include<algorithm>
#include<vector>
using namespace std;

int main(){
    
    vector<int> myVector = {10, 30, 55, 120, 50 };
    
   // To create Heap (max heap).
   
    make_heap(myVector.begin(), myVector.end());
    
    std::cout << "Initially, the max element of heap is : "<< myVector.front() << std::endl;
    
    // After pop() the max element
    
    pop_heap(myVector.begin(), myVector.end());
    myVector.pop_back();
    
    std::cout << "Now, the max element of heap is : "<< myVector.front() << std::endl;
 
    return 0;
}
```

```cpp
Output:
Initially, the max element of heap is : 120
Now, the max element of heap is : 55
```

1. **Min Heap**
    
    ```cpp
    #include<iostream>
    #include<algorithm>
    #include<vector>
    using namespace std;
    
    int main(){
        
        vector<int> myVector = {20, 80, 5, 12, 500 };
        
       // To create Heap (min heap).
       
        make_heap(myVector.begin(), myVector.end(), greater<int>());
        
        std::cout << "Initially,the min element of heap is : "<< myVector.front() << std::endl;
        
        // After pop() the min element
        
        pop_heap(myVector.begin(), myVector.end(), greater<int>());
        myVector.pop_back();
        
        std::cout << "Now, the min element of heap is : "<< myVector.front() << std::endl;
        
        return 0;
    }
    ```
    
    ```cpp
    Output:
    Initially, the min element of heap is : 5
    Now, the min element of heap is : 12
    ```
    
    Hope this article was helpful to you. Keep Coding Keep Learning.