# Mother's and Father's Day Challenges – Day 16

> **Tags**: #java #50daysofcode #DrGvishwanathanChallenge #shriramsir

##  Day 16:

---

###  DSA-Based Problem  
**Problem**: [Delete Node in a Linked List](https://leetcode.com/problems/delete-node-in-a-linked-list/)  
**Code:**
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode(int x) { val = x; }
 * }
 */
public class Solution {
    public void deleteNode(ListNode node) {
        node.val = node.next.val;
        ListNode temp = node.next;
        node.next = temp.next;
    }
}
```

### Maths-Based Problem
 **Problem**: [Sum of Square Numbers](https://leetcode.com/problems/sum-of-square-numbers/) <br>
 **code:**
```java
class Solution {
    public boolean judgeSquareSum(int c) {
        long a = 0, b = (long) Math.sqrt(c);
        while (a <= b) {
            long s = a * a + b * b;
            if (s == c) {
                return true;
            }
            if (s < c) {
                ++a;
            } else {
                --b;
            }
        }
        return false;
    }
}
```
