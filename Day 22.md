# Mother's and Father's Day Challenges – Day 22

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 22:
**Problem Description** - [DSA](https://leetcode.com/problems/minimum-remove-to-make-valid-parentheses/) <br>
Solution
```java
class Solution {
    public String minRemoveToMakeValid(String s) {

        Set<Integer> set = new HashSet<>();
        Stack<Integer> stack = new Stack<>();
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (c == '(') stack.push(i);
            if (c == ')') {
                if (!stack.isEmpty()) stack.pop();
                else set.add(i); 
            }
        }
        // remaining false indexes of '('
        while (!stack.isEmpty()) set.add(stack.pop());
        
        StringBuffer sb = new StringBuffer();
        for (int i = 0; i < s.length(); i++) {
            if (!set.contains(i)) sb.append(s.charAt(i));
        }

        return sb.toString();
    }
}
```

---

**Problem Description** - [EASY DSA](https://leetcode.com/problems/majority-element/description/) <br>
Solution - 
```java
class Solution {
    public int majorityElement(int[] nums) {
        Arrays.sort(nums);
        return nums[nums.length / 2];
    }
}
```
