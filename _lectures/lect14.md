---
num: Lecture 14
desc: "Double-Linked Lists and Memory Errors"
ready: true
slides: /lectures/CS16_Lecture14.pdf
annotatedpdfurl: /lectures/CS16_Lecture14_ann.pdf
annotatedready: true
lecture_date: 2020-02-27 
---


# Topics
* Practice with small single-linked list
* Intro to double-linked lists (define the types we will be working with in the upcoming classes LinkedList, Node)
* Basic operations on double-linked lists: insert, delete, and iterating through the linked list
* Problems with dynamic memory: memory leaks and dangling pointers
* Dynamic memory pitfalls: memory leaks (how to avoid and detect (valgrind))
* Detecting memory errors: Use valgrind

- To run your code in valgrind use the following command:

```
valgrind --leak-check=full <name of your executable>
```





