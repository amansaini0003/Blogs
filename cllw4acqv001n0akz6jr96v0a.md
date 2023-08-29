---
title: "Move semantics in C++"
datePublished: Mon Jun 08 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cllw4acqv001n0akz6jr96v0a
slug: move-semantics-in-c
tags: cpp

---

Hello Learners, Today in this tutorial we will learn about Move Semantics in C++ with some easy and comprehensible examples. New versions of C++ provide move semantics which makes it possible to eliminate unnecessary memory copies. With the help of move semantics, the memory will be optimized. Let’s discuss this in more detail.

## **Move semantics**

When we are copying a value are using double resources but if we simply move one resource to another place then it is less usage of memory and more optimized.  
In earlier versions of C++, copies were unavoidable in many situations. A move operation transfers ownership of a resource from one object to the other without making a copy. Let’s take a simple example of swapping two variables to understand move semantics in a better way.

```cpp
void swap(int &x, int &y)
{
      int temp = a;
      a = b;
      b = temp;
}
```

Here we are creating another resource to copy a value which will create more memory. But if move then it is less usage of memory and more optimized. Copying the value keeps two references of the same entity. But by using move semantics we are not copying things we are moving.

Here is a more optimized code for swapping two variables:

```cpp
#include<iostream>
using namespace std;

void swap(int &x, int &y){
    
 // here x is moved to temp now a is empty 
    int temp = move(x); 
    x = move(y);
    y = move(temp); 
}

int main(){
    
    int x = 10, y = 20;
    
    swap(x,y);
    
    std::cout << "X : " << x << "\nY : " << y<< std::endl;
}
```

```cpp
Output:
X : 20
Y : 10
```

Now definitely here we are creating one more variable temp but this variable is better as compared to the previous version because we are not copying the value keeps two references of the same entity.

But, In the case of the move, we are moving that we are not reserving twice the memory.

Example2: Print a string

```cpp
#include<iostream>
#include<string>
using namespace std;

string print(){
    return "Hello World";
}

int main(){
    
    // case 1
    string s1 = print();

    // case 2
    string&& s2 = print(); 
        
    std::cout << s2 << std::endl;
    return 0;
}
```

```cpp
Output:
Hello World 
```

In Case 1, we are copying the reference of print inside the ‘s1’ but in Case 2, we are not copying but directly referencing the value. Also in Case 1, we are copying but in Case 2, semantic type we are moving in which memory will be optimized.

I hope this article was helpful to you. Keep Coding Keep Learning.