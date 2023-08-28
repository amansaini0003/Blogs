---
title: "Search an element in a Linked List (Iterative ) in C++"
datePublished: Tue May 12 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: clluvuo5x000509kz1xqx1a0w
slug: search-an-element-in-a-linked-list-iterative-in-cpp
tags: cpp

---

Hello learners, today in this tutorial we will learn how to search an element in a Singly Linked List iteratively in C++ using an easy and comprehensible example. Initially, we have to create a singly linked list and then using the search function we have to find whether the given element is present in the list or not.

Firstly we have to make a class Node which contains the data and link part of the node and another class name solution which contains three functions append\_node(), display(), and search(). Let’s see the approach for further simplification.

**Approach:**

1. Create two classes one for the node and the second class containing all the functions.
    
2.  append\_node() -&gt; To crate the linked list, Search() -&gt; To search the element, display() -&gt; To display the linked list.
    
3. In bool Search(int find), Initialize the \*CurrentNode = root.
    
4. Do the following steps in a while (CurrentNode != NULL).
    
5. If CurrentNode -&gt; data == find, return True.
    
6. Else CurrentNode = Current -&gt; link.
    
7. Outside the while loop, return false.
    

Firstly try it by yourself before seeing the solution.

Here is the Code:

```cpp
#include<iostream>
using namespace std;

class Node{
    public:
    int data;
    Node *link;
        Node(int d){
            data = d;
            link =  NULL;
        }
};
class Solution{
    public:

    void appendNode(int d);
    bool searchElement(int find);
    void display();

};

Node *root = NULL;  // Root or Head

void Solution::appendNode(int data){

    Node *temp;
    temp = new Node(data);

    if(root == NULL)
    root = temp;

    else{
        Node *p = root;
        while(p->link != NULL)
        p = p->link;

        p->link = temp;
    }
     
}
bool Solution::searchElement(int find){
    Node *current = root;
    
    while (current != NULL)  
    {  
        if (current->data == find)  
            return true;  
        current = current->link;  
    }  
    return false;
}
void Solution::display(){
    
    Node *current = root;
    
    while(current->link != NULL)
    {
        std::cout << current->data << " >> "  ;
    
        current = current->link;
    }
    
    cout << current->data << "\n";
}
    

int main()
  {
        Solution myList;
        int find = 30;
        
        // Creation of Linked List

        myList.appendNode(10);
        myList.appendNode(20);
        myList.appendNode(30);
        myList.appendNode(40);
        myList.appendNode(50);
        
        myList.display();
        
        std::cout << "Is the element "<< find << " is in the list" << std::endl;
        
        myList.searchElement(find)? cout<<"YES" : cout<<"NO"; 

    return 0;

  }
```

```cpp
Output:
10 >> 20 >> 30 >> 40 >> 50
Is the element 30 is in the list
YES
```

Hope this article was helpful to you. Keep Coding Keep Learning.