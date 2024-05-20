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

<!-- Add other algorithms here -->

</body>
</html>
