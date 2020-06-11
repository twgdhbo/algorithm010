#### [两数之和](https://leetcode-cn.com/problems/two-sum/)

### solution 1

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {

        Arrays.sort(nums);
        int left = 0;
        int right = nums.length - 1;
        int posA = -1;
        int posB = -1;
        while(left < right) {
            if(getSum(nums[left], nums[right]) < target) {
                left++;
            } else if(getSum(nums[left], nums[right]) > target) {
                right--;
            } else {
                int arr[] = {left, right};
                return arr;
            }
        }
        int arr[] = {-1,-1};
        return arr;   
    }

    public int getSum(int a, int b) {
        return a + b;
    }
}


//brute force, n2
```

comment:做错了，排序后index变了 只返回了值