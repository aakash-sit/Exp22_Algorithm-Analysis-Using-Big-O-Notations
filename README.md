### 🧠 Experiment 22: Algorithm Analysis using Big O Notation

This study experiment focuses on understanding and applying **Big O notation**, the most widely used mathematical notation for describing the limiting behavior of an algorithm's performance (execution time or memory usage) as the input size grows.

-----

### 🎯 Aim

To study the concept of **Algorithm Analysis** and understand the role of **Big O Notation** in describing the time complexity of algorithms.

-----

### 💡 Theory: Algorithm Analysis and Big O Notation

#### What is Algorithm Analysis?

Algorithm analysis is the process of determining the resources (primarily **time** and **space/memory**) required by any algorithm. We focus on how the algorithm's resource consumption scales with the size of the input, $N$.

#### Big O Notation ($O$): Definition

**Big O notation** formally expresses the upper bound of an algorithm's running time in the worst-case scenario. It describes the rate of growth of the function $f(N)$ (the number of operations) as $N$ approaches infinity.

  * $f(N) = O(g(N))$ means that the function $f(N)$ grows no faster than $g(N)$, or $f(N)$ is **asymptotically bounded** by $g(N)$.
  * We simplify the complexity by dropping constants and lower-order terms (e.g., $3N^2 + 5N + 10$ is simplified to **$O(N^2)$**).

#### Time Complexity Hierarchy

The following table shows common time complexities, ranked from fastest (most efficient) to slowest (least efficient).

| Notation | Name | Growth Rate | Example Algorithms |
| :--- | :--- | :--- | :--- |
| $O(1)$ | Constant | Fixed, regardless of $N$. | Accessing an array element by index; stack push/pop. |
| $O(\log N)$ | Logarithmic | Time increases slowly as $N$ doubles. | Binary Search. |
| $O(N)$ | Linear | Time increases directly proportional to $N$. | Linear Search; single loop traversal. |
| $O(N \log N)$ | Log-Linear | Highly efficient for large datasets. | Merge Sort, Quick Sort (Average Case). |
| $O(N^2)$ | Quadratic | Time increases by the square of $N$. | Bubble Sort, Selection Sort, Insertion Sort. |
| $O(2^N)$ | Exponential | Time doubles with each unit increase in $N$. | Recursive calculation of Fibonacci numbers (unoptimized). |

-----

### ⚙️ Analysis of Common Algorithms

The following table demonstrates how to derive the Big O complexity for standard operations:

| Algorithm / Operation | Code Snippet Example | Analysis / Reason | Big O |
| :--- | :--- | :--- | :--- |
| **Array Access** | `int x = arr[5];` | Executes in a fixed number of steps, regardless of array size $N$. | $O(1)$ |
| **Linear Search** | `for (int i=0; i<N; i++) {...}` | The loop runs at most $N$ times. | $O(N)$ |
| **Nested Loop (Simple)** | `for (i=0; i<N; i++) { for (j=0; j<N; j++) {...} }` | The inner loop runs $N$ times for each of the $N$ runs of the outer loop ($N \times N$). | $O(N^2)$ |
| **Bubble Sort** | Two nested loops, both iterating close to $N$ times. | Number of comparisons is proportional to $N^2$. | $O(N^2)$ |
| **Binary Search** | `while (low <= high)` where interval is halved each step. | The input space is divided by 2 repeatedly until 1 (i.e., $\log_2 N$ steps). | $O(\log N)$ |

-----

### 🔧 Practical Examples: Code to Complexity

#### Example 1: Constant Time $O(1)$

```cpp
void constantTime(int arr[], int N) {
    // Only one operation regardless of N
    cout << arr[0] << endl; 
}
```

**Analysis:** Only the array access and print operation executes. This is **$O(1)$**.

#### Example 2: Linear Time $O(N)$

```cpp
void linearTime(int arr[], int N) {
    // Loop runs N times
    for (int i = 0; i < N; i++) {
        cout << arr[i] << " ";
    }
}
```

**Analysis:** The loop executes $N$ times. The total time taken is proportional to the input size $N$. This is **$O(N)$**.

#### Example 3: Quadratic Time $O(N^2)$

```cpp
void quadraticTime(int arr[], int N) {
    // Outer loop runs N times
    for (int i = 0; i < N; i++) {
        // Inner loop runs N times
        for (int j = 0; j < N; j++) {
            cout << arr[i] * arr[j] << endl;
        }
    }
}
```

**Analysis:** The total number of operations is $N \times N = N^2$. This is **$O(N^2)$**.

-----

### 📝 Key Takeaways

1.  **Worst-Case Focus**: Big O always describes the **worst-case scenario** unless otherwise specified, guaranteeing the running time will never exceed this bound.
2.  **Scalability**: Big O helps determine how well an algorithm will perform as data sets become massive. An $O(N \log N)$ algorithm is vastly superior to an $O(N^2)$ algorithm for large $N$.
3.  **Independence of Hardware**: Big O provides a machine-independent measure of efficiency, focusing on the algorithm's logic rather than CPU speed.
