Lab 12 Unsupervised Learning Exercises (Python)
================
Evan Woods
2024-01-09

## Applied

- **Question 7**: In this chapter, we mentioned the use of
  correlation-based distance and Euclidean distance as dissimilarity
  measures for hierarchical clustering. It turns out that these two
  measures are almost equivalent: if each observation has been centered
  to have mean zero and standard deviation one, and if we let r_ij
  denote the correlation between the ith and jth observations, then the
  quantity 1-r_ij is proportional to the squared Euclidean distance
  between the ith and jth observations. On the USArrests data, show that
  this proportionality holds.
  - **Answer**:
