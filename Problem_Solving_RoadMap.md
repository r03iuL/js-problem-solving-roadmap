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
| Arrays | Indexing, resizing, contiguous memory | `[]` is dynamic; understand amortized cost |
| Strings | Immutability, char codes | `split('')` vs `Array.from()` for unicode |
| Stack (LIFO) | Push/pop, call stack analogy | Implement with array before using built-in |
| Queue (FIFO + Circular) | Enqueue/dequeue, circular buffer | `shift()` is O(n) in JS — implement with a head pointer |
| Linked List (Singly + Doubly) | Node structure, pointer manipulation | No built-in; implement `Node` class + `LinkedList` class |
| HashMap / HashSet | Hashing, collision resolution (chaining vs open addressing) | `Map` vs plain object — know the difference |
| Heap / Priority Queue | Min-heap, max-heap, heapify | No native heap in JS — implement or use a library |

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
- [JavaScript Algorithms (GitHub)](https://github.com/trekhleb/javascript-algorithms) — reference implementations in JS

---

## 🟩 Phase 2 — Non-Linear Data Structures
**Duration:** 1–1.5 weeks

**Objective:** Build tree and graph foundations before jumping into traversal patterns. The call-stack behaviour of recursion must be *traceable in your head* before moving forward.

### Topics

| Topic | Key Concepts | Notes |
|---|---|---|
| Binary Trees | Node structure, left/right children, height, depth | Draw trees by hand before coding |
| Recursion Call-Stack Tracing | Base cases, call accumulation, return values | Manually trace 3–4 levels deep on paper |
| DFS | Pre-order, in-order, post-order traversal | Implement recursive *and* iterative both |
| BFS | Level-order traversal using a queue | Always use an explicit queue — not recursion |
| Graph Basics | Adjacency list, directed vs undirected, weighted vs unweighted | Build the adjacency list by hand for small test graphs |
| Graph Traversal | DFS + BFS with a `visited` Set to avoid cycles | Check `visited` *before* pushing a node to the queue |

> **Key Insight:** BFS uses a **queue** (iterative). DFS uses a **stack** (the call stack, or an explicit stack for iterative). Mixing these up is the #1 beginner mistake in graph problems.

### Practice Protocol
- Trace every recursive call on paper before running it
- After each traversal technique: solve **1–2 LeetCode Easy problems**

### Recommended Problems
- **BFS:** Binary Tree Level Order Traversal (#102), Number of Islands (#200)
- **DFS:** Maximum Depth of Binary Tree (#104), Path Sum (#112)

### Resources
- [Binary Tree Visualizer (Visualgo)](https://visualgo.net/en/bst) — interactive tree traversal
- [William Fiset – Graph Theory (YouTube)](https://www.youtube.com/playlist?list=PLDV1Zeh2NRsDGO4--qE8yH72HFL1Km93P) — best free graph theory series

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
- Convert recursive solutions to iterative as a separate exercise

#### 🔍 Searching Algorithms
- **Linear Search** — O(n), works on unsorted data
- **Binary Search** — O(log n), requires sorted input
  - Iterative implementation (preferred in interviews)
  - Recursive implementation
  - Off-by-one errors: always use `mid = left + Math.floor((right - left) / 2)` to avoid overflow

#### 🔄 Sorting Algorithms

| Algorithm | Time (avg) | Time (worst) | Space | Stable? |
|---|---|---|---|---|
| Bubble Sort | O(n²) | O(n²) | O(1) | Yes |
| Selection Sort | O(n²) | O(n²) | O(1) | No |
| Insertion Sort | O(n²) | O(n²) | O(1) | Yes |
| Merge Sort | O(n log n) | O(n log n) | O(n) | Yes |
| Quick Sort | O(n log n) | O(n²) | O(log n) | No |
| Heap Sort | O(n log n) | O(n log n) | O(1) | No |

> **Minimum viable:** Implement Merge Sort from scratch. Understand Quick Sort conceptually. Know that JS's `Array.prototype.sort()` is implementation-defined — V8 uses TimSort.

#### ➕ Edge Case Thinking
- Empty input, single element, all duplicates, negative numbers
- Integer overflow (less critical in JS due to float64, but know when to use `BigInt`)

### Practice Protocol
- Implement binary search (both iterative and recursive variants) from scratch
- Implement Merge Sort from scratch
- Solve **1 problem per algorithm topic**

### Recommended Problems
- **Binary Search:** Binary Search (#704), Search Insert Position (#35)
- **Sorting application:** Sort Colors (#75), Merge Intervals (#56)

### Resources
- [Big-O Cheat Sheet](https://www.bigocheatsheet.com) — DS + algorithm complexity reference
- [Sorting Algorithms Visualized (Visualgo)](https://visualgo.net/en/sorting) — animated comparisons

---

## 🟪 Phase 2.7 — Critical CS Topics
**Duration:** 1 week

> Often skipped. Don't skip them — they appear in medium/hard problems and are easy marks once understood.

### Topics

#### 🧠 Bit Manipulation
- Binary representation, bitwise operators: `&`, `|`, `^`, `~`, `<<`, `>>`
- XOR tricks: `a ^ a = 0`, `a ^ 0 = a` — used to find the single non-duplicate
- Check if number is power of 2: `n & (n - 1) === 0`
- Count set bits (Brian Kernighan's algorithm)
- Bit masks for subset enumeration

#### 🔗 Union-Find (Disjoint Set Union)
- `find()` with path compression
- `union()` with union by rank
- Use case: connected components, detecting cycles in undirected graphs
- Time complexity: near O(1) amortized per operation with both optimizations

#### 📖 Trie (Prefix Tree)
- Node structure: `{ children: {}, isEnd: false }`
- `insert()`, `search()`, `startsWith()` operations
- Use case: autocomplete, word search, prefix matching
- Space: O(alphabet\_size × average\_word\_length × num\_words)

### Practice Protocol
- Implement each from scratch: Union-Find class, Trie class
- Solve **1 problem per topic**

### Recommended Problems
- **Bit Manipulation:** Single Number (#136), Number of 1 Bits (#191)
- **Union-Find:** Number of Provinces (#547)
- **Trie:** Implement Trie (#208), Longest Common Prefix (#14)

### Resources
- [CP-Algorithms: Bit Manipulation](https://cp-algorithms.com/algebra/bit-manipulation.html) — concise reference
- [Union-Find Visualization (Visualgo)](https://visualgo.net/en/ufds)

---

## 🟨 Phase 3 — Pattern Mastery
**Duration:** 4–5 weeks

**Objective:** Shift to medium-level problem solving. This is the core of interview prep. Follow the **exact order below** — patterns build on each other.

> **How to work a pattern:**
> 1. Read a pattern explanation (NeetCode video or article)
> 2. Identify the 2–3 canonical problems that define it
> 3. Solve similar problems until you can recognize the pattern from the problem statement alone — not after reading the solution

### Topics

#### 1. Two Pointers
- **When:** Sorted array, pair/triplet sum, palindrome check, container problems
- **Variants:** Opposite ends, same direction (fast/slow), multiple arrays
- **Problems:** Valid Palindrome (#125), Two Sum II (#167), 3Sum (#15), Container With Most Water (#11)

#### 2. Sliding Window
- **When:** Subarray/substring problems with a constraint (max, min, exactly k, at most k)
- **Variants:** Fixed window vs variable (shrink when constraint violated)
- **Problems:** Maximum Average Subarray I (#643), Longest Substring Without Repeating Characters (#3), Minimum Window Substring (#76)

#### 3. HashMap / Frequency-Based Patterns
- **When:** Counting occurrences, anagram detection, grouping, complement lookups
- **Variants:** Complement lookup (Two Sum style), frequency map comparison
- **Problems:** Group Anagrams (#49), Top K Frequent Elements (#347), Longest Consecutive Sequence (#128)

#### 4. Stack Patterns (incl. Monotonic Stack)
- **When:** Next greater/smaller element, histogram problems, expression parsing
- **Variants:** Monotonic increasing stack, monotonic decreasing stack
- **Problems:** Daily Temperatures (#739), Largest Rectangle in Histogram (#84), Decode String (#394)

#### 5. Binary Search (Application-Based)
- **When:** Answer lies in a sorted search space — can be implicit, not just sorted arrays
- **Variants:** "Binary search on the answer" — a powerful generalization
- **Problems:** Find Minimum in Rotated Sorted Array (#153), Koko Eating Bananas (#875), Search a 2D Matrix (#74)

#### 6. Recursion + Backtracking
- **When:** Generate all combinations/permutations, constraint satisfaction problems
- **Template:** Choose → Explore → Unchoose. Pruning is critical for performance.
- **Problems:** Subsets (#78), Permutations (#46), Combination Sum (#39), N-Queens (#51)

#### 7. Tree & Graph Pattern Applications (BFS/DFS Variants)
- **Tree DFS:** Path sum, lowest common ancestor, diameter
- **Tree BFS:** Level order, right side view, zigzag traversal
- **Graph:** Number of islands, clone graph, course schedule (cycle detection)
- **Problems:** Binary Tree Right Side View (#199), Word Ladder (#127), Course Schedule (#207)

### Practice Protocol
- Work one pattern at a time — do not interleave patterns
- For each pattern: understand it → solve easy problems → solve medium problems until recognition is automatic
- After finishing a pattern, revisit earlier problems without looking at your notes

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

### Resources
- [NeetCode Pattern Playlist (YouTube)](https://www.youtube.com/@NeetCode) — pattern-by-pattern video walkthroughs
- [LeetCode Patterns (seanprashad.com)](https://seanprashad.com/leetcode-patterns/) — problem list filtered by pattern

---

## 🟧 Phase 4 — Advanced Algorithms
**Duration:** 2–3 weeks

**Objective:** Transition into complexity-heavy problem solving. These are the techniques that separate medium solvers from hard solvers.

### Topics

| Topic | What It Covers | Key Problem Signal |
|---|---|---|
| Prefix Sum | Precompute cumulative sums for O(1) range queries; 2D variant for grids | "Sum of subarray from index i to j" |
| Advanced Greedy | Interval scheduling, activity selection, jump game variants; prove by exchange argument | "Maximize/minimize with a local choice at each step" |
| Backtracking (Complex) | Sudoku solver, word search in grid, palindrome partitioning | "Find all valid configurations" with heavy pruning |
| BFS/DFS Variations | Multi-source BFS, 0-1 BFS (deque), bidirectional BFS | Multiple start nodes, or edge weight 0 or 1 |
| Recursion Serialization | Serialize/deserialize trees, encode recursive structures | "Convert structure to string and back" |
| Combined Traversals | Problems requiring BFS and DFS used together in sequence | Multi-pass graph or tree problems |

### Practice Protocol
- After covering each topic: implement the approach, solve **2–3 problems**
- Focus on identifying *which* advanced technique a problem calls for — that recognition is the skill

### Recommended Problems
- **Prefix Sum:** Range Sum Query (#303), Subarray Sum Equals K (#560)
- **Greedy:** Jump Game (#55), Non-overlapping Intervals (#435)
- **Multi-source BFS:** Rotting Oranges (#994), 01 Matrix (#542)
- **0-1 BFS:** Minimum Cost to Make at Least One Valid Path in a Grid (#1368)

### Resources
- [CP-Algorithms: Greedy](https://cp-algorithms.com/greedy/index.html) — exchange argument proofs explained
- [Multi-source BFS (YouTube)](https://www.youtube.com/results?search_query=multi+source+BFS+leetcode) — search for problem-specific explanations

---

## 🟥 Phase 4.5 — Dynamic Programming Basics
**Duration:** 1–2 weeks

> Do this *before* NeetCode's DP section. NeetCode's DP problems will feel impossible without core DP intuition established first.

### Topics

#### 🔍 Identifying DP Problems
- A problem is likely DP if it asks for a maximum/minimum value, a count of ways, or whether something is possible
- *And* the problem has **overlapping subproblems** + **optimal substructure**

#### ⬇️ Top-Down (Memoization)
- Write the recursive solution first, then add a `memo` cache
- Natural to reason about; call-stack depth can be a concern on large inputs

```js
function fib(n, memo = {}) {
  if (n <= 1) return n;
  if (memo[n] !== undefined) return memo[n];
  return memo[n] = fib(n - 1, memo) + fib(n - 2, memo);
}
```

#### ⬆️ Bottom-Up (Tabulation)
- Fill a table iteratively starting from base cases
- No recursion overhead; explicit space control
- Harder to derive initially, but often produces cleaner final code

#### 🔗 Identifying Recurrence Relations
1. Define the subproblem: *what does `dp[i]` represent?*
2. Express `dp[i]` in terms of smaller subproblems
3. Identify base cases
4. Determine fill order

### Practice Protocol
- Always define `dp[i]` in plain English *before* writing any code
- Solve the progression below in order — do not skip ahead

### Recommended Problems (Do in Order)
1. Fibonacci (#509) — simplest memoization
2. Climbing Stairs (#70) — 1D tabulation
3. House Robber (#198) — 1D with constraint
4. Unique Paths (#62) — 2D grid
5. Coin Change (#322) — unbounded knapsack
6. Longest Common Subsequence (#1143) — 2D string DP
7. 0/1 Knapsack — not on LeetCode; implement manually

### Common DP Mistakes
- Not defining `dp[i]` precisely before writing code
- Off-by-one errors in table dimensions
- Forgetting base cases in bottom-up
- Returning `dp[n]` when the answer is `dp[n-1]`

### Resources
- [DP Patterns (LeetCode Discuss)](https://leetcode.com/discuss/general-discussion/458695/Dynamic-Programming-Patterns) — community-written pattern guide
- [Aditya Verma DP Playlist (YouTube)](https://www.youtube.com/playlist?list=PL_z_8CaSLPWekqhdCPmFohncHwz8TY2Go) — best free DP progression series

---

## 🟫 Phase 5 — NeetCode 150
**Duration:** 6–10 weeks (ongoing)

**Objective:** Now fully prepared — work through NeetCode 150 sequentially by category using JavaScript throughout.

### Topics

| # | Category | Notes |
|---|---|---|
| 1 | Arrays & Hashing | Foundation — revisits Phase 1 DSes at medium difficulty |
| 2 | Two Pointers | Builds directly on Phase 3 pattern #1 |
| 3 | Sliding Window | Builds directly on Phase 3 pattern #2 |
| 4 | Stack | Monotonic stack problems appear here |
| 5 | Binary Search | Application-based; not just sorted array search |
| 6 | Linked List | Pointer manipulation, Floyd's cycle detection |
| 7 | Trees | DFS/BFS variants, LCA, serialization |
| 8 | Tries | Phase 2.7 Trie implementation applied |
| 9 | Backtracking | Complex constraint problems |
| 10 | Heap / Priority Queue | K-th element problems, merge K lists |
| 11 | Graphs | Islands, union-find, topological sort |
| 12 | Advanced Graphs | Dijkstra, Bellman-Ford, Kruskal, Prim |
| 13 | 1D Dynamic Programming | Phase 4.5 patterns applied |
| 14 | 2D Dynamic Programming | Grid DP, string DP |
| 15 | Greedy | Phase 4 greedy applied at interview difficulty |
| 16 | Intervals | Merge, insert, overlap detection |
| 17 | Math & Geometry | Spiral matrix, rotate image, prime sieve |
| 18 | Bit Manipulation | Phase 2.7 bit topics applied |

### Practice Protocol
For every problem:
1. **Read** — fully understand before writing any code
2. **Brute force first** — state the naive approach and its complexity
3. **Optimize** — identify the bottleneck and apply the right pattern
4. **Code** — write clean JS; name variables meaningfully
5. **Complexity** — state time and space complexity explicitly
6. **Edge cases** — test: empty input, single element, all same values, negatives
7. **Review after** — watch NeetCode's solution even if you solved it independently

### Tracking Template
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
| Subarray with constraint (sum, length, distinct count) | Sliding Window |
| Count/group/lookup elements | HashMap |
| Next greater/smaller, expression parsing | Monotonic Stack |
| Search in sorted or implicitly sorted space | Binary Search |
| Generate all combinations/permutations | Backtracking |
| Shortest path (unweighted graph) | BFS |
| Explore all paths, tree problems | DFS |
| Optimal value, counting ways | Dynamic Programming |
| Greedy choice at each step (provable) | Greedy |

### JavaScript-Specific Tips

```js
// Sorting numbers (ascending) — comparator is required
arr.sort((a, b) => a - b);

// Map for O(1) lookups (any key type, preserves insertion order)
const map = new Map();

// Set for O(1) existence check
const seen = new Set();

// Queue with O(1) dequeue — use an index pointer instead of shift()
let head = 0;
const queue = [...initialItems];
while (head < queue.length) {
  const node = queue[head++];
  // process node...
}

// String to char array — Array.from() handles unicode; split('') does not
const chars = Array.from(str);

// Max/Min heap — no built-in in JS; implement manually or use a library
// Recommended: implement from scratch as practice, or use 'heap' npm package
```

---

*Last updated: 2025 | Stack: JavaScript (ES2023+) | Platform: LeetCode*
