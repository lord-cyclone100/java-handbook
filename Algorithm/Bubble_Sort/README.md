#### [Go Back ↩](../README.md)

# Bubble Sort

"Bubble Sort" is a `simple comparison-based sorting algorithm` that repeatedly swaps adjacent elements if they are in the wrong order. The algorithm continues this process until the entire array is sorted. The largest elements `"bubble up"` to their correct positions in each pass.

This algorithm is easy to implement but is inefficient for large dataset.

### Implementation - Code

```java
public class BubbleSort {
    public static void bubbleSort(int[] arr) {
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
            for (int j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        bubbleSort(arr);
        System.out.println("Sorted array: " + java.util.Arrays.toString(arr));
    }
}
```

**Explanantion**
-  Compare adjacent elements and swap if necessary.
- The largest element moves to its correct position at the end.
- Repeat this process for the remaining unsorted part of the array.
- If no swaps occur in a pass, the array is already sorted, and the loop stops early (optimized version).

**Example Explanation**
For input {64, 25, 12, 22, 11}:

- {25, 12, 22, 11, 64} (64 bubbles up)
- {12, 22, 11, 25, 64} (25 bubbles up)
- {12, 11, 22, 25, 64} (22 bubbles up)
- {11, 12, 22, 25, 64} (Sorted)

## Reference Image
### <img src="https://i.ibb.co/tpYyPpz3/Bubble-Sort.png" alt="Bubble-Sort" border="0">

## Time Complexity
- **Best Case:** O(n)
- **Average Case:** 𝑂(𝑛^2)
- **Worst Case :** 𝑂(𝑛^2)

## Space Complexity
O(1) (In-place sorting)

### Constraints 
- Inefficient for large datasets due to its O(n²) time complexity.
- Works best for small or nearly sorted arrays (optimized version).
- Stable sorting algorithm (preserves the relative order of equal elements).

### External Resrouce
- [Documentation](http://geeksforgeeks.org/java-program-for-bubble-sort/)
- [Documentation](https://www.tpointtech.com/bubble-sort-in-java)
- [YouTube](https://youtu.be/Dv4qLJcxus8?si=kN8_7OB2Jn3c8gOo)