Mothers and Father's Day Challenges Day  
Day 13 :

📐 **Maths Based Problem**  
🔗 [Sign of the Product of an Array](https://leetcode.com/problems/sign-of-the-product-of-an-array/description/)

🧠 **DSA Based Problem**  
🔗 [Remove Duplicates from Sorted List II](https://leetcode.com/problems/remove-duplicates-from-sorted-list-ii/description/)


// Maths Based Problem
```java
class Solution {
    public int arraySign(int[] nums) {
        int ans = 1;
        for (int v : nums) {
            if (v == 0) {
                return 0;
            }
            if (v < 0) {
                ans *= -1;
            }
        }
        return ans;
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
    public ListNode deleteDuplicates(ListNode head) {
        ListNode dummy = new ListNode(0, head);
        ListNode pre = dummy;
        ListNode cur = head;
        while (cur != null) {
            while (cur.next != null && cur.next.val == cur.val) {
                cur = cur.next;
            }
            if (pre.next == cur) {
                pre = cur;
            } else {
                pre.next = cur.next;
            }
            cur = cur.next;
        }
        return dummy.next;
    }
}
```
