#### [Go Back ↩](../README.md)

# Linear Sort

"Linear Sort", commonly implemented as `Selection Sort`, is a simple sorting algorithm that works by repeatedly selecting the smallest element and placing it in the correct position. It maintains two subarrays: a sorted and an unsorted part. In each iteration, it finds the minimum element from the unsorted part and swaps it with the first unsorted element. This process continues until the entire array is sorted.

It performs well for small or nearly sorted arrays due to its simplicity and `in-place sorting nature`.

### Implementation - Code

```java
public class SelectionSort {
    public static void selectionSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            int minIndex = i;
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[minIndex]) {
                    minIndex = j;
                }
            }
            int temp = arr[minIndex];
            arr[minIndex] = arr[i];
            arr[i] = temp;
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        selectionSort(arr);
        System.out.println("Sorted array: " + java.util.Arrays.toString(arr));
    }
}
```

**Explanantion**
- In each iteration, it finds the `smallest element` in the unsorted part and `swaps it with the first` element of the unsorted section.
- This process repeats until the entire array is sorted.

**Example Explanation**
For input {64, 25, 12, 22, 11}:
- Iteration 1: Find the smallest element (11), swap with 64 → {11, 25, 12, 22, 64}
- Iteration 2: Find the smallest in the remaining (12), swap with 25 → {11, 12, 25, 22, 64}
- Iteration 3: Find the smallest (22), swap with 25 → {11, 12, 22, 25, 64}
- Iteration 4: The last two elements are already in order → {11, 12, 22, 25, 64}

## Reference Image
### <img src="https://i.ibb.co/j9gpQng9/Selection-SOrt.jpg" alt="Selection-SOrt" border="0" />

## Time Complexity
- **Best Case (Already Sorted):** 𝑂(𝑛^2)
- **Average Case:** 𝑂(𝑛^2)
- **Worst Case (Reverse Sorted):** 𝑂(𝑛^2)

## Space Complexity
O(1) (In-place sorting)

### Constraints 
- The number of elements 𝑛 in the array (directly affects time complexity).
- Comparison-based sorting → Performance remains constant irrespective of initial order.
- Inefficient for large datasets, but useful for small lists or cases where memory usage is a constraint

### External Resrouce
- [Documentation](https://www.geeksforgeeks.org/java-program-for-selection-sort/)
- [Documentation](http://tpointtech.com/selection-sort-in-java)
- [YouTube](https://youtu.be/EwjnF7rFLns?si=qdUGbbXVKDhKttFx)