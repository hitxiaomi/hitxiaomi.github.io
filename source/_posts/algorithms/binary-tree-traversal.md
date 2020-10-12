---
title: 二叉树的遍历
date: 2020-10-12 21:41:51
tags:
  - 数据结构与算法

categories:
  - 数据结构与算法
---

二叉树的遍历方式，根据根节点的访问顺序可以分为前序遍历，中序遍历以及后续遍历。
<!-- more -->



# 前序遍历



![](preorder.gif)


# 中序遍历

![](inorder.gif)


# 后序遍历

![](postorder.gif)



# c++ 示例代码

```c++

// C program for different tree traversals 
#include <iostream> 
using namespace std; 
  
/* A binary tree node has data, pointer to left child 
and a pointer to right child */
struct Node 
{ 
    int data; 
    struct Node* left, *right; 
    Node(int data) 
    { 
        this->data = data; 
        left = right = NULL; 
    } 
}; 
  
/* Given a binary tree, print its nodes according to the 
"bottom-up" postorder traversal. */
void printPostorder(struct Node* node) 
{ 
    if (node == NULL) 
        return; 
  
    // first recur on left subtree 
    printPostorder(node->left); 
  
    // then recur on right subtree 
    printPostorder(node->right); 
  
    // now deal with the node 
    cout << node->data << " "; 
} 
  
/* Given a binary tree, print its nodes in inorder*/
void printInorder(struct Node* node) 
{ 
    if (node == NULL) 
        return; 
  
    /* first recur on left child */
    printInorder(node->left); 
  
    /* then print the data of node */
    cout << node->data << " "; 
  
    /* now recur on right child */
    printInorder(node->right); 
} 
  
/* Given a binary tree, print its nodes in preorder*/
void printPreorder(struct Node* node) 
{ 
    if (node == NULL) 
        return; 
  
    /* first print data of node */
    cout << node->data << " "; 
  
    /* then recur on left sutree */
    printPreorder(node->left);  
  
    /* now recur on right subtree */
    printPreorder(node->right); 
}  
  
/* Driver program to test above functions*/
int main() 
{ 
    struct Node *root = new Node(1); 
    root->left             = new Node(2); 
    root->right         = new Node(3); 
    root->left->left     = new Node(4); 
    root->left->right = new Node(5);  
  
    cout << "\nPreorder traversal of binary tree is \n"; 
    printPreorder(root); 
  
    cout << "\nInorder traversal of binary tree is \n"; 
    printInorder(root);  
  
    cout << "\nPostorder traversal of binary tree is \n"; 
    printPostorder(root); 
  
    return 0; 
} 
```



