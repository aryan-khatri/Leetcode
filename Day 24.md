# Mother's and Father's Day Challenges – Day 24

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 24:
**Problem Description** - [DSA](https://leetcode.com/problems/basic-calculator/description/) <br>
Solution
```java
class Solution {
    public int calculate(String s) {
        LinkedList<Integer> stack = new LinkedList<>();
        
        char[] chArr = s.toCharArray();
        int len = chArr.length, i = 0;
        int flag = 1;
        boolean firstNum = true;
        int cur = 0;
        
        while (i < len) {
            if (chArr[i] == ' ') {
                i++;
                continue;
            } else if (chArr[i] == '+') {
                flag = 1;
            } else if (chArr[i] == '-') {
                flag = -1;
            } else if (chArr[i] == '(') {
                stack.offerLast(cur);
                stack.offerLast(flag);
                firstNum = true;
            } else if (chArr[i] == ')') {
                flag = stack.pollLast();
                cur = stack.pollLast() + (flag * cur);
            } else {
                int j = i + 1;
                while (j < len && Character.isDigit(chArr[j])) {
                    j++;
                }
                int num = Integer.valueOf(s.substring(i, j));
                if (firstNum) {
                    firstNum = false;
                    cur = num;
                } else {
                    cur += flag * num;
                }
                i = j - 1;
            }
            i++;
        }
        
        return cur;
    }
}
```

---

**Problem Description** - [EASY DSA](https://leetcode.com/problems/basic-calculator/description/) <br>
Solution - 
```java
public void moveZeroes(int[] nums) {

    int j = 0;
    for(int i = 0; i < nums.length; i++) {
        if(nums[i] != 0) {
            int temp = nums[j];
            nums[j] = nums[i];
            nums[i] = temp;
            j++;
        }
    }
}
```
