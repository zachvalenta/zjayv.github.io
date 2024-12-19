# 📚️ MY BOOKS

## 💡 little ideas 弄明白

> what should the form factor be here? repo? notebook? animation?

* compilers https://www.achaq.dev/blog/artemis https://www.achaq.dev/blog/compilers
* financial modeling https://quantus.finance/
* conventional commits https://github.com/charmbracelet/gum
* financial exchange https://www.youtube.com/watch?v=b1e4t2k2KJY
* state machines https://www.achaq.dev/blog/distributed-systems-state-machines-special-relativity
* dependency injection
* parser generator with Bison
* ledger https://news.ycombinator.com/item?id=42269227
* dimensional analysis
* strength of record

### apple stat project

### crosstabs

```python
import pandas as pd

# Sample data: our exit poll data includes an overrepresentation of college-educated white voters
data = pd.DataFrame({
    'group': ['College-Educated White', 'All Other Voters'],
    'sample_size': [600, 400],  # Over-representation of college-educated white voters
    'biden_support': [0.65, 0.50]  # Biden support in each group
})

# Known election result for Biden (e.g., 52%)
actual_biden_support = 0.52

# Step 1: Calculate total Biden support from the unweighted sample
total_biden_votes_unweighted = sum(data['sample_size'] * data['biden_support'])
total_votes = sum(data['sample_size'])
biden_support_unweighted = total_biden_votes_unweighted / total_votes

print(f"Unweighted Biden support: {biden_support_unweighted:.2f}")

# Step 2: Calculate the necessary adjustment (weighting factor) to match actual election outcome
weighting_factor = actual_biden_support / biden_support_unweighted

# Step 3: Apply the weighting factor to the overrepresented group's support level
# We adjust the weight of each group to match the actual result
data['adjusted_biden_support'] = data['biden_support'] * weighting_factor

# Step 4: Calculate the new overall weighted Biden support
total_biden_votes_weighted = sum(data['sample_size'] * data['adjusted_biden_support'])
biden_support_weighted = total_biden_votes_weighted / total_votes

# Display the results
print(f"Weighted Biden support: {biden_support_weighted:.2f}")
print(data[['group', 'biden_support', 'adjusted_biden_support']])
```

### coverage

https://nedbatchelder.com/blog/202411/coveragepy_originally.html

### dimensional analysis

```python
import csv
from collections import defaultdict

# Example sales data (similar to previous example)
data = [
    {'Product': 'Laptop', 'Region': 'East', 'Sales': 10000},
    {'Product': 'Phone', 'Region': 'West', 'Sales': 8000},
    {'Product': 'Laptop', 'Region': 'East', 'Sales': 12000},
    {'Product': 'Tablet', 'Region': 'West', 'Sales': 5000},
    {'Product': 'Phone', 'Region': 'East', 'Sales': 9000}
]

# Dictionary to store aggregated sales
sales_summary = defaultdict(int)

# Aggregate sales by Product and Region
for record in data:
    product = record['Product']
    region = record['Region']
    sales = record['Sales']
    # Using a tuple (product, region) as key to aggregate sales
    sales_summary[(product, region)] += sales

# Print the aggregated sales
for (product, region), total_sales in sales_summary.items():
    print(f"Product: {product}, Region: {region}, Total Sales: {total_sales}")
```

### Levenshtein distance

```python
def levenshtein_distance(s1: str, s2: str) -> int:
    """
    Compute the Levenshtein distance between two strings.

    :param s1: First string
    :param s2: Second string
    :return: Levenshtein distance
    """
    # Initialize matrix with size (len(s1)+1) x (len(s2)+1)
    rows, cols = len(s1) + 1, len(s2) + 1
    dp = [[0] * cols for _ in range(rows)]

    # Fill the first row and column with indices
    for i in range(rows):
        dp[i][0] = i
    for j in range(cols):
        dp[0][j] = j

    # Fill the rest of the matrix
    for i in range(1, rows):
        for j in range(1, cols):
            cost = 0 if s1[i - 1] == s2[j - 1] else 1
            dp[i][j] = min(
                dp[i - 1][j] + 1,    # Deletion
                dp[i][j - 1] + 1,    # Insertion
                dp[i - 1][j - 1] + cost  # Substitution
            )

    return dp[-1][-1]


# Example usage
if __name__ == "__main__":
    str1 = "kitten"
    str2 = "sitting"
    distance = levenshtein_distance(str1, str2)
    print(f"Levenshtein distance between '{str1}' and '{str2}': {distance}")
```

### markov chains

### PageRank

```python
from collections import defaultdict

def pagerank(graph, damping_factor=0.85, iterations=100):
    # Initialize PageRank values to 1/N
    nodes = list(graph.keys())
    N = len(nodes)
    ranks = {node: 1 / N for node in nodes}
    
    # Run the PageRank algorithm
    for _ in range(iterations):
        new_ranks = defaultdict(float)
        for node in nodes:
            # Distribute current rank to outbound links
            outbound_links = graph[node]
            if outbound_links:
                shared_rank = ranks[node] / len(outbound_links)
                for outbound in outbound_links:
                    new_ranks[outbound] += shared_rank
            # Handle dangling nodes (no outbound links)
            else:
                for other_node in nodes:
                    new_ranks[other_node] += ranks[node] / N

        # Apply the damping factor
        for node in nodes:
            new_ranks[node] = (1 - damping_factor) / N + damping_factor * new_ranks[node]
        
        ranks = new_ranks

    return ranks

# Example directed graph
# Each key is a node, and its value is a list of nodes it links to
example_graph = {
    "A": ["B", "C"],
    "B": ["C", "D"],
    "C": ["A"],
    "D": ["C"],
    "E": ["A", "D"],
}

# Run the toy PageRank implementation
result = pagerank(example_graph)

# Print the results
print("PageRank results:")
for page, rank in sorted(result.items(), key=lambda x: x[1], reverse=True):
    print(f"{page}: {rank:.4f}")
```

### telemetry vocab