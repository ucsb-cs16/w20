---
annotatedready: true
num: Lecture 10
desc: "References and Pointers, Call by value, address and reference"
ready: true
slides: /lectures/CS16_Lecture10.pdf
annotatedpdfurl: /lectures/CS16_Lecture10_ann.pdf
lecture_date: 2018-10-31
---

# Topics

## Code from lecture


## C++ References
* Creating aliases with references


## Pointers

* Pointer declaration - difference/similarities with declaring basic types
* Accessing variables "indirectly" via pointers
* The address and indirection operators: "&" and "*"
* Differences between references and pointers
* Constant pointers and references, when and why to use them
* Pointers and arrays - similarities and differences
* Passing arrays to functions - specifically looking at how arrays degenerate to pointers on function calls.

# The good, bad and ugly about pointers

The good:

* Pointers allow arrays to be passed to functions efficiently
* Pointers allow arrays of large structs to be traversed effiently

The bad:

* Pointers can only point to one type of data (not generic)
* They don't automatically point - need to do some work

The ugly

* Bugs in code that involves pointers can cause your program to irrecoverably crash (Segmentation fault)
* Examples: dereferencing a null pointer, out of bound array access, dereferncing a pointer that has junk value.



## Call by value, address and reference
* Understanding the differences via stack diagrams
* When and why to use each of these




