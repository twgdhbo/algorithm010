#### [删除排序数组中的重复项](https://leetcode-cn.com/problems/remove-duplicates-from-sorted-array/)

### solution 1

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length < 1) {
            return nums.length;
        }
        int j = 0;
        for (int i = 1; i < nums.length; i++) {
            if (nums[i] > nums[j]) {
                j++;
                nums[j] = nums[i];
            }
        }
        return j+1;
    }
}



//two pointers
```

comment: