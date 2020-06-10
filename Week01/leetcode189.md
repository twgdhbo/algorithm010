#### [旋转数组](https://leetcode-cn.com/problems/rotate-array/)

### solution 1

```java
class Solution {
    public void rotate(int[] nums, int k) {
        for (int i = 0; i < k; i++) {
            for (int j = 1; j < nums.length ; j++) {
                swap(nums, 0, j);
            }
        }
    }

    public void swap(int[] nums, int a, int b) {
        int temp = nums[b];
        nums[b] = nums[a];
        nums[a] = temp;
    }
}
//运行K次每次位移一位: swap first index with current index
```

comment: 自己想到的暴力破解,k取余没有做



### solution 2

```java
class Solution {
    public void rotate(int[] nums, int k) {
        k = k % nums.length;
        reverse(nums, 0, nums.length - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.length - 1);
    }

    public void reverse(int[] nums, int start, int end) {
        while (start < end) {
            int temp = nums[start];
            nums[start] = nums[end];
            nums[end] = temp;
            start++;
            end--;
        }
    }
}
//reverse
```

comment: 参考了答案的reverse使得时间复杂度为O(n)