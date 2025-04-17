===========
Bubble sort
===========


Description
===========

Bubble sort, sometimes referred to as **sinking sort**, is a simple sorting algorithm that repeatedly 
steps through the input list element by element, comparing the current element with the one after 
it, swapping their values if needed. These passes through the list are repeated until **no swaps have 
to be performed during a pass**, meaning that the list has become fully sorted. The algorithm, which 
is a comparison sort, is named for the way the larger elements "bubble" up to the top of the list.

This simple algorithm performs poorly in real-world use and is used primarily as an educational tool. 
More efficient algorithms such as quicksort, timsort, or merge sort are used by the sorting libraries 
built into popular programming languages such as Python and Java.[2][3] However, if **parallel processing** 
is allowed, bubble sort sorts in O(n) time, making it considerably faster than parallel implementations 
of insertion sort or selection sort which do not parallelize as effectively.[citation needed]

Reference: `https://en.wikipedia.org/wiki/Bubble_sort`


Complexity
==========

* Time: O(n^2)
* Space: O(1)


Implementation
==============

.. code:: rust

    fn bubble_sort(arr: &mut [i32]) {
        let n = arr.len();
        if n <= 1 {
            return;
        }

        for i in 0..n {
            for j in 0..(n - i - 1) {
                if arr[j] > arr[j + 1] {
                    arr.swap(j, j + 1);
                }
            }
        }
    }
