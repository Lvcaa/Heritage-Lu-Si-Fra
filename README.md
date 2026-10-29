The original paper for the **AVL tree algorithm** is G. M. Adel’son-Vel’skii and E. M. Landis’s 1962 Russian article, “An algorithm for the organization of information.” It introduced a self-balancing binary search tree—now called an AVL tree after the authors’ initials.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)]

## Original bibliographic record

- **Authors:** G. M. Adel’son-Vel’skii (also rendered Georgy Adelson-Velsky) and E. M. Landis
- **Title:** “An algorithm for the organization of information” (*Один алгоритм организации информации*)
- **Journal:** *Doklady Akademii Nauk SSSR* (Reports of the Academy of Sciences of the USSR)
- **Volume / issue:** Volume 146, No. 2
- **Pages:** 263–266
- **Year:** 1962
- **Language:** Russian
- **English translation:** Myron J. Ricci, translator; published as “An algorithm for the organization of information,” *Soviet Mathematics–Doklady*, Volume 3, pages 1259–1263 (some sources give 1259–1262), 1962.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)][[tarjotin.cs.aalto](https://tarjotin.cs.aalto.fi/CS-A1140/2020/notes/bst-avl.html)]

A standard citation is:

> Adel’son-Vel’skii, G. M., & Landis, E. M. (1962). An algorithm for the organization of information. *Doklady Akademii Nauk SSSR*, 146(2), 263–266. English translation in *Soviet Mathematics–Doklady*, 3, 1259–1263.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)]

## Why this is the original

The article is listed in the 1962 archive of *Doklady Akademii Nauk SSSR* under the title “An algorithm for organization of information,” with Adel’son-Vel’skii and Landis as authors and page 263 as its starting page. Multiple authoritative data-structure references identify this same article as the publication that introduced the AVL tree.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)][[tarjotin.cs.aalto](https://tarjotin.cs.aalto.fi/CS-A1140/2020/notes/bst-avl.html)]

“AVL” is not an acronym for a technical phrase; it derives from the surnames **A**del’son-Vel’skii and **L**andis.[[tarjotin.cs.aalto](https://tarjotin.cs.aalto.fi/CS-A1140/2020/notes/bst-avl.html)][[khoury.northeastern](https://khoury.northeastern.edu/home/vip/teach/Algorithms/7_hash_RBtree_simpleDS/AVL%20tree%20-%20Wikipedia.pdf)]

## The problem in its computing era

The problem was how to keep an ordered collection useful as it changed. A program might need to find a record by key, add a new one, or remove one without repeatedly rebuilding the whole collection. A sorted array supports binary search, but inserting or deleting an item can require moving many later items. A sequential file can be simple to maintain, but finding a particular record may mean scanning much of it. A binary search tree offers another route: comparisons guide each search down a path, and updates can be made locally. Its weakness is that the path can become nearly as long as a list when keys arrive in an unfortunate order. The AVL contribution was to keep that path short by maintaining a height condition as updates happen.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[Cornell CS312](https://www.cs.cornell.edu/courses/cs312/2007fa/lectures/lec14.html)]

This was a practical concern in early information processing, when computers were costly, memory and storage were limited, and processing time mattered. An algorithm that avoided scanning or reorganizing a large ordered collection could make better use of those resources. This is historical context for the problem, rather than a claim that the four-page article gives a hardware survey or ties the invention to one particular machine. The paper frames its subject broadly as the “organization of information.” Contemporary writing on data structures likewise treated how information was represented in memory and how it could be accessed as a central programming problem.[[MathNet paper record](https://www.mathnet.ru/eng/dan26964)][[Annual Review in Automatic Programming (1969)](https://www.sciencedirect.com/science/article/pii/0066413869900366)]

Before AVL trees, programmers already had ordered arrays, sequential files, and binary search trees; the search-tree idea itself was not new. The missing guarantee was that a dynamically updated binary search tree would stay shallow. Periodic rebuilding could restore balance, but it requires extra work at rebuild time. AVL trees instead repair local imbalance after insertion or deletion with tree rotations. This yields logarithmic worst-case height while preserving the search-tree ordering. The choice reflects an important trade-off: spend a small amount of work during updates to keep later searches predictably short.[[Cornell CS312](https://www.cs.cornell.edu/courses/cs312/2007fa/lectures/lec14.html)][[UNSW AVL lecture](https://cgi.cse.unsw.edu.au/~cs2521/20T2/lecs/avl/slides.html)]

## Authors and publication setting

The authors were G. M. Adel’son-Vel’skii and E. M. Landis, mathematicians working in the Soviet Union. The article appeared in the mathematics section of *Doklady Akademii Nauk SSSR*, a Soviet Academy of Sciences journal that published brief reports of research. MathNet’s record gives the paper’s submission date as 13 April 1962 and notes that it was presented by I. G. Petrovskii. It appeared later that year in volume 146, issue 2, pages 263–266. These details place the work in a mathematical research publication setting; they do not establish that the authors were responding to a particular commercial database or computer project.[[MathNet paper record](https://www.mathnet.ru/eng/dan26964)]

The paper’s title and framing are deliberately broad: it describes an algorithm for organizing information, not a new type of tree named after its inventors. The later name “AVL tree” made the authors’ contribution easy to refer to internationally. An English translation appeared in *Soviet Mathematics–Doklady*, helping make the work accessible to readers who did not read Russian.[[MathNet paper record](https://www.mathnet.ru/eng/dan26964)][[NIST DADS](https://xlinux.nist.gov/dads/HTML/avltree.html)]

## Algorithm and context

The paper proposed a binary search tree maintained in a balanced form so that lookup, insertion, and deletion retain logarithmic worst-case behavior. In modern terminology, an AVL tree is a height-balanced binary search tree: for every node, the heights of its left and right subtrees differ by at most one.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[tarjotin.cs.aalto](https://tarjotin.cs.aalto.fi/CS-A1140/2020/notes/bst-avl.html)]

The original authors called the structure an “algorithm for the organization of information,” reflecting its purpose as a method for storing and retrieving ordered information efficiently, rather than using today’s term “AVL tree.” The modern balance-factor formulation—left-subtree height minus right-subtree height, constrained to `-1, 0,` or `1`—is a later pedagogical standardization of the structure introduced in the 1962 paper.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)][[tarjotin.cs.aalto](https://tarjotin.cs.aalto.fi/CS-A1140/2020/notes/bst-avl.html)][[cs.put.poznan](https://www.cs.put.poznan.pl/mszachniuk/mszachniuk_files/lab_aisd/Szachniuk-ASD-t2.pdf)]

## Terminology and notation

In current notation, let `h(v)` be the height of node `v`'s subtree, and let `L(v)` and `R(v)` denote its left and right child subtrees. The AVL condition is `|h(L(v)) − h(R(v))| ≤ 1` at every node. A balance factor is often defined as `BF(v) = h(L(v)) − h(R(v))`, so allowed values are `−1`, `0`, and `+1`; some texts reverse the subtraction, so the signs can swap while the condition stays the same. Height conventions also differ: some count edges and others count nodes. These are notation choices in modern explanations, not a claim that the original paper used this exact symbolic language.[[Cornell CS312](https://www.cs.cornell.edu/courses/cs312/2007fa/lectures/lec14.html)][[ETH Zürich AVL lecture](https://lec.inf.ethz.ch/DA/2022/slides/daAll.en.handout.2x2.pdf)]

When insertion or deletion makes a node violate the condition, a rotation changes links while preserving the in-order key sequence. A single rotation repairs an outside imbalance (left-left or right-right); a double rotation repairs an inside imbalance (left-right or right-left). In modern textbooks these are commonly named LL, RR, LR, and RL cases. Some translations and later technical accounts call balanced trees “admissible”; “AVL tree” became the standard eponym afterward.[[McCloskey, Insertion and Deletion in AVL Trees](https://www.cs.scranton.edu/~mccloske/courses/cmps240/avl_trees_report.pdf)][[MathNet paper record](https://www.mathnet.ru/eng/dan26964)]

## Design choices and trade-offs

The key design choice is a strict local height rule: each node's two subtree heights may differ by at most one. This makes the height bound follow recursively from the rule, independent of insertion order. The smallest AVL tree of height `h` must have subtrees of heights `h−1` and `h−2`, giving a Fibonacci-like minimum-size recurrence. That proof is also why AVL trees are sometimes associated with Fibonacci numbers.[[Cornell CS312](https://www.cs.cornell.edu/courses/cs312/2007fa/lectures/lec14.html)][[NIST DADS](https://xlinux.nist.gov/dads/HTML/avltree.html)]

The rule favors reliably short searches but requires bookkeeping and repair during updates. Implementations can store each node's height, or store only a compact balance state and update it as operations travel back up the search path. After insertion, rebalancing stops once the repaired subtree returns to its former height; deletion can continue to affect ancestors and can need repairs at multiple levels. These consequences explain why AVL trees can suit search-heavy workloads, while looser balancing schemes may make updates cheaper.[[UNSW AVL lecture](https://cgi.cse.unsw.edu.au/~cs2521/20T2/lecs/avl/slides.html)][[Amani, Lai & Tarjan, 2016](https://arxiv.org/abs/1506.03528)]

## Rediscovery and attribution

The sources consulted for this README consistently identify the 1962 Adel’son-Vel’skii and Landis paper as the first published dynamically maintained height-balanced binary search tree. I found no well-supported account of an earlier independent invention of this same AVL rule, or a substantive attribution dispute over the AVL name. This reports what the cited historical and reference sources document; it does not prove that no unpublished or unrecorded parallel idea existed. The paper itself is catalogued in the *Doklady* archive with the authors, submission date, presenter, volume, issue, and pages.[[MathNet paper record](https://www.mathnet.ru/eng/dan26964)][[Cambridge, Advanced Data Structures](https://www.cambridge.org/core/books/abs/advanced-data-structures/balanced-search-trees/E4D8994947D174C4F4F971DBB080E18D)][[NIST DADS](https://xlinux.nist.gov/dads/HTML/avltree.html)]

## Later variants and descendants

The AVL paper helped establish the broader design pattern of keeping a search tree logarithmically shallow by restoring an invariant after updates. Later structures chose different invariants and update trade-offs:

- **Red-black trees:** Rudolf Bayer introduced symmetric binary B-trees in 1972; Guibas and Sedgewick later developed the red/black coloring framework. Their balance condition is less strict than AVL's, often making updates convenient while allowing somewhat taller trees.[[CLRS, Red-Black Trees](https://bobson.ludost.net/books/algo/book6/chap14.htm)][[NIST DADS](https://xlinux.nist.gov/dads/HTML/avltree.html)]
- **Weight-balanced trees:** Nievergelt and Reingold (1973) control subtree sizes rather than heights, offering another way to bound search paths.[[MIT 6.006 lecture notes](https://www.idc-online.com/technical_references/pdfs/information_technology/Balanced_Binary_Search_Trees.pdf)]
- **Splay trees:** Sleator and Tarjan (1985) move accessed nodes toward the root. They do not maintain an AVL-style per-node balance condition, instead guaranteeing logarithmic amortized cost across operation sequences.[[CLRS, Red-Black Trees chapter notes](https://bobson.ludost.net/books/algo/book6/chap14.htm)]
- **Treaps and randomized search trees:** Seidel and Aragon (1996) combine search-tree key order with randomized priorities to obtain expected balance.[[MIT 6.006 lecture notes](https://www.idc-online.com/technical_references/pdfs/information_technology/Balanced_Binary_Search_Trees.pdf)]
- **Weak AVL (WAVL) and rank-balanced trees:** These use integer ranks and relaxed local rank differences, retaining logarithmic height while reducing the rebalancing burden of strict AVL maintenance, especially for updates.[[Haeupler, Sen & Tarjan, Rank-Balanced Trees](https://www.microsoft.com/en-us/research/publication/rank-balanced-trees-2/)]
- **B-trees:** Bayer and McCreight's multiway search trees (1972) address external storage by keeping many keys per node and reducing disk accesses; they are a related response to ordered retrieval, rather than a direct binary-tree variant.[[MIT 6.006 lecture notes](https://www.idc-online.com/technical_references/pdfs/information_technology/Balanced_Binary_Search_Trees.pdf)]

These are descendants in the broad algorithmic sense of balanced search-tree design, not all direct modifications of AVL trees. Later work also revisited AVL's update costs: a 2016 analysis established that mixed insertion and deletion sequences can require `Θ(n log n)` total rotations, showing that the strict balance guarantee does not imply a constant amortized number of rotations per update.[[Amani, Lai & Tarjan, 2016](https://arxiv.org/abs/1506.03528)]

## Later developments

AVL trees were the first widely recognized self-balancing binary search tree structure and became foundational for balanced-tree research. Later balanced search trees, notably red-black trees, address similar ordering and retrieval goals with different rebalancing rules and implementation trade-offs; contemporary studies still compare AVL and red-black tree variants.[[onlinelibrary.wiley](https://onlinelibrary.wiley.com/doi/10.1002/spe.3437)]

For citation purposes, use the Russian *Doklady* version as the original primary source, and cite Ricci’s English translation when quoting or relying on the English text.[[xlinux.nist](https://xlinux.nist.gov/dads/HTML/avltree.html)][[mathnet](https://www.mathnet.ru/php/archive.phtml?jrnid=dan&wshow=contents&viewarchiveID=8&vl=146&option_lang=eng)]
