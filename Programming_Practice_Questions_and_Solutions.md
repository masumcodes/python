# Programming Practice Questions and Solutions

## 1. Python Program to Implement Merge Sort

``` python
# Question: Write a Python program to implement Merge Sort.

def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2

    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])

    result = []
    i = 0
    j = 0

    while i < len(left) and j < len(right):
        if left[i] <= right[j]:
            result.append(left[i])
            i += 1
        else:
            result.append(right[j])
            j += 1

    result.extend(left[i:])
    result.extend(right[j:])

    return result


arr = [38, 12, 27, 43, 9, 31, 18, 25]

print("Original list:", arr)
print("Sorted list:", merge_sort(arr))
```

------------------------------------------------------------------------

## 2. Python Program to Implement Binary Search

``` python
# Question: Write a Python program to implement Binary Search.

def binary_search(arr, target):
    low = 0
    high = len(arr) - 1

    while low <= high:
        mid = (low + high) // 2

        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            low = mid + 1
        else:
            high = mid - 1

    return -1


arr = [10, 20, 30, 40, 50, 60, 70]
target = 40

result = binary_search(arr, target)

if result != -1:
    print("Element found at index:", result)
else:
    print("Element not found")
```

------------------------------------------------------------------------

## 3. Python Program to Check Whether Two Strings Are Valid Anagrams

``` python
# Question: Write a Python program to check if two strings are valid anagrams.

def are_anagrams(str1, str2):
    return sorted(str1.lower()) == sorted(str2.lower())


str1 = "listen"
str2 = "silent"

if are_anagrams(str1, str2):
    print("The strings are valid anagrams")
else:
    print("The strings are not valid anagrams")
```

------------------------------------------------------------------------

## 4. Python Program to Check Whether a String Is a Palindrome

``` python
# Question: Write a Python program to check if a string is a palindrome.

def is_palindrome(string):
    return string == string[::-1]


string = "madam"

if is_palindrome(string):
    print("The string is a palindrome")
else:
    print("The string is not a palindrome")
```

------------------------------------------------------------------------

## 5. C++ Program to Solve the Two Sum Problem

``` cpp
// Question: Write a C++ program to solve the Two Sum problem.

#include <iostream>
#include <vector>
#include <unordered_map>
using namespace std;

int main() {
    vector<int> arr = {2, 7, 11, 15};
    int target = 9;

    unordered_map<int, int> mp;

    for (int i = 0; i < arr.size(); i++) {
        int complement = target - arr[i];

        if (mp.find(complement) != mp.end()) {
            cout << "Indices: " << mp[complement] << " and " << i << endl;
            return 0;
        }

        mp[arr[i]] = i;
    }

    cout << "No solution found" << endl;

    return 0;
}
```

------------------------------------------------------------------------

## 6. C++ Program to Check Valid Parentheses Using STL

``` cpp
// Question: Write a C++ program to check valid parentheses using Standard Template Library.

#include <iostream>
#include <stack>
using namespace std;

bool isValid(string s) {
    stack<char> st;

    for (char ch : s) {
        if (ch == '(' || ch == '{' || ch == '[') {
            st.push(ch);
        }
        else {
            if (st.empty())
                return false;

            char top = st.top();
            st.pop();

            if ((ch == ')' && top != '(') ||
                (ch == '}' && top != '{') ||
                (ch == ']' && top != '[')) {
                return false;
            }
        }
    }

    return st.empty();
}

int main() {
    string str = "{[()]}";

    if (isValid(str))
        cout << "Valid Parentheses";
    else
        cout << "Invalid Parentheses";

    return 0;
}
```

------------------------------------------------------------------------

## 7. C Program to Create a Singly Linked List Using Dynamic Memory Allocation

``` c
// Question: Write a C program to create a singly linked list using dynamic
// memory allocation (malloc). Perform insertion, deletion and reverse
// operations. Print the linked list.

#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void insert(struct Node **head, int data) {
    struct Node *newNode = (struct Node *)malloc(sizeof(struct Node));

    newNode->data = data;
    newNode->next = *head;
    *head = newNode;
}

void deleteNode(struct Node **head, int data) {
    struct Node *temp = *head;
    struct Node *prev = NULL;

    while (temp != NULL && temp->data != data) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element not found
");
        return;
    }

    if (prev == NULL)
        *head = temp->next;
    else
        prev->next = temp->next;

    free(temp);
}

void reverse(struct Node **head) {
    struct Node *prev = NULL;
    struct Node *current = *head;
    struct Node *next = NULL;

    while (current != NULL) {
        next = current->next;
        current->next = prev;
        prev = current;
        current = next;
    }

    *head = prev;
}

void printList(struct Node *head) {
    while (head != NULL) {
        printf("%d -> ", head->data);
        head = head->next;
    }

    printf("NULL
");
}

int main() {
    struct Node *head = NULL;

    insert(&head, 30);
    insert(&head, 20);
    insert(&head, 10);

    printf("Original List:
");
    printList(head);

    deleteNode(&head, 20);

    printf("After Deletion:
");
    printList(head);

    reverse(&head);

    printf("After Reversing:
");
    printList(head);

    return 0;
}
```
