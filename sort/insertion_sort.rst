==============
Insertion sort
==============


Description
===========

Insertion sort is a simple sorting algorithm that builds the final sorted array (or list) one item at a 
time by comparisons. It is much less efficient on large lists than more advanced algorithms such as quicksort, 
heapsort, or merge sort. However, insertion sort provides several advantages:

    - Simple implementation: Jon Bentley shows a version that is three lines in C-like pseudo-code, and five 
     lines when optimized.[1]
    - Efficient for (quite) small data sets, much like other quadratic (i.e., O(n2)) sorting algorithms
    - More efficient in practice than most other simple quadratic algorithms such as selection sort or bubble sort
    - Adaptive, i.e., efficient for data sets that are already substantially sorted: the time complexity is O(kn) 
     when each element in the input is no more than k places away from its sorted position
    - Stable; i.e., does not change the relative order of elements with equal keys
    - In-place; i.e., only requires a constant amount O(1) of additional memory space
    - Online; i.e., can sort a list as it receives it

When people manually sort cards in a bridge hand, most use a method that is similar to insertion sort.[2] 

Reference: `https://en.wikipedia.org/wiki/Insertion_sort`


Complexity
==========

* Time: O(n^2)
* Space: O(1)
Stability: True


Implementation
==============

.. code:: rust

    fn insertion_sort<T: Ord>(arr: &mut [T]) {
        let n = arr.len();
        for i in 0..n {
            let mut j = i;
            while j > 0 && arr[j] < arr[j - 1] {
                arr.swap(j - 1, j);
                j -= 1;
            }
        }
    }
