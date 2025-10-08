Writing effective code and their edge case considerations :

12 Adversarial Cases 

| **Category**                     | **Examples**                                                                 | **What It Breaks**                                                                                 |
|----------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------|
| Empty & Singleton                | `[]`, `[0]`, `[1]`, `[""]`                                                  | Bad base cases, unguarded indexing                                                                 |
| All Equal                        | `[5,5,5,5,5]`                                                               | Strict vs non-strict comparisons; infinite loops in binary search                                   |
| Strictly Increasing / Decreasing | `[1,2,3,4,5]`, `[5,4,3,2,1]`                                                | “Next greater/smaller” stack logic; off-by-ones in peaks/valleys                                   |
| Duplicates at the Boundary       | `[1,1,2,2,3,3]`, `target=2`                                                 | `lower_bound`/`upper_bound`; removing duplicates in-place                                          |
| Window Extremes                  | `a=[1,2,3,4], k=1` &#124; `k=len(a)`                                       | Sliding window init/teardown; counting windows incorrectly                                          |
| Alternating Signs / Parity      | `[1,-1,1,-1,1,-1]`, `[0,1,0,1,0,1]`                                        | Prefix sums; “at most K odd/zero” windows; greedy that assumes monotonicity                         |
| Overflow Bait (32-bit)          | `[109,109,109,109]`, `target=2_000_000_000`<br>`max=2_147_483_647`, `min=-2_147_483_648` | Sum/products; median formulas `(l + r) / 2` without long; area/perimeter math                      |
| Unicode & Weird Whitespace      | `s="a\u00A0b"` (non-breaking space)<br>`s=" a b "` (multiple spaces/trim)  | Tokenization, `split()` assumptions, palindrome checks                                              |
| Graph Singles & Multi-Source    | `n=1, edges=[]`<br>`sources=[0,3,9]`                                       | BFS/Topo init; visited handling; queue priming                                                      |
| 0–1 Weights (Use Deque, not Heap)| `edges: (u,v,w)` where `w ∈ {0,1}`                                         | Shortest path with binary costs; grid “free move or cost 1”—Dijkstra TLEs, use 0-1 BFS              |
| Intervals Touching vs Overlapping| `[[1,2],[2,3]]`, `[[1,2],[3,4]]`                                           | Inclusive/exclusive confusion for merging/scheduling                                                |
| DAG vs Cycle                     | DAG: `1→2→3→4`<br>Cycle: `1→2→3→1`                                         | “Topological DP” on non-DAG inputs; missing cycle detection                                         |
