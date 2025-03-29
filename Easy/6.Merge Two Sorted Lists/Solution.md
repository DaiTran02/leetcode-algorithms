# Merge Two Sorted Lists
You are given the heads of two sorted linked lists list1 and list2.

Merge the two lists into one sorted list. The list should be made by splicing together the nodes of the first two lists.

Return the head of the merged linked list.

Example 2:

Input: list1 = [], list2 = []
Output: []
Example 3:

Input: list1 = [], list2 = [0]
Output: [0]

## Solution
1. Browse 2 lists and then add each element to an emplty list

### Complexity
1. Coppy listNode1 O(m).
2. Coppy listNode2 O(n).
=> Coppy 2 listnode = O(m+n).
3. Sort listNode O((m+n)2).

### Code
	public ListNode mergeTwoLists(ListNode listNode1, ListNode listNode2) {

		ListNode listNode = new ListNode();
		ListNode lTemplate = listNode;

		while(listNode1 != null) {
			int a = listNode1.val;
			lTemplate.next = new ListNode(a);
			lTemplate = lTemplate.next;

			listNode1 = listNode1.next;
		}

		while(listNode2 != null) {
			int b = listNode2.val;
			lTemplate.next = new ListNode(b);
			lTemplate = lTemplate.next;

			listNode2 = listNode2.next;
		}

		ListNode l3 = listNode;

		sort(l3.next);

		return listNode.next;
	}

	private void sort(ListNode listNode) {

		ListNode l1;
		ListNode l2 = null;
		boolean isSwap = false;
		do {
			isSwap = false;
			l1 = listNode;
			if(l1 != null) {
				while(l1.next != l2) {
					if(l1.val > l1.next.val) {
						swap(l1, l1.next);
						isSwap = true;
					}

					l1 = l1.next;
				}
			}

			l2 = l1;


		} while (isSwap);

	}