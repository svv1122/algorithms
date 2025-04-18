==============
Selection sort
==============


Description
===========

In computer science, selection sort is an in-place comparison sorting algorithm. It has 
a O(n2) time complexity, which makes it inefficient on large lists, and generally performs 
worse than the similar insertion sort. Selection sort is noted for its simplicity and has 
performance advantages over more complicated algorithms in certain situations, particularly 
where auxiliary memory is limited.

The algorithm divides the input list into two parts: a sorted sublist of items which is built 
up from left to right at the front (left) of the list and a sublist of the remaining unsorted 
items that occupy the rest of the list. Initially, the sorted sublist is empty and the unsorted 
sublist is the entire input list. The algorithm proceeds by finding the smallest (or largest, 
depending on sorting order) element in the unsorted sublist, exchanging (swapping) it with the 
leftmost unsorted element (putting it in sorted order), and moving the sublist boundaries one 
element to the right.

The time efficiency of selection sort is quadratic, so there are a number of sorting techniques 
which have better time complexity than selection sort. 

Reference: `https://en.wikipedia.org/wiki/Selection_sort`


Complexity
==========

* Time: O(n^2)
* Space: O(1)
* Stability: False


Implementation
==============

.. code:: rust

    fn selection_sort<T: PartialOrd>(arr: &mut [T]) {
        let n = arr.len();
        if n <= 1 {
            return;
        }

        for i in 0..n {
            let mut min_index = i;

            for j in (i + 1)..n {
                if arr[j] < arr[min_index] {
                    min_index = j;
                }
            }

            if min_index != i {
                arr.swap(i, min_index);
            }
        }
    }
