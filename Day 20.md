# Mother's and Father's Day Challenges – Day 20

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 20:
**Problem Description** - [DSA]([link](https://leetcode.com/problems/evaluate-reverse-polish-notation/description/)) <br>
Solution
```java
class Solution {
    public int evalRPN(String[] tokens) {
        Deque<Integer> stk = new ArrayDeque<>();
        for (String t : tokens) {
            if (t.length() > 1 || Character.isDigit(t.charAt(0))) {
                stk.push(Integer.parseInt(t));
            } else {
                int y = stk.pop();
                int x = stk.pop();
                switch (t) {
                case "+":
                    stk.push(x + y);
                    break;
                case "-":
                    stk.push(x - y);
                    break;
                case "*":
                    stk.push(x * y);
                    break;
                default:
                    stk.push(x / y);
                    break;
                }
            }
        }
        return stk.pop();
    }
}
```

---

**Problem Description** - [EASY DSA]([link](https://leetcode.com/problems/find-greatest-common-divisor-of-array/submissions/1638356128/)) <br>
Solution - 
```java
class Solution {
    public int findGCD(int[] nums) {
        int a=1, b=1000;
        for (int x : nums){
            a = Math.max(a,x);
            b = Math.min(b,x);
        }
        return gcd(a,b);
    }
    private int gcd(int a, int b){
        return b == 0 ? a:gcd(b, a%b);
    }
}
```
