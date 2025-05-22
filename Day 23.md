# Mother's and Father's Day Challenges – Day 19

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 19:
**Problem Description** - [DSA](https://leetcode.com/problems/longest-valid-parentheses/description/) <br>
Solution
```java
class Solution {
    public int longestValidParentheses(String s) {
        if(s == null || s.length() == 0) return 0;
        int len = s.length();
        int result = 0;
        int[] dp = new int[len + 1];
        char[] arr = s.toCharArray();
        for(int i = 1; i < arr.length; i++){
            char c = arr[i];
            if(c == ')'){
                if(arr[i - 1] == '('){
                    dp[i + 1] = dp[i - 1] + 2;
                    result = Math.max(result, dp[i + 1]);
                }
                else if(arr[i - 1] == ')'){
                    if(i - 1 - dp[i] >=0 && arr[i - 1 - dp[i]] == '('){
                        dp[i + 1] = dp[i] + 2 + ((i - 1 - dp[i] >= 0) ? dp[i - 1 - dp[i]] : 0);
                        result = Math.max(result, dp[i + 1]);
                    }
                }
            }
        }
        return result;
    }
}
```

---

**Problem Description** - [EASY DSA](https://leetcode.com/problems/search-insert-position/description/) <br>
Solution - 
```java
public class Solution {
    public int searchInsert(int[] nums, int target) {
        int h = 0;
        int t = nums.length - 1;
        int m = (h + t ) / 2;
        while (h <= t )
        {
            m = (h + t) / 2;
        if (nums [m] == target){
            return m;
        } else if(nums[m] < target){
            h = m + 1;
        } else {
            t = m - 1;
        }
    }
    return h;
    }
}
```
