# Programming and DSA

### Programming in Python
- **Basics:** Variables, data types, operators, control structures (if-else, loops).
- **Functions:** Definition, arguments, return values.
- **Modules and Packages:** Importing and using standard libraries.
- **File I/O:** Reading from and writing to files.
- **Exception Handling:** try, except, finally.
- **Data Structures in Python:** Lists, tuples, dictionaries, sets.

### Basic Data Structures
**Stacks:**
- **Definition:** LIFO (Last In First Out) data structure.
- **Operations:** Push, pop, peek, isEmpty.
- **Implementation in Python:**
  ```python
  stack = []
  stack.append(1)  # Push
  stack.pop()  # Pop
  ```

**Queues:**
- **Definition:** FIFO (First In First Out) data structure.
- **Operations:** Enqueue, dequeue, front, isEmpty.
- **Implementation in Python:**
  ```python
  from collections import deque
  queue = deque()
  queue.append(1)  # Enqueue
  queue.popleft()  # Dequeue
  ```

**Linked Lists:**
- **Definition:** A sequence of nodes where each node points to the next node.
- **Types:** Singly linked list, doubly linked list.
- **Implementation in Python:**
  ```python
  class Node:
      def __init__(self, data):
          self.data = data
          self.next = None

  class LinkedList:
      def __init__(self):
          self.head = None
  ```

**Trees:**
- **Definition:** Hierarchical data structure with a root node and child nodes.
- **Binary Tree:** Each node has at most two children.
- **Binary Search Tree (BST):** Left child < parent < right child.
- **Implementation in Python:**
  ```python
  class TreeNode:
      def __init__(self, data):
          self.data = data
          self.left = None
          self.right = None
  ```

**Hash Tables:**
- **Definition:** Data structure that maps keys to values using a hash function.
- **Implementation in Python:**
  ```python
  hash_table = {}
  hash_table['key'] = 'value'
  ```

### Search Algorithms
**Linear Search:**
- **Definition:** Sequentially checks each element of the list until a match is found.
- **Implementation in Python:**
  ```python
  def linear_search(arr, x):
      for i in range(len(arr)):
          if arr[i] == x:
              return i
      return -1
  ```

**Binary Search:**
- **Definition:** Searches a sorted array by repeatedly dividing the search interval in half.
- **Implementation in Python:**
  ```python
  def binary_search(arr, x):
      low, high = 0, len(arr) - 1
      while low <= high:
          mid = (low + high) // 2
          if arr[mid] == x:
              return mid
          elif arr[mid] < x:
              low = mid + 1
          else:
              high = mid - 1
      return -1
  ```

### Basic Sorting Algorithms
**Selection Sort:**
- **Definition:** Repeatedly selects the smallest element and moves it to the sorted portion of the array.
- **Implementation in Python:**
  ```python
  def selection_sort(arr):
      for i in range(len(arr)):
          min_idx = i
          for j in range(i+1, len(arr)):
              if arr[j] < arr[min_idx]:
                  min_idx = j
          arr[i], arr[min_idx] = arr[min_idx], arr[i]
  ```

**Bubble Sort:**
- **Definition:** Repeatedly swaps adjacent elements if they are in the wrong order.
- **Implementation in Python:**
  ```python
  def bubble_sort(arr):
      n = len(arr)
      for i in range(n):
          for j in range(0, n-i-1):
              if arr[j] > arr[j+1]:
                  arr[j], arr[j+1] = arr[j+1], arr[j]
  ```

**Insertion Sort:**
- **Definition:** Builds the final sorted array one item at a time.
- **Implementation in Python:**
  ```python
  def insertion_sort(arr):
      for i in range(1, len(arr)):
          key = arr[i]
          j = i - 1
          while j >= 0 and key < arr[j]:
              arr[j + 1] = arr[j]
              j -= 1
          arr[j + 1] = key
  ```

### Divide and Conquer Algorithms
**Mergesort:**
- **Definition:** Divides the array into halves, sorts each half, and then merges the sorted halves.
- **Implementation in Python:**
  ```python
  def merge_sort(arr):
      if len(arr) > 1:
          mid = len(arr) // 2
          L = arr[:mid]
          R = arr[mid:]

          merge_sort(L)
          merge_sort(R)

          i = j = k = 0
          while i < len(L) and j < len(R):
              if L[i] < R[j]:
                  arr[k] = L[i]
                  i += 1
              else:
                  arr[k] = R[j]
                  j += 1
              k += 1

          while i < len(L):
              arr[k] = L[i]
              i += 1
              k += 1

          while j < len(R):
              arr[k] = R[j]
              j += 1
              k += 1
  ```

**Quicksort:**
- **Definition:** Picks an element as a pivot, partitions the array around the pivot, and recursively sorts the partitions.
- **Implementation in Python:**
  ```python
  def quick_sort(arr):
      if len(arr) <= 1:
          return arr
      else:
          pivot = arr[len(arr) // 2]
          left = [x for x in arr if x < pivot]
          middle = [x for x in arr if x == pivot]
          right = [x for x in arr if x > pivot]
          return quick_sort(left) + middle + quick_sort(right)
  ```

### Introduction to Graph Theory
- **Graph:** A set of nodes (vertices) connected by edges.
- **Types of Graphs:** Directed, undirected, weighted, unweighted.
- **Representation:** Adjacency matrix, adjacency list.

### Basic Graph Algorithms
**Traversals:**
- **Breadth-First Search (BFS):** Explores all neighbors at the present depth before moving on to nodes at the next depth level.
  ```python
  from collections import deque
  def bfs(graph, start):
      visited = set()
      queue = deque([start])
      while queue:
          vertex = queue.popleft()
          if vertex not in visited:
              visited.add(vertex)
              queue.extend(set(graph[vertex]) - visited)
      return visited
  ```

- **Depth-First Search (DFS):** Explores as far as possible along each branch before backtracking.
  ```python
  def dfs(graph, start, visited=None):
      if visited is None:
          visited = set()
      visited.add(start)
      for next in set(graph[start]) - visited:
          dfs(graph, next, visited)
      return visited
  ```

**Shortest Path:**
- **Dijkstra's Algorithm:** Finds the shortest path from a single source node to all other nodes in a weighted graph.
  ```python
  import heapq
  def dijkstra(graph, start):
      queue = []
      heapq.heappush(queue, (0, start))
      distances = {start: 0}
      while queue:
          current_distance, current_node = heapq.heappop(queue)
          if current_distance > distances.get(current_node, float('inf')):
              continue
          for neighbor, weight in graph[current_node].items():
              distance = current_distance + weight
              if distance < distances.get(neighbor, float('inf')):
                  distances[neighbor] = distance
                  heapq.heappush(queue, (distance, neighbor))
      return distances
  ```
