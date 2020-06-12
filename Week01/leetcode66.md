#### [加一](https://leetcode-cn.com/problems/plus-one/)

### solution 1

```java
class Solution {
    public int[] plusOne(int[] digits) {

        boolean merge = false;

        for (int i = digits.length - 1; i >= 0; i--) {

                //bu jin wei
                digits[i]++;
                if(digits[i] < 10) {
                     //digits[i] = sum;
                     break;
                }else {
                    digits[i] = 0;
                    if ( i == 0) {
                        merge = true;
                    }
                }
            }

            if (merge) {
                // [1] + digits
                int[] a=new int[digits.length + 1];
                a[0]  = 1;
                for (int j = 0 ; j < digits.length; j++) {
                    a[j + 1] = digits[j];
                }
                return a;
            }else {
                return digits;
            }
            
    }
}
```

comment: 自己写的 一遍过了 空间有点大

