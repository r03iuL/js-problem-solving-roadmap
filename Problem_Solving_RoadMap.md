# 📌 Problem-Solving Roadmap (JavaScript Focus)

> **Goal:** Build a solid DSA foundation in JavaScript, moving from data structure internals → core algorithms → pattern mastery → NeetCode 150 proficiency.
>
> **Total estimated time:** ~12–16 weeks (consistent daily practice, 1–2 hours/day)
>
> **Philosophy:** Understand before memorizing. Implement from scratch before relying on built-ins. Never rush a phase — pattern recognition built on shaky foundations collapses under medium problems.

---

## ✅ Progress Tracker

| Phase | Topic | Status |
|-------|-------|--------|
| 1 | Core Linear Data Structures | ⬜ |
| 2 | Non-Linear Data Structures | ⬜ |
| 2.5 | Core Algorithms | ⬜ |
| 2.7 | Critical CS Topics | ⬜ |
| 3 | Pattern Mastery | ⬜ |
| 4 | Advanced Algorithms | ⬜ |
| 4.5 | Dynamic Programming Basics | ⬜ |
| 5 | NeetCode 150 | ⬜ |

---

## 🟦 Phase 1 — Core Linear Data Structures
**Duration:** 1–2 weeks

**Objective:** Understand internal mechanics and implement each data structure from scratch in JavaScript — not just use them, but know *how they work internally*.

### Topics

| Data Structure | Key Concepts | JS Gotcha |
|---|---|---|
| Arrays | indexing, resizing, contiguous memory | `[]` is dynamic; understand amortized cost |
| Strings | immutability, char codes | `split('')` vs `Array.from()` for unicode |
| Stack (LIFO) | push/pop, call stack analogy | Implement with array before using built-in |
| Queue (FIFO + Circular) | enqueue/dequeue, circular buffer | JS arrays are O(n) for `shift()` — implement with pointer |
| Linked List (Singly + Doubly) | node structure, pointer manipulation | No built-in; implement `Node` class + `LinkedList` class |
| HashMap / HashSet | hashing, collision resolution (chaining vs open addressing) | `Map` vs plain object — know the difference |
| Heap / Priority Queue | min-heap, max-heap, heapify | No native heap in JS — implement or use a library |

### Practice Protocol
- After each DS: implement it from scratch in JS
- Solve **2–3 LeetCode Easy problems** that directly use that structure
- Write out time/space complexity for every operation

### Recommended Problems
- **Stack:** Valid Parentheses (#20), Min Stack (#155)
- **Queue:** Implement Queue using Stacks (#232)
- **Linked List:** Reverse Linked List (#206), Middle of Linked List (#876)
- **HashMap:** Two Sum (#1), Contains Duplicate (#217)

### Resources
- [Visualgo](https://visualgo.net/en) — animated DS visualizations
- [JavaScript Algorithms (GitHub)](https://github.com/trekhleb/javascript-algorithms) — reference implementations

---

## 🟩 Phase 2 — Non-Linear Data Structures
**Duration:** 1–1.5 weeks

**Objective:** Build tree and graph foundations before jumping into traversal patterns. The call-stack behaviour of recursion must be *traceable in your head* before you move forward.

### Topics

- **Binary Trees** — node structure, left/right children, height, depth
- **Recursion call-stack tracing** — manually trace 3–4 levels deep on paper
- **DFS** — pre-order, in-order, post-order (recursive + iterative)
- **BFS** — level-order traversal using a queue
- **Graph Basics** — adjacency list representation, directed vs undirected, weighted vs unweighted
- **Graph Traversal** — DFS + BFS with a `visited` Set to avoid cycles

### Key Insight
> BFS uses a **queue** (iterative). DFS uses a **stack** (explicit stack or the call stack via recursion). Confusing these is the #1 beginner mistake in graph problems.

### Practice Protocol
- Trace every recursive call on paper before running it
- After each traversal technique: solve **1–2 LeetCode Easy problems**

### Recommended Problems
- **BFS:** Binary Tree Level Order Traversal (#102), Number of Islands (#200)
- **DFS:** Maximum Depth of Binary Tree (#104), Path Sum (#112)

---

## 🔵 Phase 2.5 — Core Algorithms
**Duration:** 1.5–2 weeks

**Objective:** Establish algorithmic reasoning foundations *before* pattern solving. Every pattern you encounter later will require Big-O thinking and sorting/searching intuition.

### Topics

#### 📊 Big-O Complexity Analysis
- Time complexity vs space complexity — they are separate metrics
- Common complexities: O(1), O(log n), O(n), O(n log n), O(n²), O(2ⁿ)
- Amortized analysis (why dynamic array resize is still O(1) amortized)
- Drop constants and lower-order terms — know *why*, not just the rule
- **Space:** distinguish input space from auxiliary space (stack frames count)

#### 🔁 Recursion
- Base case identification — the #1 source of bugs
- Stack frame accumulation — know when you'll hit stack overflow
- Tail recursion concept (JS doesn't optimize it, but understand the idea)
- Convert recursive solutions to iterative as an exercise

#### 🔍 Searching Algorithms
- **Linear Search** — O(n), works on unsorted
- **Binary Search** — O(log n), requires sorted input
  - Iterative implementation (preferred in interviews)
  - Recursive implementation
  - Off-by-one errors: `mid = left + Math.floor((right - left) / 2)` — always use this form to avoid overflow

#### 🔄 Sorting Algorithms
| Algorithm | Time (avg) | Time (worst) | Space | Stable? |
|---|---|---|---|---|
| Bubble Sort | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n²) | O(n²) | O(1) | Yes |
| Merge Sort | O(n log n) | O(n log n) | O(n) | Yes |
| Quick Sort | O(n log n) | O(n²) | O(log n) | No |
| Heap Sort | O(n log n) | O(n log n) | O(1) | No |

> **Minimum viable:** Implement Merge Sort from scratch. Understand Quick Sort conceptually. Know that JS's `Array.prototype.sort()` is implementation-defined (V8 uses TimSort).

#### ➕ Edge Case Thinking
- Empty input, single element, all duplicates, negative numbers
- Integer overflow (less critical in JS due to float64, but know when to use `BigInt`)

### Practice Protocol
- Implement binary search (both variants) from scratch
- Implement merge sort from scratch
- Solve **1 problem per algorithm topic**

### Recommended Problems
- **Binary Search:** Binary Search (#704), Search Insert Position (#35)
- **Sorting application:** Sort Colors (#75), Merge Intervals (#56)

---

## 🟪 Phase 2.7 — Critical CS Topics
**Duration:** 1 week

> Often skipped. Don't skip them — they appear in medium/hard problems and are easy marks once understood.

### Topics

#### 🧠 Bit Manipulation
- Binary representation, bitwise operators: `&`, `|`, `^`, `~`, `<<`, `>>`
- XOR tricks: `a ^ a = 0`, `a ^ 0 = a` (find the single non-duplicate)
- Check if number is power of 2: `n & (n - 1) === 0`
- Count set bits (Brian Kernighan's algorithm)
- Bit masks for subset enumeration

#### 🔗 Union-Find (Disjoint Set Union)
- `find()` with path compression
- `union()` with union by rank
- Use case: connected components, detecting cycles in undirected graphs
- Time complexity: near O(1) amortized per operation with both optimizations

#### 📖 Trie (Prefix Tree)
- Node structure: `{children: {}, isEnd: false}`
- `insert()`, `search()`, `startsWith()` operations
- Use case: autocomplete, word search, prefix matching
- Space: O(alphabet_size × average_word_length × num_words)

### Practice Protocol
- Implement each from scratch: Union-Find class, Trie class
- Solve **1 problem per topic**

### Recommended Problems
- **Bit Manipulation:** Single Number (#136), Number of 1 Bits (#191)
- **Union-Find:** Number of Provinces (#547)
- **Trie:** Implement Trie (#208), Longest Common Prefix (#14)

---

## 🟨 Phase 3 — Pattern Mastery
**Duration:** 4–5 weeks

**Objective:** Shift to medium-level problem solving. This is the core of interview prep. Follow the **exact order below** — patterns build on each other.

> **How to work a pattern:**
> 1. Read a pattern explanation (NeetCode video or article)
> 2. Identify the 2–3 canonical problems that define it
> 3. Solve similar problems until you can recognize the pattern from the problem statement alone — not after reading the solution

### Patterns (In Order)

#### 1. Two Pointers
- When: sorted array, pair/triplet sum, palindrome check, container problems
- Variants: opposite ends, same direction (fast/slow), multiple arrays
- Problems: Valid Palindrome (#125), Two Sum II (#167), 3Sum (#15), Container With Most Water (#11)

#### 2. Sliding Window
- When: subarray/substring problems with a constraint (max, min, exactly k, at most k)
- Fixed window vs variable (shrink when constraint violated)
- Problems: Maximum Average Subarray I (#643), Longest Substring Without Repeating Characters (#3), Minimum Window Substring (#76)

#### 3. HashMap / Frequency-Based Patterns
- When: counting occurrences, anagram detection, grouping
- Complement lookup (Two Sum style)
- Problems: Group Anagrams (#49), Top K Frequent Elements (#347), Longest Consecutive Sequence (#128)

#### 4. Stack Patterns (incl. Monotonic Stack)
- When: next greater/smaller element, histogram problems, expression parsing
- Monotonic stack: maintains increasing or decreasing order
- Problems: Daily Temperatures (#739), Largest Rectangle in Histogram (#84), Decode String (#394)

#### 5. Binary Search (Application-Based)
- When: answer lies in a sorted search space — can be implicit (not just sorted arrays)
- "Binary search on the answer" — a powerful generalization
- Problems: Find Minimum in Rotated Sorted Array (#153), Koko Eating Bananas (#875), Search a 2D Matrix (#74)

#### 6. Recursion + Backtracking
- When: generate all combinations/permutations, constraint satisfaction
- Template: choose → explore → unchoose
- Pruning is critical for performance
- Problems: Subsets (#78), Permutations (#46), Combination Sum (#39), N-Queens (#51)

#### 7. Tree & Graph Pattern Applications (BFS/DFS Variants)
- Tree DFS patterns: path sum, lowest common ancestor, diameter
- Tree BFS patterns: level order, right side view, zigzag
- Graph: number of islands, clone graph, course schedule (cycle detection)
- Problems: Binary Tree Right Side View (#199), Word Ladder (#127), Course Schedule (#207)

### Problem Targets Per Pattern
| Pattern | Easy | Medium | Hard (optional) |
|---|---|---|---|
| Two Pointers | 3 | 4 | 1 |
| Sliding Window | 2 | 4 | 1 |
| HashMap | 3 | 3 | — |
| Stack / Monotonic | 2 | 4 | 1 |
| Binary Search | 2 | 4 | 1 |
| Backtracking | 2 | 4 | 1 |
| Tree & Graph | 4 | 6 | 1 |

---

## 🟧 Phase 4 — Advanced Algorithms
**Duration:** 2–3 weeks

**Objective:** Transition into complexity-heavy problem solving. These are the techniques that separate medium solvers from hard solvers.

### Topics

- **Prefix Sum** — precompute cumulative sums for O(1) range queries; 2D prefix sum for grid problems
- **Advanced Greedy** — interval scheduling, activity selection, jump game variants; prove correctness by exchange argument
- **Backtracking (Complex Cases)** — Sudoku solver, word search in grid, palindrome partitioning
- **BFS/DFS Variations**
  - Multi-source BFS (start from multiple nodes simultaneously)
  - 0-1 BFS (deque-based for graphs with edge weights 0 or 1)
  - Bidirectional BFS (meet in the middle — reduces O(b^d) to O(b^(d/2)))
- **Deep Recursion Serialization** — serialize/deserialize trees, encode structures
- **Multiple Traversal Strategies Combined** — problems requiring both BFS and DFS in sequence

### Practice Protocol
- After covering each topic: implement the approach, solve 2–3 problems
- Focus on identifying *which* advanced technique a problem calls for — that recognition is the skill

### Recommended Problems
- **Prefix Sum:** Range Sum Query (#303), Subarray Sum Equals K (#560)
- **Greedy:** Jump Game (#55), Non-overlapping Intervals (#435)
- **Multi-source BFS:** Rotting Oranges (#994), 01 Matrix (#542)

---

## 🟥 Phase 4.5 — Dynamic Programming Basics
**Duration:** 1–2 weeks

> Do this *before* NeetCode DP problems. NeetCode's DP section will feel impossible without core DP intuition.

### Core Concepts

#### Identifying DP Problems
A problem is likely DP if it asks for:
- Maximum / minimum value
- Number of ways to do something
- Whether something is possible (true/false)
…and the problem has **overlapping subproblems** + **optimal substructure**.

#### Top-Down (Memoization)
- Write the recursive solution first
- Add a `memo` object/Map to cache results
- Natural to reason about; call-stack depth can be a concern

```js
function fib(n, memo = {}) {
  if (n <= 1) return n;
  if (memo[n] !== undefined) return memo[n];
  return memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
}
```

#### Bottom-Up (Tabulation)
- Fill a table iteratively from base cases upward
- No recursion overhead; explicit space control
- Harder to derive initially, but often cleaner final code

#### Identifying Recurrence Relations
1. Define the subproblem: `dp[i]` means what?
2. Express `dp[i]` in terms of smaller subproblems
3. Identify base cases
4. Determine fill order

### DP Problem Progression (Do in Order)
1. Fibonacci (#509) — simplest memoization
2. Climbing Stairs (#70) — 1D tabulation
3. House Robber (#198) — 1D with constraint
4. Unique Paths (#62) — 2D grid
5. Coin Change (#322) — unbounded knapsack
6. Longest Common Subsequence (#1143) — 2D string DP
7. 0/1 Knapsack (not on LeetCode, implement manually)

### Common DP Mistakes
- Not defining `dp[i]` precisely before writing code
- Off-by-one errors in the table dimensions
- Forgetting to handle the base case in bottom-up
- Returning `dp[n]` when the answer is `dp[n-1]`

---

## 🟫 Phase 5 — NeetCode 150
**Duration:** 6–10 weeks (ongoing)

Now fully prepared. Work through NeetCode 150 sequentially by category. Use JavaScript throughout.

### Category Order (Follow This Sequence)
1. Arrays & Hashing
2. Two Pointers
3. Sliding Window
4. Stack
5. Binary Search
6. Linked List
7. Trees
8. Tries
9. Backtracking
10. Heap / Priority Queue
11. Graphs
12. Advanced Graphs
13. 1D Dynamic Programming
14. 2D Dynamic Programming
15. Greedy
16. Intervals
17. Math & Geometry
18. Bit Manipulation

### Per-Problem Protocol
For every problem you solve:
1. **Read** — understand the problem fully before writing any code
2. **Brute force first** — state the naive approach and its complexity
3. **Optimize** — identify the bottleneck and apply the right pattern
4. **Code** — write clean JS; name variables meaningfully
5. **Complexity** — state time and space complexity explicitly
6. **Edge cases** — test: empty input, single element, all same, negatives
7. **Review after** — watch NeetCode's solution even if you solved it

### Tracking Template (per problem)
```
Problem: #XXX Name
Approach: [pattern used]
Time: O(?)  Space: O(?)
Status: ✅ Solved independently / 🟡 Needed hint / ❌ Looked at solution
Notes: [anything non-obvious]
```

### Resources
- [NeetCode.io](https://neetcode.io) — roadmap + video solutions
- [LeetCode](https://leetcode.com) — primary practice platform
- [Blind 75](https://leetcode.com/discuss/general-discussion/460599) — curated 75 if time-constrained

---

## 🧠 Final Checklist

### Data Structures
- [ ] Arrays
- [ ] Strings
- [ ] Stack
- [ ] Queue (including circular)
- [ ] Linked List (singly + doubly)
- [ ] HashMap / HashSet
- [ ] Heap / Priority Queue
- [ ] Binary Trees
- [ ] Graphs (adjacency list)
- [ ] Trie
- [ ] Union-Find

### Algorithms & Concepts
- [ ] Big-O Analysis (time + space)
- [ ] Recursion (call-stack tracing, base cases)
- [ ] Binary Search (iterative + recursive)
- [ ] Merge Sort (implemented from scratch)
- [ ] Quick Sort (conceptual + partition logic)
- [ ] Bit Manipulation
- [ ] Prefix Sum

### Patterns (7 Core)
- [ ] Two Pointers
- [ ] Sliding Window
- [ ] HashMap / Frequency-Based
- [ ] Stack / Monotonic Stack
- [ ] Binary Search (application-based)
- [ ] Recursion + Backtracking
- [ ] Tree & Graph BFS/DFS Applications

### Advanced
- [ ] Advanced Greedy
- [ ] Multi-source BFS / 0-1 BFS
- [ ] Dynamic Programming (top-down + bottom-up)
- [ ] NeetCode 150 completed

---

## 📎 Quick Reference

### When to Use Which Pattern
| Problem Signal | Pattern |
|---|---|
| Sorted array + find pair/triplet | Two Pointers |
| Subarray with constraint (sum, length, distinct) | Sliding Window |
| Count/group elements | HashMap |
| Next greater/smaller, expression parsing | Monotonic Stack |
| Search in sorted or implicitly sorted space | Binary Search |
| Generate all combinations/permutations | Backtracking |
| Shortest path (unweighted) | BFS |
| Explore all paths, tree problems | DFS |
| Optimal value, counting ways | Dynamic Programming |
| Greedy choice at each step (provable) | Greedy |

### JavaScript-Specific Tips
```js
// Sorting (ascending) — don't forget the comparator for numbers
arr.sort((a, b) => a - b);

// Max/Min heap simulation (no built-in)
// Use a library like 'heap' or implement manually

// Map for O(1) lookups (preserves insertion order, any key type)
const map = new Map();

// Set for O(1) lookup of unique values
const seen = new Set();

// Deque simulation (for BFS / sliding window max)
const deque = []; // push to back, shift from front (use index pointer for O(1))

// String to char array
const chars = Array.from(str); // handles unicode correctly
```

---

*Last updated: 2025 | Stack: JavaScript (ES2023+) | Platform: LeetCode*
