---
layout: post
title:  "Refresher - Python Data Structures"
date:   2022-06-29 20:29:42 -0700
categories: refresher python
---
Before we can do any computing, we have to create new data
structures which make it easy to represent quantum states and gates in Python.

Python has 4 basic data primitives - `int, float, bool and string`.
Python also has 4 inbuilt data structures - `list, tuple, dict and set`.
More complex data structures can be built upon these basic data structures.

## Numpy Array Data Structure
As a demonstration, I will consider a data structure that most readers shoudl be very familiar with, the numpy ndarray, and inspect how it can be constructed using lists with some additional constraints, properties and operations. (A numpy array has more constraints, properties and operations than the examples mentioned below.)

### Construction
A numpy array of rank 0 is a python data primitive. A numpy array of rank 1 is a list of numpy arrays of rank 0. A numpy array of rank n is a list of numpy arrays of rank n-1.
<!-- ``` -->
{% highlight python %}
array_0 = 3.
array_1 = [3., 4., 5.]
array_2 = [[3., 4., 5.], [4., 5., 6.], [1., 5., 9.]]
{% endhighlight %}
<!-- ``` -->
### Constraints
All the nested numpy arrays of the same rank have the same length.
<!-- ``` -->
{% highlight python %}
array_2 = [[3., 4., 5.], [4., 5., 6.], [1., 5., 9.]]
len(array_2[0]) == len(array_2[1]) == len(array_2[2]) == 3
{% endhighlight %}
<!-- ``` -->
### Properties
Numpy ndarrays have a `shape` property, which is a tuple whose `\i^{th}` element is the length of the rank-i list.
<!-- ``` -->
{% highlight python %}
array_2.shape = (3, 3)
{% endhighlight %}
<!-- ``` -->
### Operations
The '+' operation is redefined for numpy ndarrays. Only ndarrays of equal shape can be added, resulting in a new ndarray of the same shape whose elements are elementwise sums of the two original ndarrays.
<!-- ``` -->
{% highlight python %}
array_1 + array_2  ## Raises exception.
[3., 4., 5.] + [4., 5., 6.] = [7., 9., 11.]
{% endhighlight %}
<!-- ``` -->

Thus a new data structure can be constructed from python primitives and data structure that have its own set of constraints, properties and operations.

Next let's jump into the [land of probability][probability-density-vectors].

[probability-density-vectors]: https://github.com/quantum-software-engineer.github.io/probability-density-vectors
