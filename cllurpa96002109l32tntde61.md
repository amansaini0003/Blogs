---
title: "Tokens, Expressions and Control Structures in C++"
datePublished: Wed Apr 29 2020 06:30:00 GMT+0000 (Coordinated Universal Time)
cuid: cllurpa96002109l32tntde61
slug: tokens-expressions-and-control-structures-in-c
tags: cpp

---

Hello Learners, Today in this tutorial we will learn about the Tokens, Expressions, and Control Structures in C++ with some easy and comprehensible examples. Any C++ program is written using the help of tokens, expressions, and control structures or control statements.  
  
**Tokens:** The smallest individual elements of a program are known as **tokens**. In C and C++ most of the tokens are the same. In C++ we have the following tokens.

* Keywords
    
* Identifiers
    
* Constants
    
* Strings
    
* Operators
    

1. **Keywords**: There are some keywords declared in C++ which are explicitly reserved identifiers and can’t be used as variable names in the program.
    
2. **Identifiers**: It sequence of characters that refer to the name of an array, classes, variables, a function, etc.
    
    ```plaintext
    Example: int arr[5], here arr is the identifier for an array.
    ```
    
3. **Constants**: A fixed value that does not change when the program is executed.
    
    ```plaintext
    Example: 90(Integer constant), 2.2(Floating point constant), "C++"(String Constant), 'a'(Character Constant)
    ```
    
4. **Strings:** A sequence of characters is known as strings.
    
    ```plaintext
    Example: "India is beautiful country"
    ```
    
5. **Operators:** Operators are used for performing various operations on variables and constants. All C operators are also applicable in C++.
    
    ```plaintext
    Examples: Arithmetic operators('+' , '-', '*' , '/') , extraction operator(" >>"), insertion operator("<< ") etc.
    ```
    

```cpp
#include <iostream>
#include<string>

using namespace std;

int main() {
    string s1="hello world" ;
    // s1 is an "identifier" of "string" data type.
    cout<<s1;
    // ' << ' is the insertion " operator "
    
    const int a =100;
    // Here 'a' is an " identifier "
    // 'for' , 'namespace' & 'const' are " keyword "
    //which can't be used as a variable name
    
    for(int i=0 ;i<3;i++ ) {
     cout << a+i << endl; // '+' is an "operator"
    }
    return 0;
}
```

Output:

```plaintext
hello world                                                                                    
100                                                                                            
101                                                                                            
102
```

**Expressions:** A combination of variables, constants, and operators arranged as per rules is called an expression. They are of seven types:

* **Constant Expression:** It consists of only constant values.
    
    ```plaintext
    Example: 10 , 10+20*20 , 100/20*2+221-383 etc.
    ```
    
* **Integral Expression:** Integral expressions are those which, after all, conversions, produce integral results.
    
    ```plaintext
    Example: x,  x *y*z , 10+int(2.0) . // Here x,y,z are integers
    ```
    
* **Float Expression:** Floating expressions are those that produce floating-point results after implementing all the automatic and explicit type conversions.
    
    ```plaintext
    Example: x+y, 5 +float(10),  22/7.0    // Here x,y are of float type.
    ```
    
* **Pointer Expression:** Pointer expression are those which gives the address value.
    
    ```plaintext
    Example: &m, *ptr,*ptr+1
    ```
    
* **Relational Expression:** Relation expression are those that compare the two expressions and gives the bool-type result.
    
    ```plaintext
    Example: a>b, a==b, a+b>100
    ```
    
* **Logical Expression:** When two or more relational expressions are combined and give the bool type result means either 0 or 1.
    
    ```plaintext
    Example: (a<b  &&  x==10) , (x==100 || b==2)
    ```
    
* **Bitwise Expression:** An expression that is used to manipulate data at a bit level. This expression is used for shifting or testing of bits.
    
    ```plaintext
    Example: a >> 5   // Shift  5  bit position to right
    
    a << 2   // Shift  2  bit position to left
    ```
    

**Control Structures:** Several statements by which we can control the flow of execution or behaviour of a program. C++ has three kinds of control structures.

* **Sequence Structure**: When a set of program statements is executed sequentially then it is a sequence structure.
    
* **Selection Structure:** A set of program statements executed based on whether a boolean condition is true or false.
    
* **Loop Structure:** A set of program statements executed until the loop condition is met.
    

Here is an example of Sequence Structure

```cpp
#include <iostream>

using namespace std;
    
int main() {
    int a=10;   
    int b=20;   
    int total;
     std::cout << "Statements are executed sequentially in sequence structure" << std::endl;   
     total=a+b;  
     std::cout << total << std::endl;
     return 0;
}
```

```plaintext
Output:
Statements are executed sequentially in sequence structure
30
```

Here are the examples of Selection Structure

```cpp
#include <iostream>

using namespace std;

int main() {

    int a=1000, b=100;
    if(a<b){
      std::cout << "a is less than b" << std::endl;
    } else if(a>b) {
     std::cout << "a is greater than b" << std::endl;
    } else {
     std::cout << "a is equal to b" << std::endl;
    }
    return 0;
}
```

```plaintext
Output:
a is greater than b
```

```cpp
#include <iostream>
using namespace std;

int main() {
    int a=1000 , b=100 ,c=10,d;
     cout<<"Press 1 to print value of a \n Press 2 to print value of b \n Press 3 to print value of c \n ";
     cin>>d; // input from user
    
    switch(d) {
    case 1: std::cout << a << std::endl;
            break;
    case 2: std::cout << b << std::endl;
            break;
    case 3: std::cout << c << std::endl;
            break;
    default: std::cout << "You have entered wrong no." << std::endl;
    }
    return 0;
}
```

Output:

```plaintext
Press 1 to print value of a                                                                    
Press 2 to print value of b                                                                   
Press 3 to print value of c                                                                   
2                                                                                             
100
```

Here is an example of a Loop Structure  

```cpp
#include <iostream>
using namespace std;
int main()
{
        std::cout << "In for loop" << std::endl;
        for(int i=1;i<=5;i++)
        {
            std::cout << "i=" << i <<std::endl ;      //  for loop will iterates 5 times
        }
        int j=3;
        std::cout << "In while loop" << std::endl;
        while(j>0)
        {
            std::cout << "j=" << j <<std::endl ;    // while loop will iterates 3 times
            j--;
        }
   
    return 0;
}
```

Output:

```cpp
In for loop                                                                                    
i=1                                                                                            
i=2                                                                                            
i=3                                                                                            
i=4                                                                                            
i=5                                                                                            
In while loop                                                                                  
j=3                                                                                            
j=2                                                                                            
j=1
```

Hope this article was helpful to you. Keep Coding Keep Learning.