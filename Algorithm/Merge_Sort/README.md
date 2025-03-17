#### [Go Back ↩](../README.md)

# Merge Sort

"Merge Sort" is a `divide-and-conquer` sorting algorithm that `recursively splits` an array into two halves, sorts each half, and then `merges them back together` in sorted order. It is a stable sorting algorithm and works efficiently for large datasets.

Unlike Bubble Sort or Selection Sort, it `does not sort in-place` but instead `requires extra space` for merging, making it not an in-place sorting algorithm.

### Implementation - Code

```java
public class MergeSort {
    public static void mergeSort(int[] arr, int left, int right) {
        if (left < right) {
            int mid = left + (right - left) / 2;
            mergeSort(arr, left, mid);
            mergeSort(arr, mid + 1, right);
            merge(arr, left, mid, right);
        }
    }

    private static void merge(int[] arr, int left, int mid, int right) {
        int n1 = mid - left + 1;
        int n2 = right - mid;
        int[] leftArray = new int[n1];
        int[] rightArray = new int[n2];

        for (int i = 0; i < n1; i++)
            leftArray[i] = arr[left + i];
        for (int j = 0; j < n2; j++)
            rightArray[j] = arr[mid + 1 + j];

        int i = 0, j = 0, k = left;
        while (i < n1 && j < n2) {
            if (leftArray[i] <= rightArray[j]) {
                arr[k] = leftArray[i];
                i++;
            } else {
                arr[k] = rightArray[j];
                j++;
            }
            k++;
        }

        while (i < n1) {
            arr[k] = leftArray[i];
            i++;
            k++;
        }

        while (j < n2) {
            arr[k] = rightArray[j];
            j++;
            k++;
        }
    }

    public static void main(String[] args) {
        int[] arr = {64, 25, 12, 22, 11};
        mergeSort(arr, 0, arr.length - 1);
        System.out.println("Sorted array: " + java.util.Arrays.toString(arr));
    }
}
```

**Explanantion**
-  Divide: Recursively divide the array into two halves until each half has only one element.
- Sort: The smaller subarrays are already sorted (as they contain only one element).
- Merge: Merge two sorted halves into a single sorted array

**Example Explanation**
For input {64, 25, 12, 22, 11}:

- Split → {64, 25, 12} and {22, 11}
- Further split → {64, 25} {12} {22} {11}
- Merge {64, 25} → {25, 64}, {22, 11} → {11, 22}
- Merge {25, 64} and {12} → {12, 25, 64}
- Merge {12, 25, 64} and {11, 22} → {11, 12, 22, 25, 64}

## Reference Image
### <img src="https://i.ibb.co/RGmcTR4x/Merge-Sort-in.png" alt="Merge-Sort-in" border="0">

## Time Complexity
- **Best Case:** O(nlogn)
- **Average Case:** O(nlogn)
- **Worst Case:** O(nlogn)

## Space Complexity
O(n) (Uses extra space for merging)

### Constraints 
- Efficient for large datasets due to O(n log n) time complexity.
- Requires extra memory to store temporary subarrays.
- Stable sorting algorithm (preserves the order of equal elements).

### External Resrouce
- [Documentation](https://www.geeksforgeeks.org/merge-sort/)
- [Documentation](https://www.baeldung.com/java-merge-sort)
- [YouTube](https://youtu.be/3j0SWDX4AtU?si=3t621xgECG_KPKzE)