# PROGRAMMING PRACTICE QUESTIONS AND SOLUTIONS

## 1. Python Program to Implement Merge Sort

**Question:** Write a Python program to implement Merge Sort.

``` python
def merge_sort(arr):
    if len(arr) <= 1:
        return arr

    mid = len(arr) // 2
    left = merge_sort(arr[:mid])
    right = merge_sort(arr[mid:])

    result = []
    i = j = 0

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

**Output:**

``` text
Original list: [38, 12, 27, 43, 9, 31, 18, 25]
Sorted list: [9, 12, 18, 25, 27, 31, 38, 43]
```

------------------------------------------------------------------------

## 2. Python Program to Implement Binary Search

**Question:** Write a Python program to implement Binary Search.

``` python
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

**Output:**

``` text
Element found at index: 3
```

------------------------------------------------------------------------

## 3. Python Program to Check Whether Two Strings Are Valid Anagrams

**Question:** Write a Python program to check if two strings are valid
anagrams.

``` python
def are_anagrams(str1, str2):
    return sorted(str1.lower()) == sorted(str2.lower())


str1 = "listen"
str2 = "silent"

if are_anagrams(str1, str2):
    print("The strings are valid anagrams")
else:
    print("The strings are not valid anagrams")
```

**Output:**

``` text
The strings are valid anagrams
```

------------------------------------------------------------------------

## 4. Python Program to Check Whether a String Is a Palindrome

**Question:** Write a Python program to check if a string is a
palindrome.

``` python
def is_palindrome(string):
    return string == string[::-1]


string = "madam"

if is_palindrome(string):
    print("The string is a palindrome")
else:
    print("The string is not a palindrome")
```

**Output:**

``` text
The string is a palindrome
```

------------------------------------------------------------------------

## 5. C++ Program to Solve the Two Sum Problem

**Question:** Write a C++ program to solve the Two Sum problem.

``` cpp
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
            cout << "Indices: " << mp[complement]
                 << " and " << i << endl;
            return 0;
        }

        mp[arr[i]] = i;
    }

    cout << "No solution found" << endl;
    return 0;
}
```

**Output:**

``` text
Indices: 0 and 1
```

------------------------------------------------------------------------

## 6. C++ Program to Check Valid Parentheses Using STL

**Question:** Write a C++ program to check valid parentheses using the
Standard Template Library.

``` cpp
#include <iostream>
#include <stack>
#include <string>
using namespace std;

bool isValid(string s) {
    stack<char> st;

    for (char ch : s) {
        if (ch == '(' || ch == '{' || ch == '[') {
            st.push(ch);
        } else {
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

**Output:**

``` text
Valid Parentheses
```

------------------------------------------------------------------------

## 7. C Program to Create a Singly Linked List Using Dynamic Memory Allocation

**Question:** Write a C program to create a singly linked list using
dynamic memory allocation (`malloc`). Perform insertion, deletion and
reverse operations. Print the linked list.

``` c
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void insert(struct Node **head, int data) {
    struct Node *newNode =
        (struct Node *)malloc(sizeof(struct Node));

    if (newNode == NULL) {
        printf("Memory allocation failed\\n");
        return;
    }

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
        printf("Element not found\\n");
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

    printf("NULL\\n");
}

int main() {
    struct Node *head = NULL;

    insert(&head, 30);
    insert(&head, 20);
    insert(&head, 10);

    printf("Original List:\\n");
    printList(head);

    deleteNode(&head, 20);

    printf("After Deletion:\\n");
    printList(head);

    reverse(&head);

    printf("After Reversing:\\n");
    printList(head);

    while (head != NULL) {
        struct Node *temp = head;
        head = head->next;
        free(temp);
    }

    return 0;
}
```

**Output:**

``` text
Original List:
10 -> 20 -> 30 -> NULL
After Deletion:
10 -> 30 -> NULL
After Reversing:
30 -> 10 -> NULL
```

------------------------------------------------------------------------

## 8. Python Program to Solve the N-Queens Problem Using Backtracking

**Question:** Write a Python program to solve the N-Queens problem using
backtracking.

``` python
def is_safe(board, row, col, n):
    # Check the same column
    for i in range(row):
        if board[i][col] == 1:
            return False

    # Check upper-left diagonal
    i, j = row - 1, col - 1
    while i >= 0 and j >= 0:
        if board[i][j] == 1:
            return False
        i -= 1
        j -= 1

    # Check upper-right diagonal
    i, j = row - 1, col + 1
    while i >= 0 and j < n:
        if board[i][j] == 1:
            return False
        i -= 1
        j += 1

    return True


def solve(board, row, n):
    if row == n:
        for r in board:
            print(" ".join("Q" if x else "." for x in r))
        print()
        return True

    found = False

    for col in range(n):
        if is_safe(board, row, col, n):
            board[row][col] = 1

            if solve(board, row + 1, n):
                found = True

            board[row][col] = 0

    return found


n = int(input("Enter number of queens: "))

if n <= 0:
    print("Enter a positive number")
else:
    board = [[0] * n for _ in range(n)]

    if not solve(board, 0, n):
        print("No solution exists")
```

**Sample Output (N = 4):**

``` text
Enter number of queens: 4
. Q . .
. . . Q
Q . . .
. . Q .

. . Q .
Q . . .
. . . Q
. Q . .
```

------------------------------------------------------------------------

## 9. Python Program to Generate Fibonacci Numbers Using Recursion with Memoization

**Question:** Write a Python program to generate Fibonacci numbers using
recursion with memoization.

``` python
def fibonacci(n, memo):
    if n <= 1:
        return n

    if n in memo:
        return memo[n]

    memo[n] = fibonacci(n - 1, memo) + fibonacci(n - 2, memo)
    return memo[n]


n = int(input("Enter number of terms: "))

if n < 0:
    print("Enter a non-negative number")
else:
    memo = {}

    print("Fibonacci Series:")
    for i in range(n):
        print(fibonacci(i, memo), end=" ")
```

**Output:**

``` text
Enter number of terms: 10
Fibonacci Series:
0 1 1 2 3 5 8 13 21 34
```

------------------------------------------------------------------------

## 10. Python Program to Implement Deep Learning-Based Face Detection Using OpenCV DNN

**Question:** Implement deep learning-based face detection using the
OpenCV DNN module and pretrained models on a Kaggle benchmark dataset.

``` python
import cv2
import matplotlib.pyplot as plt

# Load the pretrained Caffe model
net = cv2.dnn.readNetFromCaffe(
    "deploy.prototxt",
    "res10_300x300_ssd_iter_140000.caffemodel"
)

# Load input image
image = cv2.imread("face.jpg")

if image is None:
    print("Image not found")
else:
    h, w = image.shape[:2]

    # Create input blob
    blob = cv2.dnn.blobFromImage(
        cv2.resize(image, (300, 300)),
        1.0,
        (300, 300),
        (104, 177, 123)
    )

    net.setInput(blob)

    # Detect faces
    detections = net.forward()
    count = 0

    for i in range(detections.shape[2]):
        confidence = detections[0, 0, i, 2]

        if confidence > 0.5:
            box = detections[0, 0, i, 3:7] * [w, h, w, h]
            x1, y1, x2, y2 = box.astype(int)

            x1, y1 = max(0, x1), max(0, y1)
            x2, y2 = min(w - 1, x2), min(h - 1, y2)

            if x2 <= x1 or y2 <= y1:
                continue

            count += 1

            cv2.rectangle(
                image, (x1, y1), (x2, y2),
                (0, 255, 0), 2
            )

            cv2.putText(
                image,
                f"Face: {confidence:.2f}",
                (x1, max(20, y1 - 10)),
                cv2.FONT_HERSHEY_SIMPLEX,
                0.5,
                (0, 255, 0),
                2
            )

    print("Total Faces Detected:", count)

    plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()
```

**Required Libraries:**

``` bash
pip install opencv-python matplotlib
```

**Pretrained Model Files:** - `deploy.prototxt` -
`res10_300x300_ssd_iter_140000.caffemodel`

**Dataset:** WIDER FACE dataset (available on Kaggle).

**Output:** Detects faces and draws green bounding boxes around them.

**Note:** This program performs inference using a pretrained model. It
does not train the model or calculate benchmark mAP.

------------------------------------------------------------------------

## 11. Python Program to Find the Longest Substring Without Repeating Characters Using Sliding Window

**Question:** Write a Python program to find the longest substring
without repeating characters using the sliding window technique.

``` python
def longest_substring(s):
    char_index = {}
    left = 0
    max_length = 0
    result = ""

    for right in range(len(s)):
        char = s[right]

        if char in char_index and char_index[char] >= left:
            left = char_index[char] + 1

        char_index[char] = right

        if right - left + 1 > max_length:
            max_length = right - left + 1
            result = s[left:right + 1]

    return result, max_length


s = input("Enter a string: ")
substring, length = longest_substring(s)

print("Longest substring:", substring)
print("Length:", length)
```

**Output:**

``` text
Enter a string: abcabcbb
Longest substring: abc
Length: 3
```

------------------------------------------------------------------------

## 12. Python Program to Perform Matrix Transposition and Multiplication Using NumPy

**Question:** Write a Python program to perform matrix transposition and
multiplication using NumPy.

``` python
import numpy as np

# Create two matrices
A = np.array([[1, 2],
              [3, 4]])

B = np.array([[5, 6],
              [7, 8]])

# Display matrices
print("Matrix A:")
print(A)

print("\\nMatrix B:")
print(B)

# Transpose of Matrix A
print("\\nTranspose of Matrix A:")
print(A.T)

# Matrix multiplication
print("\\nMultiplication of A and B:")
print(np.dot(A, B))
```

**Output:**

``` text
Matrix A:
[[1 2]
 [3 4]]

Matrix B:
[[5 6]
 [7 8]]

Transpose of Matrix A:
[[1 3]
 [2 4]]

Multiplication of A and B:
[[19 22]
 [43 50]]
```

**Required Library:**

``` bash
pip install numpy
```

------------------------------------------------------------------------

# SUMMARY OF PROGRAMMING QUESTIONS

    No. Programming Question                                  Language
  ----- ----------------------------------------------------- ----------
      1 Merge Sort                                            Python
      2 Binary Search                                         Python
      3 Valid Anagrams                                        Python
      4 Palindrome String                                     Python
      5 Two Sum Problem                                       C++
      6 Valid Parentheses Using STL                           C++
      7 Singly Linked List Using malloc                       C
      8 N-Queens Using Backtracking                           Python
      9 Fibonacci Using Recursion and Memoization             Python
     10 Face Detection Using OpenCV DNN                       Python
     11 Longest Substring Using Sliding Window                Python
     12 Matrix Transposition and Multiplication Using NumPy   Python

**TOTAL: 12 PROGRAMMING QUESTIONS**
