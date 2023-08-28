---
title: "std::greater in C++ with examples"
datePublished: Fri May 08 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluvkj7d000o08kz7l06aqsg
slug: stdgreater-in-cpp-with-examples
tags: cpp

---

Hello learners, today in this tutorial we will learn about **std:: greater** method of STL library in C++. **std:: greater** is a functional object. It is used for changing the functionality of the given function. Let’s understand this in more detail using easy and comprehensible examples.

**std:: greater** is used for performing a comparison between the two arguments passed. It is also defined as the functional object class for greater( &gt; ) or equal-to( = ) inequality comparison. ( &gt;=).

It is defined in the functional header file as:

```cpp
template<class T > struct greater{
    bool operator() (const T& a, T& b) const{ return  a > b ; }
    typedef  T  first_argument_type;
    typedef  T  second_argument_type;
    typedef bool result_type;
};
```

In this, the member function is a bool operator() (const T& a, const T& b) Member function compares the two arguments based on which it returns the result.

std::greater is used in many standard algorithms. Let’s see one of them.

**Example 1**: Sorting using std:: greater.

Here is the Code:

```cpp
#include<bits/stdc++.h>
#include<functional>
using namespace std;

int main()
{
    int arr[] = { 44, 1, 76, 20, 86, 19, 5 };

    int size = sizeof(arr)/sizeof(arr[0]);

    std::cout << "Input Array: "<< "{ 44 1 76 20 86 19 5}" << std::endl;

    // Sort array in descending order
    // using greater functional object

    sort(arr, arr + size, greater<int>());

     std::cout << "Output Array: {" ;

    // for range-based loop

    for (int i : arr){
        std::cout << i << " ";
    }

    std::cout << "}" << std::endl;
    return 0;
}
```

```cpp
Output:
Input Array: { 44 1 76 20 86 19 5}
Output Array: {86 76 44 20 19 5 1 }
```

**Example 2**: Creating a Min\_Heap using priority\_queue.

Explanation: Generally priority\_queue is used for creating Max\_Heap but by using the greater &lt;int&gt;() function we can create Min\_Heap.

Here is the Code:

```cpp
#include<bits/stdc++.h>
using namespace std;

int main()
{
    // Create Min_Heap
    
    priority_queue<int, vector<int>, greater<int>> p_queue;

    p_queue.push(10);
    p_queue.push(5);
    p_queue.push(87);
    p_queue.push(22);
    p_queue.push(1);
    p_queue.push(43);
    p_queue.push(101);


    std::cout << "Priority Queue is : " ;

    while( !p_queue.empty() )
    {
        std::cout << p_queue.top() << " ";

        // remove top element
        // so that top points to next element
        p_queue.pop();
    }

    return 0;
}
```

```cpp
Output:
Priority Queue is : 1  5  10  22  43  87  101
```

Hope this article was helpful to you. Keep Coding Keep Learning.