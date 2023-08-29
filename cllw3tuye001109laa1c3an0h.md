---
title: "C++ program to find Height of a complete binary tree (or Heap) with N nodes"
datePublished: Sun May 24 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cllw3tuye001109laa1c3an0h
slug: c-program-to-find-height-of-a-complete-binary-tree-or-heap-with-n-nodes
tags: cpp

---

Hello learners, today in this tutorial we will learn how to find the height of a complete binary tree with N nodes in C++ using some easy and comprehensible examples. A binary tree is mainly of 5 types, Perfect Binary Tree, Full Binary Tree, Balanced Binary Tree, Complete Binary Tree, and A degenerate Tree. Let’s discuss this in additional detail.

 **Complete Binary Tree (Binary Heap):** A complete binary tree is a binary tree in which every level is filled, except possibly the last one, and all nodes are as left as possible.

Now we have N nodes in a tree and we have to find the height of a tree. Firstly try to find out a pattern by yourself then see the code. So, I hope you have tried and found the pattern and if not so let’s dive into the code to make it more clear.

**Height of Complete Binary tree :** \[ ceil(log2(nodes + 1)) – 1 \].

```cpp
#include<iostream>
#include<math.h>
using namespace std;

        int main(){

                unsigned int nodes, height;
                cout << "Enter the number of nodes in a complete binary tree : ";

                cin >> nodes;
                
                if(nodes == 0)
                height = 0;
                
                else
                height = ceil(log2(nodes + 1)) - 1;

                cout << "Height of the Binary Tree is : " << height << " \n ";

                return 0;
        }
```

```cpp
Output:
Enter the number of nodes in a complete binary tree: 10
Height of the Binary Tree is : 3
```

I hope this article was helpful to you. Keep Coding Keep Learning.