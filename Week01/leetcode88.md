#### [合并两个有序数组](https://leetcode-cn.com/problems/merge-sorted-array/)

### solution 1

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {

        int p = m - 1;
        int q = n - 1;

        while (p>=0 && q >=0) {
            if (nums1[p] >= nums2[q]) {
                nums1[p + q + 1] = nums1[p];
                p--;
            }else {
                nums1[p + q + 1] = nums2[q];
                q--;
            }               
        }

        if (p == -1) {
        //copy num2
        System.arraycopy(nums2 ,0,nums1, 0 ,q + 1);
        } 
    }
}
```

comment: q+1 第一次写成q了一次