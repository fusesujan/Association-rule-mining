# Association Rule Mining

Association Rule Mining is a rule-based machine learning method to discover how items are associated to each other. Stores use them to figure out products that are bought together, this way they can provide different offers to the different customers e.g, buy one get one free. Earlier, recommendation systems like Amazon, Netflix used them. In this notebook, we will go through Apriori type of Association Rule Learning model.

Its primary goal is to discover interesting and meaningful relationships, associations, or patterns within large datasets. Specifically, association rule mining focuses on identifying rules that describe the co-occurrence or dependency between different items in a dataset.

### Advantages

Association rule mining helps discover hidden and meaningful patterns, relationships, and dependencies in large datasets. The discovered association rules can be used for decision-making and strategy development. Some advanced algorithms, like FP-growth, are efficient and scalable, making it feasible to apply association rule mining to large datasets.  
**BUT**  
Association rule mining is sensitive to data quality and noise. Effective application of association rule mining often requires domain knowledge. Lack of Causality and possible rules grows exponentially are some serious issue in association rule mining.

**Some key terminologies that should be understood in association rule mining**:

**Support**: This measures the frequency or occurrence of a particular itemset (combination of items) in the dataset. It indicates how frequently a rule is applicable. High support values suggest that the rule is applicable to a significant portion of the dataset.

`Support(X) = (Number of transactions containing X) / (Total number of transactions)`

**Confidence**: Confidence measures the strength of the association between items in a rule. It is the probability that an item Y occurs in the dataset when item X is present. High confidence values indicate a strong relationship between items.

`Confidence(X => Y) = (Number of transactions containing X and Y) / (Number of transactions containing X)`

**Lift**: Lift helps in understanding how much more likely it is for the items in the rule to appear together compared to their individual occurrence rates. Lift is particularly useful for determining the practical importance of an association rule. The lift value is calculated as the ratio of the observed support of the rule to the expected support of the rule under statistical independence assumptions.

`Lift = (Support of Rule) / (Support of Item A * Support of Item B)`

Two well-known algorithms for association rule mining are the Apriori algorithm and the FP-growth algorithm:

## Apriori algorithm

The algorithm is based on the concept of "apriori property," which means that if an itemset is frequent (i.e., it meets a minimum support threshold), then all of its subsets must also be frequent. '  
Apriori algorithm works as:

- Set a minimum support and confidence.
- Take all the subsets in transactions having higher support than minimum support.
- Take all the rules of these subsets having higher confidence than minimum confidence.
- Sort the rules by decreasing lift.

## FP-growth

FP-growth uses a different approach that eliminates the need to generate and prune candidate itemsets. Instead, it builds a data structure known as the FP-tree, which represents frequent patterns in a compact and efficient way.

FP-growth algorithm works as:

- Constructs an FP-tree by scanning the dataset once and counting the support of each item.
- Mines frequent itemsets directly from the FP-tree.
- The algorithm recursively explores the tree to generate frequent itemsets and association rules.

Both Apriori and FP-growth are widely used in practice for association rule mining, and the choice between them depends on the specific characteristics of the dataset and the computational resources available. Apriori is more intuitive and easier to implement, while FP-growth is often preferred for its efficiency, especially when working with large and high-dimensional datasets.
