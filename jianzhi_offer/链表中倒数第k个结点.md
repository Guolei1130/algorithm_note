### 问题描述

输入一个链表，输出该链表中倒数第k个结点。

### 问题解法

采用双指针的思想。先让第一个指针走到 K-1的位置，然后第二个指针和第一个同时走，等等一个指针到了尾部的时候，第二个指针所指的位置就是倒数第K个节点。


### 代码

```
public class ListNode {
    int val;
    ListNode next = null;

    ListNode(int val) {
        this.val = val;
    }
}

public class Solution {
    public ListNode FindKthToTail(ListNode head,int k) {
        if(head==null||k<=0){
            return null;
        }
        ListNode pre=head;
        ListNode last=head;       
        for(int i=1;i<k;i++){
            if(pre.next!=null){
                pre=pre.next;
            }else{
                return null;
            }
        }
        while(pre.next!=null){
            pre = pre.next;
            last=last.next;
        }
        return last;
    }
}
```