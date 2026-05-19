# 3-Month Plan: CS Fundamentals for a Working Developer

> A focused plan to build deep understanding of data structures, algorithms, and systems — designed for an experienced Go/PHP developer without a CS degree. Assumes 6–10 hours per week.

## How to use this plan

- **Build everything in Go.** Go's explicitness about memory, pointers, and allocation will teach you more than the same exercise in PHP or Python.
- **Keep an `algorithms-in-go` repo.** Commit every implementation, every benchmark, every test. You'll reference it for years.
- **Apply each concept to real code you've written.** The "different perspective" you're after comes from connecting new vocabulary to existing intuition, not from problem-solving in the abstract.
- **If you fall behind, cut breadth before depth.** Skip Week 8 or Week 11 rather than rushing through trees or DP.

---

## Month 1 — Core Data Structures

### Week 1: Arrays and Hashing Basics
- Implement a dynamic array from scratch. Understand growth factor (1.5x vs 2x) and why amortized O(1) works.
- Implement a hash map with linear probing.
- Implement FNV-1a as your hash function; understand why it's not cryptographic.
- Read Go's `runtime/map.go` source. See how the real implementation handles collisions, growth, and iteration.

### Week 2: Hash Maps, Deeper
- Reimplement your hash map with separate chaining. Benchmark it against linear probing on realistic data shapes.
- Implement an LRU cache (hash map + doubly linked list).
- Read Skiena chapters 1–3.
- **Side project:** Find a hot-path map in your day-job code. Instrument it — count collisions, measure load factor under real load.

### Week 3: Trees
- Implement a binary search tree (insert, delete, in-order/pre-order/post-order traversal).
- Make it self-balancing. **Choose AVL first** — it's easier to reason about. Red-black is what most stdlibs use, but it's harder to get right the first time.
- Implement a trie. Use it to build a working autocomplete over 10k+ English words.
- This week is conceptually heavy. Go slower if needed.

### Week 4: Heaps and Graphs
- Implement a min-heap as an array. Build a priority queue on top.
- Implement a graph as an adjacency list, then as an adjacency matrix. Understand when each is appropriate.
- By end of week: you have a personal library of data structures you actually understand.

---

## Month 2 — Algorithms and Problem-Solving

### Week 5: Sorting and Searching
- Implement quicksort, mergesort, and heapsort.
- Read Go's `sort.Sort` source. Understand why it uses pattern-defeating quicksort.
- Master binary search variants: leftmost, rightmost, insertion point. These show up everywhere once you have eyes for them.

### Week 6: Graph Algorithms
- Implement BFS, DFS, Dijkstra (using your heap), and topological sort.
- **Build something real with one of them.** A dependency resolver, a maze solver, or a tool that visualizes import graphs in a Go codebase.
- The "build something real" step is non-negotiable. It converts knowledge into intuition.

### Week 7: Dynamic Programming
- This is where many self-taught devs hit a wall. Take it slow.
- Work through canonical problems: Fibonacci with memoization, longest common subsequence, coin change, edit distance.
- The skill isn't memorizing problems — it's recognizing the *shape* of a problem that admits DP.
- Skiena's DP chapter is gentler than CLRS. Use it.

### Week 8: Algorithm Design Techniques
- Greedy algorithms vs. divide-and-conquer. When each applies.
- Implement a bloom filter. Use it in a small project (e.g., a duplicate-URL detector for a crawler).
- Read about consistent hashing and implement it. This single concept underlies most distributed systems you've ever used.

---

## Month 3 — Systems and Synthesis

### Weeks 9–10: Build a Small Database or Interpreter
Pick **one** and go deep:

- **Database track:** Build a simple key-value store with a B-tree on disk, a write-ahead log, and basic transactions.
- **Interpreter track:** Work through Thorsten Ball's *Writing An Interpreter In Go*. Best $40 you'll spend on this plan.

Either project will pull together everything from Months 1–2 and force you to think about real engineering tradeoffs.

### Week 11: Read *Designing Data-Intensive Applications*
- Cover at least chapters 1–7.
- By now you have the foundation to actually understand it, not just nod along.
- **As you read, map concepts back to systems you work on.** When DDIA describes a B-tree vs. LSM tree tradeoff, think about which would suit your actual workload at work.

### Week 12: Synthesis and Gap-Filling
- Take a system you built or maintained at work.
- Write a design doc analyzing its data structures and algorithms using your new vocabulary.
- Where would a different data structure help? Where are the implicit assumptions about scaling?
- **This is the week the abstract knowledge becomes "looking at problems differently."** The actual thing you set out to achieve.

---

## Resources Referenced

- *The Algorithm Design Manual* — Steven Skiena
- *Designing Data-Intensive Applications* — Martin Kleppmann
- *Computer Systems: A Programmer's Perspective* — Bryant & O'Hallaron (reference, not required for this plan)
- *Writing An Interpreter In Go* — Thorsten Ball
- Go standard library source: `runtime/map.go`, `sort/sort.go`

---

## After the 3 months

Pick one specialized area that fascinates you — compilers, databases, networking, distributed systems — and go deep. MIT 6.824 (Distributed Systems) is the obvious next step for a Go developer; the labs implement Raft and MapReduce in Go and it's famous for a reason.
