Mothers and Father's Day Challenges Day  
Day 14 :

📐 **Maths Based Problem**  
🔗 [Reverse Integer](https://leetcode.com/problems/reverse-integer/description/)

🧠 **DSA Based Problem**  
🔗 [Partition List](https://leetcode.com/problems/partition-list/description/)

```java
// Maths Based Problem
public class Solution {
    public int reverse(int x) {
        int result = 0;
        while (x != 0) {
            int tail = x % 10;
            int newResult = result * 10 + tail;
            if ((newResult - tail) / 10 != result) { // check for overflow
                return 0;
            }
            result = newResult;
            x = x / 10;
        }
        return result;
    }
}
```

// DSA Based Problem
```java
/**
 * Definition for singly-linked list.
 * public class ListNode {
 *     int val;
 *     ListNode next;
 *     ListNode() {}
 *     ListNode(int val) { this.val = val; }
 *     ListNode(int val, ListNode next) { this.val = val; this.next = next; }
 * }
 */
class Solution {
    public ListNode partition(ListNode head, int x) {
        ListNode l = new ListNode();
        ListNode r = new ListNode();
        ListNode tl = l, tr = r;
        for (; head != null; head = head.next) {
            if (head.val < x) {
                tl.next = head;
                tl = tl.next;
            } else {
                tr.next = head;
                tr = tr.next;
            }
        }
        tr.next = null;
        tl.next = r.next;
        return l.next;
    }
}
```
