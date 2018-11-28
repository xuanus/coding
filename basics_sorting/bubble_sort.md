# Bubble Sort

核心：**冒泡**，持续比较相邻元素，大的挪到后面，因此大的会逐步往后挪，故称之为冒泡。

![Bubble Sort](https://github.com/xuanus/coding/tree/f09f25ddc0c56beb8d4ed92fcfb3e81a80f8ab75/shared-files/images/bubble_sort.gif)

## Implementation

### Python

```python
#!/usr/bin/env python


def bubbleSort(alist):
    for i in xrange(len(alist)):
        print(alist)
        for j in xrange(1, len(alist) - i):
            if alist[j - 1] > alist[j]:
                alist[j - 1], alist[j] = alist[j], alist[j - 1]

    return alist

unsorted_list = [6, 5, 3, 1, 8, 7, 2, 4]
print(bubbleSort(unsorted_list))
```

### Java

```java
public class Sort {
    public static void main(String[] args) {
        int[] unsortedArray = new int[]{6, 5, 3, 1, 8, 7, 2, 4};
        bubbleSort(unsortedArray);
        System.out.println("After sort: ");
        for (int item : unsortedArray) {
            System.out.print(item + " ");
        }
    }

    public static void bubbleSort(int[] nums) {
        int len = nums.length;
        for (int i = 0; i < len; i++) {
            for (int num : nums) {
                System.out.print(num + " ");
            }
            System.out.println();
            for (int j = 1; j < len - i; j++) {
                if (nums[j - 1] > nums[j]) {
                    int temp = nums[j - 1];
                    nums[j - 1] = nums[j];
                    nums[j] = temp;
                }
            }
        }
    }
}
```

### 复杂度分析

平均情况与最坏情况均为 $$O(n^2)$$, 使用了 temp 作为临时交换变量，空间复杂度为 $$O(1)$$.

## Reference

* [冒泡排序 - 维基百科，自由的百科全书](http://zh.wikipedia.org/wiki/冒泡排序)

