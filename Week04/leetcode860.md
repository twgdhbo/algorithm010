#### [柠檬水找零](https://leetcode-cn.com/problems/lemonade-change/)

### solution 1

```java
class Solution {
    public boolean lemonadeChange(int[] bills) {

        int change_five = 0;
        int change_ten = 0;

        for (int i = 0; i < bills.length; i++) {
            
            //0,1,3
            int cur_q = bills[i]/5 - 1;
            if (cur_q == 0) {
                change_five++;
            }else if(cur_q == 1){

                if (change_five > 0) {
                    change_five--;
                }else {
                    return false;
                }
                change_ten++;
            }else{
                if(change_ten > 0 && change_five > 0) {
                    change_five--;
                    change_ten--;
                }else if (change_five > 2){
                    change_five = change_five -3;
                }else {
                    return false;
                }
            }
            
        }

        return true;

    }
}
```

comment: