Algorithm 1: O(1) - Constant Time
Description:
The execution time remains constant, regardless of the size of the input. A typical example is accessing a specific element in an array by index.

Implementation:
python
Copiar código
def constant_access(array, index):
    return array[index]

# Test
array = [10, 20, 30, 40, 50]
index = 2
print(constant_access(array, index))  # Output: 30
Algorithm 2: O(log n) - Logarithmic Time
Description:
The execution time grows logarithmically with the size of the input. An example is binary search in a sorted list.

Implementation:
python
Copiar código
def binary_search(arr, target):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == target:
            return mid
        elif arr[mid] < target:
            left = mid + 1
        else:
            right = mid - 1
    return -1

# Test
arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
target = 7
print(binary_search(arr, target))  # Output: 6 (index of element 7)
Algorithm 3: O(n) - Linear Time
Description:
The execution time grows linearly with the size of the input. An example is iterating through an array and performing an operation on each element.

Implementation:
python
Copiar código
def sum_elements(arr):
    total = 0
    for element in arr:
        total += element
    return total

# Test
arr = [1, 2, 3, 4, 5]
print(sum_elements(arr))  # Output: 15
Algorithm 4: O(n log n) - Log-Linear Time
Description:
The execution time grows faster than logarithmic but slower than polynomial. An example is the Merge Sort algorithm.

Implementation:
python
Copiar código
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left_half = arr[:mid]
        right_half = arr[mid:]

        merge_sort(left_half)
        merge_sort(right_half)

        i = j = k = 0

        while i < len(left_half) and j < len(right_half):
            if left_half[i] < right_half[j]:
                arr[k] = left_half[i]
                i += 1
            else:
                arr[k] = right_half[j]
                j += 1
            k += 1

        while i < len(left_half):
            arr[k] = left_half[i]
            i += 1
            k += 1

        while j < len(right_half):
            arr[k] = right_half[j]
            j += 1
            k += 1
    return arr

# Test
arr = [38, 27, 43, 3, 9, 82, 10]
print(merge_sort(arr))  # Output: [3, 9, 10, 27, 38, 43, 82]
Algorithm 5: O(n²) - Quadratic Time
Description:
The execution time grows quadratically with the size of the input. An example is the Insertion Sort algorithm.

Implementation:
python
Copiar código
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    return arr

# Test
arr = [12, 11, 13, 5, 6]
print(insertion_sort(arr))  # Output: [5, 6, 11, 12, 13]
Algorithm 6: O(2^n) - Exponential Time
Description:
The execution time grows exponentially with the size of the input. An example is solving the Fibonacci sequence using recursion.

Implementation:
python
Copiar código
def fibonacci(n):
    if n <= 1:
        return n
    else:
        return fibonacci(n-1) + fibonacci(n-2)

# Test
n = 5
print(fibonacci(n))  # Output: 5
Algorithm 7: O(n!) - Factorial Time
Description:
The time complexity grows extremely fast, making it impractical for large datasets. An example is solving the Traveling Salesman Problem using brute force.

Implementation:
python
Copiar código
from itertools import permutations

def traveling_salesman(distances):
    cities = list(range(len(distances)))
    min_cost = float('inf')
    best_route = None
    for perm in permutations(cities):
        cost = 0
        for i in range(len(perm) - 1):
            cost += distances[perm[i]][perm[i + 1]]
        cost += distances[perm[-1]][perm[0]]
        if cost < min_cost:
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
Discussion:
O(1) - Constant Time:

Advantages: Extremely fast and independent of the input size.
Disadvantages: Few operations can be performed in constant time.
Suitable Situations: Simple operations like accessing elements in an array.
O(log n) - Logarithmic Time:

Advantages: Very efficient for large inputs.
Disadvantages: Requires structured inputs, such as sorted lists.
Suitable Situations: Searching in balanced search trees, binary search.
O(n) - Linear Time:

Advantages: Simple to implement, good for operations that require visiting all elements.
Disadvantages: Inefficient for more complex problems.
Suitable Situations: Summing elements of an array, iterating through lists.
O(n log n) - Log-Linear Time:

Advantages: More efficient for sorting and divide-and-conquer operations.
Disadvantages: More complex to implement.
Suitable Situations: Efficient sorting algorithms like Merge Sort and Quick Sort.
O(n²) - Quadratic Time:

Advantages: Simple to understand and implement.
Disadvantages: Inefficient for large inputs.
Suitable Situations: Sorting small lists.
O(2^n) - Exponential Time:

Advantages: Useful for solving complex and specific problems.
Disadvantages: Impractical for large inputs.
Suitable Situations: Brute force problems like recursive Fibonacci.
O(n!) - Factorial Time:

Advantages: Can find the optimal solution for combinatorial problems.
Disadvantages: Extremely impractical for large inputs.
Suitable Situations: Combinatorial problems like the Traveling Salesman Problem.
Conclusion:
Each complexity class has its specific use, depending on the problem and the size of the input. Understanding these differences is crucial for choosing the most efficient algorithm for each situation. When comparing algorithms, it's important to balance simplicity and efficiency, always considering the context and requirements of the problem to be solved.
