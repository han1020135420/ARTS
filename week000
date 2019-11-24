# Algorithm
You are given two non-empty linked lists representing two non-negative integers. 
The digits are stored in reverse order and each of their nodes contain a single digit. 
Add the two numbers and return it as a linked list.
You may assume the two numbers do not contain any leading zero, except the number 0 itself.
Example:

Input: (2 -> 4 -> 3) + (5 -> 6 -> 4)
Output: 7 -> 0 -> 8
Explanation: 342 + 465 = 807.


class Solution {
    public ListNode addTwoNumbers(ListNode l1, ListNode l2) {
        ListNode l3 = new ListNode(0);
        ListNode tail = l3;
        int preFlag = 0;

        while(l1 != null || l2 != null || preFlag/10 > 0) {
            preFlag /= 10;
            if (l1 != null) {
                preFlag += l1.val;
                l1 = l1.next;
            }
            if (l2 != null) {
                preFlag += l2.val;
                l2 = l2.next;
            }
            tail.next = new ListNode(preFlag % 10);
            tail = tail.next;
        }
        return l3.next;
    }
}



# Review

# Tip
自己搭建了一个梯子

# Share

刚开始写还不知道从哪些方面开始，后续再慢慢完善。


