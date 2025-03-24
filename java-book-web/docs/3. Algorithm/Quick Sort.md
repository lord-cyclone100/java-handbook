#### [Go Back ↩](../README.md)

# Quick Sort

"Quick Sort" is a `divide-and-conquer` sorting algorithm that works by selecting a pivot element, partitioning the array into two subarrays (one with elements smaller than the pivot and the other with elements greater), and recursively sorting the subarrays.

It is one of the `most efficient` sorting algorithms, performing well on large datasets.

### Implementation - Code

```java
public class QuickSort {
    public static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            int pi = partition(arr, low, high);
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    private static int partition(int[] arr, int low, int high) {
        int pivot = arr[high];
        int i = low - 1;
        for (int j = low; j < high; j++) {
            if (arr[j] < pivot) {
                i++;
                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }
        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;
        return i + 1;
    }

    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        quickSort(arr, 0, arr.length - 1);
        System.out.println("Sorted array: " + java.util.Arrays.toString(arr));
    }
}
```

**Explanantion**
- `Choose a Pivot`: Typically the last element is chosen as the pivot.
Partitioning: Rearrange elements such that those smaller than the pivot come before it, and larger ones come after.
Recursion: Apply Quick Sort recursively to the left and right subarrays.

**Example Explanation**
For input {64, 25, 12, 22, 11}:

- Select pivot 11, partition → {11, 25, 12, 22, 64}
- Select pivot 64, partition → {11, 25, 12, 22, 64}
- Select pivot 22, partition → {11, 12, 22, 25, 64}
- The array is now sorted → {11, 12, 22, 25, 64}

## Reference Image
### <img src="https://i.ibb.co/vCfyj7ZP/Quick-Sort.png" alt="Quick-Sort" border="0" />

## Time Complexity
- **Best Case:** O(nlogn)
- **Average Case:** O(nlogn)
- **Worst Case:** O(n^2)

## Space Complexity
O(log n) (Recursive function call stack)

### Constraints 
- Efficient for large datasets, outperforms Merge Sort in practice due to low memory usage.
- Not a stable sort (does not preserve the order of equal elements).
- Worst case occurs when an unbalanced pivot is chosen repeatedly.


### External Resrouce
- [Documentation](https://www.geeksforgeeks.org/java-program-for-quicksort/)
- [Documentation](https://www.baeldung.com/java-quicksort)
- [YouTube](https://youtu.be/Vtckgz38QHs?si=zenJkQTYvIvdhf_J)