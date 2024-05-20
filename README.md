<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Algorithm Complexity Examples</title>
</head>
<body>

<h1>Algorithm Complexity Examples</h1>

<h2>Algorithm 1: O(1) - Constant Time</h2>
<h3>Description:</h3>
<p>The execution time remains constant, regardless of the size of the input. A typical example is accessing a specific element in an array by index.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def constant_access(array, index):
    return array[index]

# Test
array = [10, 20, 30, 40, 50]
index = 2
print(constant_access(array, index))  # Output: 30
</code></pre>

<h2>Algorithm 2: O(log n) - Logarithmic Time</h2>
<h3>Description:</h3>
<p>The execution time grows logarithmically with the size of the input. An example is binary search in a sorted list.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left &lt;= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] &lt; target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

# Test
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 7
print(binary_search(arr, target))  # Output: 6 (index of element 7)
</code></pre>

<h2>Algorithm 3: O(n) - Linear Time</h2>
<h3>Description:</h3>
<p>The execution time grows linearly with the size of the input. An example is iterating through an array and performing an operation on each element.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def sum_elements(arr):
    total = 0
    for element in arr:
        total += element
    return total

# Test
arr = [1, 2, 3, 4, 5]
print(sum_elements(arr))  # Output: 15
</code></pre>

<h2>Algorithm 4: O(n log n) - Log-Linear Time</h2>
<h3>Description:</h3>
<p>The execution time grows faster than logarithmic but slower than polynomial. An example is the Merge Sort algorithm.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        merge_sort(left_half)
        merge_sort(right_half)

        i = j = k = 0

        while i &lt; len(left_half) and j &lt; len(right_half):
            if left_half[i] &lt; right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        while i &lt; len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j &lt; len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1
    return arr

# Test
arr = [38, 27, 43, 3, 9, 82, 10]
print(merge_sort(arr))  # Output: [3, 9, 10, 27, 38, 43, 82]
</code></pre>

<h2>Algorithm 5: O(n²) - Quadratic Time</h2>
<h3>Description:</h3>
<p>The execution time grows quadratically with the size of the input. An example is the Insertion Sort algorithm.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j &gt;= 0 and key &lt; arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

# Test
arr = [12, 11, 13, 5, 6]
print(insertion_sort(arr))  # Output: [5, 6, 11, 12, 13]
</code></pre>

<h2>Algorithm 6: O(2^n) - Exponential Time</h2>
<h3>Description:</h3>
<p>The execution time grows exponentially with the size of the input. An example is solving the Fibonacci sequence using recursion.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">def fibonacci(n):
    if n &lt;= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci(n-2)

# Test
n = 5
print(fibonacci(n))  # Output: 5
</code></pre>

<h2>Algorithm 7: O(n!) - Factorial Time</h2>
<h3>Description:</h3>
<p>The time complexity grows extremely fast, making it impractical for large datasets. An example is solving the Traveling Salesman Problem using brute force.</p>

<h3>Implementation:</h3>
<pre><code class="language-python">from itertools import permutations

def traveling_salesman(distances):
    cities = list(range(len(distances)))
    min_cost = float('inf')
    best_route = None
    for perm in permutations(cities):
        cost = 0
        for i in range(len(perm) - 1):
            cost += distances[perm[i]][perm[i + 1]]
        cost += distances[perm[-1]][perm[0]]
        if cost &lt; min_cost:
            min_cost = cost
            best_route = perm
    return min_cost, best_route

# Test
distances = [
    [0, 10, 15, 20],
    [10, 0, 35, 25],
    [15, 35, 0, 30],
    [20, 25, 30, 0]
]
print(traveling_salesman(distances))  # Output: (80, (0, 1, 3, 2))
</code></pre>

<h2>Discussion:</h2>
<ul>
    <li><strong>O(1) - Constant Time</strong>: Extremely fast and independent of the input size.
    </li>
</ul>
