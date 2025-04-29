# CMPS 2200 Assignment 5
## Answers

**Name:**____Jackson Burch_____________________






- **1a.**

log_d n

- **1b.**

delete-min:

work: O(d * log_d n)

insert:

work: O(log_d n)

- **1c.**

delete-min:

O(|V| * d * log_d(|V|))

insert:

O(|E| * log_d(|V|))

Total work:

W(n) = O(|V| * d * log_d(|V|) + |E| * log_d(|V|))

- **1d.**

d = |V|^epsilon



- **2a.**
APSP(i,j,k)

k=0
(the dots and underlines are for formatting do not pay attention to them)

(i,j) ___ APSP (i,j,0) ___  explanation

(0,0) ______ 0 ______  no movement

(0,1) ______ -2 _______ direct edge (0 -> 1)

(0, 2) ______ 2 ________ direct edge (0->2)

(1, 0) ______ ∞ _______ no direct edge (1->0)

(1,1) _______ 0 ________ no movement 

(1,2) _______ 1 ________ direct edge (1->2)

(2,0) _______ ∞ ________ no driect edge (2->0)

(2,1) _______ ∞ ________ no direct edge (2->1)

(2,2) _______ 0 ________ no movement



k=1

vertices {0, 1}

APSP (i, j, 1) = min(APSP i,j,0), APSP(i,j0) + APSP (1,j,0)

(i,j) ___ APSP (i,j,0) ___  explanation

(0,0) ______ 0 ______  no better path through intermediatry node 1

(0,1) ______ -2 _______ direct path was already best path

(0, 2) ______ -1 ________ with intermediary node 1 a better path can be found

(1, 0) ______ ∞ _______ no direct edge (1->0) no improvement with intermediary node

(1,1) _______ 0 ________ no movement 

(1,2) _______ 1 ________ direct path was already best path 

(2,0) _______ ∞ ________ no driect edge (2->0) no imporvement with intermediary node

(2,1) _______ ∞ ________ no direct edge (2->1) 

(2,2) _______ 0 _________ no movement



k =2

vertices {0,1,2}

APSP(i,j,2)= min(APSP(i,j,1),APSP(i,2,1)+APSP(2,j,1))

(i,j) ___ APSP (i,j,0) ___  explanation

(0,0) ______ 0 ______  no better path through intermediatry through 2 intermediary nodes

(0,1) ______ -2 _______ no better path through intermediatry through 2 intermediary nodes

(0, 2) ______ -1 ________ no better path through intermediatry through 2 intermediary nodes

(1, 0) ______ ∞ _______ no direct edge (1->0) no improvement with intermediary nodes

(1,1) _______ 0 ________ no movement 

(1,2) _______ 1 ________ no better path through intermediatry through 2 intermediary nodes 

(2,0) _______ ∞ ________ no driect edge (2->0) no imporvement with intermediary node

(2,1) _______ ∞ ________ no direct edge (2->1)  no improvement with intermediary node

(2,2) _______ 0 _________ no movement

- **2b.**

APSP(i,j,2) = min(APSP(i,j,1), APSP(i,2,1) + APSP(2,j,1))

The shortest path from i to j using nodes {0, 1, 2} is the best path not involving node 2 from k=1 or the shortest path is a new path going through the new intermediary  node 2. APSP(i, j, 1) is the best path not involing nodes 2 or 1, which is a direct path using k =0 or the shortest possible path is a new path using the intermediary node 1. 

- **2c.**

APSP(i,j,k) = min(APSP(i, j, k-1), APSP(i, k, k-1) + APSP(k, j, k-1))

similarly to my solution from part b. The shortest shorets path from i to j is the best path not using node k or the shortest path from i to k using node k-1 and then from i to j using node k-1. So finding the shorets path requires using solutions of nodes k-1.

- **2d.**

for n vertices for every k you compute the pair (i,j)

n^2 * n = n^3

work: w(n) = O(n^3)

- **2e.**

The work of our dynamically programmed algorithm w(n) = O(n^3)

Johnson's algorithm W(n) = O(|V| * |E| log |E|)

the johnson algorithm is better in most cases. Specifically when their are less edges

if the dynamically programmed algorithm would be better when the graph has many edges

- **3a.**

The MST is not gauranteed to be a solution to MMET because the MST minimizes the total weight of all the edges in the tree while MMET only minimizes the maximum weighted edge in the tree.

- **3b.**

Find the second best mst.

start with the mst you already have. delete a mst edge and replace it with the lightest edge that is not currently in the mst to reconnect the graph. Pick the trees with the smallest total weights to create the next best mst.


- **3c.**

work: O(|E| log |E|)