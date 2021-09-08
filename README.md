# assignment2-kanaparthi

# Naveen Kumar Kanaparthi

### Dubai

Dubai is one of the best cities in the world. Lifestyle in dubai is exceptionally good. The climate in dubai is perfect for 8 months of the year. **It is one of the best places to live in the world**. Weekend in dubai is on friday and saturday. **There are no personal or income taxes in dubai**.

---

# Directions from Maryville to Kansas

1. First of all, you've to go through 1st St towards N main St
2. Meanwhile turn left onto US-71 S Main St
3. Take the ramp to US-71
    1. Use the left lane to take the I-29 S/US-71 S exit towards US-59 S/Kansas city 
    2. Merge onto I-29 S/US-71 S
4. Use the middle lane to continue on US-71.

# Extra Items That We carry To Kansas

* Bagpack
* Camera
* Airpods
* Flipflops

---

**[About Myself](AboutMe.md)**

---

# My Favourite Places To Eat

I find these items delicious compare to other options

| Item  | Location  | Cost  |   
|---|---|---|
| Biryani  |Curryleaves   |$18   |   
|Haleem   |Kababgrill   |$14|
|Mc Chicken Burger  | Mc Donalds | $2 |
| Mc Flurry | Mc Donalds | $5 |

---

# Pithy Quotes

>Everything comes in time to him who knows how to wait.
– *Leo Tolstoy*

>It is not the answer that enlightens, but the question.
– *Eugène Ionesco*

# Minimum spanning tree - Kruskal's algorithm

Kruskal's algorithm finds a minimum spanning forest of an undirected edge-weighted graph. If the graph is connected, it finds a minimum spanning tree. (A minimum spanning tree of a connected graph is a subset of the edges that forms a tree that includes every vertex, where the sum of the weights of all the edges in the tree is minimized. For a disconnected graph, a minimum spanning forest is composed of a minimum spanning tree for each connected component.) It is a greedy algorithm in graph theory as in each step it adds the next lowest-weight edge that will not form a cycle to the minimum spanning forest.

Link: <https://en.wikipedia.org/wiki/Kruskal%27s_algorithm>

```
struct Edge {
    int u, v, weight;
    bool operator<(Edge const& other) {
        return weight < other.weight;
    }
};

int n;
vector<Edge> edges;

int cost = 0;
vector<int> tree_id(n);
vector<Edge> result;
for (int i = 0; i < n; i++)
    tree_id[i] = i;

sort(edges.begin(), edges.end());

for (Edge e : edges) {
    if (tree_id[e.u] != tree_id[e.v]) {
        cost += e.weight;
        result.push_back(e);

        int old_id = tree_id[e.u], new_id = tree_id[e.v];
        for (int i = 0; i < n; i++) {
            if (tree_id[i] == old_id)
                tree_id[i] = new_id;
        }
    }
}
```
Link: <https://cp-algorithms.com/graph/mst_kruskal.html>




