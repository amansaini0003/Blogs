---
title: "Iterator to last element in std::list in C++"
datePublished: Sun Dec 13 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cllw8a1q6000i09mn1ema2uj6
slug: iterator-to-last-element-in-stdlist-in-c
tags: cpp

---

Hello learners, today in this tutorial we will learn about the **list::end()**. It is a predefined function in a C++ Standard Template Library(STL). It will return an iterator that is pertaining to the past-the-end item. Let’s understand this in more detail using an easy and comprehensible example.

Our task is to iterate until the last element in the list. It can be done in several ways but will be done using the list::end() function.

**Syntax:** 

```cpp
list_Name.end()
```

**Parameters:**

```cpp
 None
```

**Return Value:**

```cpp
 It returns an iterator which is referring to the past-the-end-element in the list container.
```

**Past the last element:** It’s a logical feature that will follow the last item in the list container. It will not point to any element i.e. why we can’t dereference it.

This function is usually used with a **list::begin()** to identify the range of the list.

Here is the code :

```cpp
#include <iostream>
#include <list>
using namespace std;

int main(){
    
    list<int> l;
    
    l.push_back(43);
    l.push_back(3);
    l.push_back(15);
    l.push_back(22);
    l.push_back(51);
    l.push_back(101);

    list<int>::iterator it1 = l.end();

    // referring to the past-the-end element in the list container
    // i.e why it can't be dereferenced

    // std::cout << *it1 << std::endl;
 
    std::cout << "Iterates till the last element in the list :" << std::endl;
    
    // "auto" can be used instead of "list<int>::const_iterator".
        
    for (list<int>::const_iterator i = l.begin(); i != l.end(); ++i) {
        std::cout << *i << " ";     
    }
    return 0;   
}
```

```cpp
Output:
Iterates till the last element in the list : 43 3 15 22 51 101
```

  
Hope this article was helpful to you. Keep Coding Keep Learning.