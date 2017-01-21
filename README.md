# IMAP
IMAP: An Iterative Method for Aligning Protein-Protein Interaction Networks

## Abstract
Biological network alignment benefits the community by providing regions of topological and functional similarity between different species. Due to its importance, researchers made plenty attempts in this direction. However, most existing network aligners follow heuristic methods, which first compute similarity between nodes and then find a high-scoring alignment, capturing only static informations that based purely on the original isolated networks. Instead, we proposed an iterative method IMAP, which starts from an imperfect seed alignment generated with any aligner and then iteratively improves it until convergence. With this framework, we are able to capture dynamic informations, informations that depend on current alignment. Furthermore, we model the task with classification model, thus heuristic scoring functions are no longer needed. We also extend the framework to start from multiple seed alignments for further improvement. Experiments using both real and synthetic data indicate that our framework IMAP can successfully improve performance of existing network aligners significantly.

## The Framework
The IMAP framework follows the idea that an imperfect alignment actually contains rich information for further alignment. For example, it is easy to align a node if its neighbors are already aligned. This is also true even for alignments with rather low quality or low coverage, e.g. in GRAAL the authors take advantage of seed alignment with only one pair of nodes by grouping the nodes by distances to the seed pair and aligning them within each group.

In our framework, we extract the hidden information in seed alignment by generating the followings based on the seed alignment in each iteration: (1) candidate pairs, (2) pairwise training data and (3) pairwise features. Using these, we then learn a classification model indicating whether two nodes should be aligned. Applying it over the candidate set we generate pairwise likelihood for each candidate pair. Then we employ pairwise-score-based aligning algorithms to generate the improved alignment, which will be used as the seed alignment for next iteration. We show the overview in the following figure.

![](http://apex.sjtu.edu.cn/public/files/projects/20161022/bappin.png)

## Results

![](http://apex.sjtu.edu.cn/public/files/projects/20161022/result-A.png)

![](http://apex.sjtu.edu.cn/public/files/projects/20161022/result-B.png)

# Contacts
[Xuezhi Cao](http://apex.sjtu.edu.cn/members/cxz "Xuezhi Cao")
