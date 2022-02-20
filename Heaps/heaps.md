
<!-- markdownlint-disable MD004 MD009 MD014 MD024 MD040 -->

# Heaps

<!-- 
1. https://docs.google.com/document/d/1PKsR5jucFukB__jwzIakv8upM_Et_AI8sKA32TQYoIw/edit
2. Lecture1: https://courses.engr.illinois.edu/cs225/sp2021/assets/lectures/slides/cs225sp21-24-Heaps-slides.pdf
3. Lecture2: https://courses.engr.illinois.edu/cs225/sp2021/assets/lectures/slides/cs225sp21-25-HeapOps-slides.pdf
4. Handout1: https://courses.engr.illinois.edu/cs225/sp2021/assets/lectures/handouts/cs225sp21-24-Heaps-handout.pdf
5. Handout2: https://courses.engr.illinois.edu/cs225/sp2021/assets/lectures/handouts/cs225sp21-25-HeapOps-handout.pdf
-->

## Uses

* getting the smallest/largest item each time in succession

* maintaining top or bottom k elements, getting the median of large datasets 

* sorting data via heap sort

### Pre reqs of the data

* Has to be orderable 

* Has to have `>` implemented 

### ADT implementation functions

- insert 
- remove 
- isEmpty 

## min heap vs max heap

* min heap is smallest at top and higher at the bottom

* max heap is the largest at top and goes smaller at the bottom

* the logic is basically the same in either case, just inverted - we'll do min heap here but the similar prinicples apply to max heap quite easily

## Array based implementation

* the simplest way to do it is with arrays that has each level contiguous 

* it makes swaps and indexing easy 

* not having to deal with pointers as much

### Compare to other implementations 

<!-- mostly look at TA notes for this?? -->

* unsorted 

## insert() - Heapify up

* Add a bottom 

## Heapify down 

## Build heap

### Recursive proof

## Heap Sort

## Priority Queue 

