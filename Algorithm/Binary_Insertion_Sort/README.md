#### [Go Back ↩](../README.md)

# Binary Insertion Sort

"Binary Insertion Sort" is an `optimized version` of the standard Insertion Sort, where instead of performing a linear search to find the correct position for an element, Binary Search is used. This `reduces the number of comparisons`, making the algorithm slightly `more efficient`.

However, the number of shifts (element movements) remains the same as in Insertion Sort, so the overall time complexity stays O(n²). It is useful when comparisons are more expensive than swaps.

### Implementation - Code

```java
public class InsertionSort {
    public static void insertionSort(int[] arr) {
        int n = arr.length;
        for (int i = 1; i < n; i++) {
            int key = arr[i];
            int j = i - 1;
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }
            arr[j + 1] = key;
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        insertionSort(arr);
        System.out.println("Sorted array: " + java.util.Arrays.toString(arr));
    }
}
```

**Explanantion**
- Use Binary Search to find the correct position in the sorted part of the array.
- Shift elements to the right to make space for the element.
- Insert the element in its correct position.
- Repeat for all elements

**Example Explanation**
For input {64, 25, 12, 22, 11}:

- 25 → Correct position found at index 0 → Insert → {25, 64, 12, 22, 11}
- 12 → Correct position at index 0 → Insert → {12, 25, 64, 22, 11}
- 22 → Correct position at index 1 → Insert → {12, 22, 25, 64, 11}
- 11 → Correct position at index 0 → Insert → {11, 12, 22, 25, 64}

## Reference Image
### <img src="https://i.ibb.co/5gYVqG7x/insertion-sort.png" alt="insertion-sort" border="0">

## Time Complexity
- **Best Case :** O(nlogn)
- **Average Case:** 𝑂(𝑛^2)
- **Worst Case :** 𝑂(𝑛^2)

## Space Complexity
O(1) (In-place sorting)

### Constraints 
- More efficient than Insertion Sort for large datasets, but still not as fast as Merge Sort or Quick Sort.
- Shifting elements remains costly, even though comparisons are optimized.
- Works best when comparisons are expensive (e.g., custom comparison functions).


### External Resrouce
- [Documentation](https://www.geeksforgeeks.org/binary-insertion-sort/)
- [Documentation](https://www.tutorialspoint.com/java-program-for-binary-insertion-sort)
- [YouTube](https://youtu.be/-OVB5pOZJug?si=EyPujeSjWFLEbv-s)