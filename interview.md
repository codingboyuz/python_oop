

1. 📚 **Nazariy savollar** (Computer Science fundamentals, OOP, DSA, tizim dizayni)
2. 🧑‍💻 **Coding tasklar (LeetCode Top 50)** – har biriga tushuntirilgan yechim bilan
3. 💬 **Behavioral (HR) savollar** – STAR metodida javob berish uchun

---

# 📚 1-QISM: NAZARIY SAVOLLAR (Eng ko‘p chiqadiganlari)

### 🔹 Data Structures

1. Array va Linked List farqi?
2. Stack va Queue farqi?
3. Binary Tree va Binary Search Tree farqi?
4. Heap nima? Priority Queue qanday ishlaydi?
5. HashMap qanday ishlaydi? Collision qanday hal qilinadi?

### 🔹 Algorithms

1. Binary Search qanday ishlaydi?
2. Merge Sort va Quick Sort farqi?
3. Dynamic Programming nima? Misol bilan tushuntiring.
4. Breadth First Search (BFS) va Depth First Search (DFS) farqi?
5. Time Complexity va Space Complexity nima?

### 🔹 OOP va Software Engineering

1. OOPning 4 asosiy tamoyili (Encapsulation, Inheritance, Polymorphism, Abstraction).
2. SOLID prinsiplar nima?
3. Design Patterns: Singleton, Factory, Observer tushuntirish.
4. Thread vs Process farqi?
5. Deadlock nima va qanday oldini olish mumkin?

### 🔹 System Design (Senior daraja uchun)

1. URL Shortener (bit.ly) qanday dizayn qilasiz?
2. Chat app (Telegram, WhatsApp) arxitekturasi qanday quriladi?
3. Amazon’da “Add to Cart” funksiyasi qanday ishlaydi?
4. Database Sharding nima?
5. Load Balancer va Caching qachon ishlatiladi?

---

# 🧑‍💻 2-QISM: CODING TASKLAR (Top 10 LeetCode Classic)

### ✅ Task 1: Two Sum (LeetCode #1)

```python
def two_sum(nums, target):
    lookup = {}
    for i, num in enumerate(nums):
        diff = target - num
        if diff in lookup:
            return [lookup[diff], i]
        lookup[num] = i
    return []
```

⏱ O(n) | 🔹 HashMap orqali hal qilinadi.

---

### ✅ Task 2: Reverse Linked List (LeetCode #206)

```python
def reverse_list(head):
    prev = None
    curr = head
    while curr:
        nxt = curr.next
        curr.next = prev
        prev = curr
        curr = nxt
    return prev
```

⏱ O(n) | 🔹 LinkedListni pointerlarni almashtirib teskari qilamiz.

---

### ✅ Task 3: Valid Parentheses (LeetCode #20)

```python
def isValid(s: str) -> bool:
    stack = []
    mapping = {")": "(", "}": "{", "]": "["}
    for char in s:
        if char in mapping:
            if not stack or stack[-1] != mapping[char]:
                return False
            stack.pop()
        else:
            stack.append(char)
    return not stack
```

⏱ O(n) | 🔹 Stack bilan yechiladi.

---

### ✅ Task 4: Merge Intervals (LeetCode #56)

```python
def merge(intervals):
    intervals.sort(key=lambda x: x[0])
    merged = []
    for i in intervals:
        if not merged or merged[-1][1] < i[0]:
            merged.append(i)
        else:
            merged[-1][1] = max(merged[-1][1], i[1])
    return merged
```

⏱ O(n log n) | 🔹 Sort + interval birlashtirish.

---

### ✅ Task 5: Maximum Subarray (Kadane’s Algorithm, LeetCode #53)

```python
def maxSubArray(nums):
    best = nums[0]
    curr = nums[0]
    for num in nums[1:]:
        curr = max(num, curr + num)
        best = max(best, curr)
    return best
```

⏱ O(n) | 🔹 Dynamic Programming.

---

### ✅ Task 6: Climbing Stairs (LeetCode #70)

```python
def climbStairs(n):
    if n <= 2: return n
    a, b = 1, 2
    for _ in range(3, n+1):
        a, b = b, a+b
    return b
```

⏱ O(n) | 🔹 Fibonacci bilan bog‘liq DP masalasi.

---

### ✅ Task 7: Product of Array Except Self (LeetCode #238)

```python
def productExceptSelf(nums):
    n = len(nums)
    left, right, res = [1]*n, [1]*n, [1]*n
    
    for i in range(1, n):
        left[i] = left[i-1] * nums[i-1]
    for i in range(n-2, -1, -1):
        right[i] = right[i+1] * nums[i+1]
    for i in range(n):
        res[i] = left[i] * right[i]
    return res
```

⏱ O(n) | 🔹 Division ishlatmasdan prefix-suffix orqali hal qilinadi.

---

### ✅ Task 8: Search in Rotated Sorted Array (LeetCode #33)

Binary Search modifikatsiyasi.

---

### ✅ Task 9: Longest Substring Without Repeating Characters (LeetCode #3)

Sliding Window bilan yechiladi.

---

### ✅ Task 10: Word Break (LeetCode #139)

Dynamic Programming bilan yechiladi.

---

# 💬 3-QISM: BEHAVIORAL SAVOLLAR (Amazon “Leadership Principles” asosida)

1. **Tell me about a time you disagreed with your manager.**
   → STAR metodida: Situation, Task, Action, Result.

2. **Describe a time you failed and how you handled it.**
   → Xatoni yashirmasdan, undan olgan saboqni ko‘rsatish kerak.

3. **Give an example of a time you took initiative.**
   → Liderlik qobiliyatingizni ko‘rsatish.

4. **How do you prioritize tasks under pressure?**
   → Deadline qisqa bo‘lsa, vazifalarni bo‘lib chiqib ishlashni tushuntirish.

5. **What motivates you to work at \[Google/Amazon/Meta]?**
   → Kompaniya missioniga mos javob berish.

---


