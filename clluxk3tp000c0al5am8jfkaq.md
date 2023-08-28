---
title: "Index of smallest element in vector in C++"
datePublished: Wed May 20 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluxk3tp000c0al5am8jfkaq
slug: index-of-smallest-element-in-vector-in-cpp
tags: cpp

---

Hello learners, today in this tutorial we will learn about the **std::min\_element** method of the STL library in C++. It is practised for finding the least element in a vector, an array, or in the list. std::min\_element returns an iterator pointing to the lowest element in the list. Let’s understand this in more detail using easy and comprehensible examples.

**std::min\_element** is used for finding the least element in a given range \[ first, last). By comparing the objects “&gt;”. In the event more than one item is filled with the smallest condition, the iterator returned points to the first of such elements and If the list is empty, it points to the last.

It is defined in the algorithm header file as:

```cpp
ForwardIterator min_element (ForwardIterator first, ForwardIterator last)
```

```cpp
first: It is a forward iterator that points to the beginning of the range of list.
```

```cpp
last: It is a forward iterator that points to the end of the range of list.
```

```cpp
return value: Returns a pointer pointing to the least value of element.
```

Using min\_element we will find the index of minimum element. Let’s see with an example.

Here is the code:

Example 1: Finding the index of the smallest element is the complete range.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){

    vector<int> myarr = {10, 50, 76, 22, 23, 9, 100, 55, 50};

   // We can also use "auto" instead of  vector<int>::iterator.

    vector<int>::iterator it = min_element(myarr.begin(), myarr.end());

    int minElementIndex = it - myarr.begin();

    cout << "Minimum ELement = " << *it << "\n";

    // add 1 in minElementIndex because vector start from index '0'.

    cout << "Index of Minimum ELement = " << minElementIndex + 1 << std::endl;

    return 0;
}
```

```cpp
Output:
Minimum ELement = 9
Index of Minimum ELement = 6
```

Example 2: Finding the index of the smallest element in a specific range.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main(){

    vector<int> myarr = {10, 50, 6, 22, 23, 9, 1, 5, 50};

   // Minimum ELement in a specific range of elements

    vector<int>::iterator it = min_element(myarr.begin()+2, myarr.end()-3);

    int minElementIndex = it - myarr.begin();

    cout << "Minimum ELement = " << *it << "\n";

    // add 1 in minElementIndex because vector start from index '0'.

    cout << "Index of Minimum ELement = " << minElementIndex + 1 << std::endl;

    return 0;

}
```

```cpp
Output:
Minimum ELement = 6
Index of Minimum ELement = 3
```

Hope this article was helpful to you. Keep Coding Keep Learning.