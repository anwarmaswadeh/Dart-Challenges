# 💻 Challenges-In-Dart

## 📌 Stacks: 
### 🚀 Challenges:

**✨ Challenge 1: Reverse a List**

**- Create a function that prints the contents of a list in reverse order.**

**- my solution:**

  ```dart
void printListInReverse(List<dynamic> list) {
  for (var i = list.length - 1; i >= 0; i--) {
    print(list[i]);
  }
}

  ```

**✨ Challenge 2: Balance the Parentheses**

**- Check for balanced parentheses. Given a string, check if there are ( and ) characters,
    and return true if the parentheses in the string are balanced.**

**- my solution:**

 ```dart
bool isBalancedParentheses(String input) {
  var stack = <String>[];

  for (var char in input.split('')) {
    if (char == '(') {
      stack.add(char);
    } else if (char == ')') {
      if (stack.isEmpty || stack.removeLast() != '(') {
        return false;
      }
    }
  }

  return stack.isEmpty;
}
  ```

## 📌 Linked Lists: 
### 🚀 Challenges:

**✨ Challenge 1: Print in Reverse**

**- Create a function that prints the nodes of a linked list in reverse order.**

**- my solution:**

  ```dart
  class Node {
  var data;
  Node? next;

  Node(this.data);
}

void printLinkedListReverse(Node? head) {
  if (head == null) {
    return;
  }

  printLinkedListReverse(head.next);
  print(head.data);
}
  ```

**✨ Challenge 2: Find the Middle Node**

**- Create a function that finds the middle node of a linked list.**

**- my solution:**

 ```dart
 class ListNode {
  int value;
  ListNode? next;

  ListNode(this.value, [this.next]);
}

ListNode? findMiddleNode(ListNode? head) {
  if (head == null) {
    return null;
  }

  ListNode? slow = head;
  ListNode? fast = head;

  while (fast != null && fast.next != null) {
    slow = slow!.next;
    fast = fast.next!.next;
  }

  return slow;
}
 ```

**✨ Challenge 3: Reverse a Linked List**

**- Create a function that reverses a linked list.**

**- my solution:**

 ```dart
 class ListNode {
  int value;
  ListNode? next;

  ListNode(this.value, [this.next]);
}

ListNode? reverseLinkedList(ListNode? head) {
  ListNode? prev = null;
  ListNode? current = head;
  ListNode? next;

  while (current != null) {
    next = current.next;
    current.next = prev;
    prev = current;
    current = next;
  }

  return prev;
}

void printLinkedList(ListNode? head) {
  while (head != null) {
    print(head.value);
    head = head.next;
  }
}
 ```

**✨ Challenge 4: Remove All Occurrences**

**- Create a function that removes all occurrences of a specific element from a linked list.**

**- my solution:**

 ```dart
 class ListNode {
  int value;
  ListNode? next;

  ListNode(this.value, [this.next]);
}

ListNode? removeOccurrences(ListNode? head, int target) {
  if (head == null) {
    return null;
  }

  while (head != null && head.value == target) {
    head = head.next;
  }

  ListNode? current = head;
  ListNode? prev;

  while (current != null) {
    if (current.value == target) {
      prev!.next = current.next;
    } else {
      prev = current;
    }
    current = current.next;
  }

  return head;
}

void printLinkedList(ListNode? head) {
  while (head != null) {
    print(head.value);
    head = head.next;
  }
}
 ```
