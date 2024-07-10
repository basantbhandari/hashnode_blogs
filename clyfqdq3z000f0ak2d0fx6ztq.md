---
title: "621. Task Scheduler"
datePublished: Wed Jul 10 2024 11:02:28 GMT+0000 (Coordinated Universal Time)
cuid: clyfqdq3z000f0ak2d0fx6ztq
slug: 621-task-scheduler
tags: dsa

---

You are given an array of CPU `tasks`, each represented by letters A to Z, and a cooling time, `n`. Each cycle or interval allows the completion of one task. Tasks can be completed in any order, but there's a constraint: **identical** tasks must be separated by at least `n` intervals due to cooling time.

​Return the *minimum number of intervals* required to complete all tasks.

**Example 1:**

**Input:** tasks = \["A","A","A","B","B","B"\], n = 2

**Output:** 8

**Explanation:** A possible sequence is: A -&gt; B -&gt; idle -&gt; A -&gt; B -&gt; idle -&gt; A -&gt; B.

After completing task A, you must wait two cycles before doing A again. The same applies to task B. In the 3<sup>rd</sup> interval, neither A nor B can be done, so you idle. By the 4<sup>th</sup> cycle, you can do A again as 2 intervals have passed.

**Example 2:**

**Input:** tasks = \["A","C","A","B","D","B"\], n = 1

**Output:** 6

**Explanation:** A possible sequence is: A -&gt; B -&gt; C -&gt; D -&gt; A -&gt; B.

With a cooling interval of 1, you can repeat a task after just one other task.

**Example 3:**

**Input:** tasks = \["A","A","A", "B","B","B"\], n = 3

**Output:** 10

**Explanation:** A possible sequence is: A -&gt; B -&gt; idle -&gt; idle -&gt; A -&gt; B -&gt; idle -&gt; idle -&gt; A -&gt; B.

There are only two types of tasks, A and B, which need to be separated by 3 intervals. This leads to idling twice between repetitions of these tasks.

**Constraints:**

* `1 <= tasks.length <= 10<sup>4</sup>`
    
* `tasks[i]` is an uppercase English letter.
    
* `0 <= n <= 100`
    

Solution:

```python
class Solution:
    def leastInterval(self, tasks: List[str], n: int) -> int:
        # hashmap : "letter" -> frequency
        count = Counter(tasks)
        # max heep simulation
        maxHeap = [-cnt for cnt in count.values()]
        heapq.heapify(maxHeap)
        # initialization
        time = 0
        q = deque()  # pairs of [-cnt, idleTime]

        while maxHeap or q:
            time += 1

            if not maxHeap:
                time = q[0][1]
            else:
                cnt = 1 + heapq.heappop(maxHeap)
                if cnt:
                    q.append([cnt, time + n])
            if q and q[0][1] == time:
                heapq.heappush(maxHeap, q.popleft()[0])
                
        return time
```