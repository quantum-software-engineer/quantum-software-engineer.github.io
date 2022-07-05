---
layout: item
title:  "Probability Density and Basis Vectors"
updated:   2022-06-30 22:12:42 -0700
categories: refresher, probability, basis
# image: /images/kaka.jpg
# brief: A loud, social forest-dwelling parrot with North and South Island subspecies 
# status: Endangered
# nz_status: Endemic
# distribution: Forests and offshore islands throughout the country
---
If you have dabbled in ML, you might be familiar with the probability distribution vector. 

## Probability Density Vector
Consider a simple example, you build an ML model that identifies which fruit is present in an image. Each image contains 1 of 3 fruits, `apple, orange or banana`. Most models, be they DNNs or SVMs, will output a vector of probabilities for each image, call it `v`.
This vector is a numpy array of rank-1 with some additional constraints.
### Additional Constraints
- Length of the vector is equal to the number of classes, in this case `len(v) == 3`.
- The values of the vector correspond to the predicted probability of the class in an arbitrary but fixed order. Lets say the order we fix is `['apple', 'orange', 'banana']` and the output of the model is `[0.2, 0.3, 0.5]`. This means that the model predicts `0.2` as the probability of the image being of an apple, `0.3` is the probability of an orange, `0.5` is the probability of a banana. This definition gives us two more constraints.
  - The sum of the output vector is 1. `sum(v) == 1`. # Probabilities
  - All the element of the array much be non-negative. `v[i] >= 0 \forall i`.

In summary we have learnt -
1. `Probability density vector` - The array `[0.2, 0.3, 0.5]` captures everything we know about a specific image in a specific basis.
2. `Basis` - In this example, the fruit probability density vector of 1 particular image is `[0.2, 0.3, 0.5]`. A different image could have a different density vector, say `[0.4, 0.4, 0.2]`. The `basis` of all these vectors is `['apple', 'orange', 'banana']`. If we had chosen the basis to be `['orange', 'banana', 'apple']`, the probabilty density vector would also reorder to `[0.3, 0.5, 0.2]`, since the information contained in the image has not changed.
3. `Change of basis` - We could also measure the image in a completely new basis. For example, we could modify the basis to whether there is an apple in the image or not. In this case the new basis would be `['apple present', 'apple absent']`. Then the new probability density vector in this new basis would be `[0.2, 0.8]`.

Next, let's dive into [quantum][quantum-state].

[probability-density-vectors]: https://github.com/quantum-software-engineer.github.io/quantum-state
