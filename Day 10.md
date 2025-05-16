# Mother's and Father's Day Challenges – Day 6

## Math-Based Challenge

🔗 [Challenge Link](https://leetcode.com/problems/bulb-switcher/description/)

```java
class Solution {
    public int bulbSwitch(int n) {
        return (int) Math.sqrt(n);
    }
}
```
DSA-Based Challenge
🔗 [Challenge Link](https://leetcode.com/problems/delete-the-middle-node-of-a-linked-list/description/)
```java
class Solution {
    public ListNode deleteMiddle(ListNode head) {
        if (head == null || head.next == null) {
            return null;
        }

        ListNode slow = head;
        ListNode fast = head;
        ListNode prev = null;

        while (fast != null && fast.next != null) {
            prev = slow;
            slow = slow.next;
            fast = fast.next.next;
        }

        prev.next = slow.next;

        return head;
    }
}
```
🔖 Hashtags
#java #50daysofcode #DrGvishwanathanChallenge #shriramsir
