.. tocvstoc documentation master file, created by
   sphinx-quickstart on Sun Jul 1 16:43:26 2024.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to TOC+ documentation!
====================================

**TOC+** is an extended version of the original TOC proposed by R. G. Ponitius. This tool is more informative. It is a numerically reliable tool to describe a binary classifier performance, data exploration and discover intricated probability statistical characteristics of any variable that is considered as a classifier. 

TOC+ Extends the Original TOC curve presenting the cumulative distribution function in compact manner. TOC+ is constructed in seconds [#f1]_ with all data and shows the sparsity of the rank domain.

.. image:: TOC.png
	:align: center

One of the most important innovations in this software is the implementation of findings regarding the direct relation with the Probability Density functions. 

+++++++++++++++++++++++++++
First Derivative of the TOC. The Histogram of frequencies
+++++++++++++++++++++++++++

The histogram of frequencies are plotted from the toc with::

   tocplus.plotHistograms()



By analyzing the first derivative of the TOC, we can elucidate the underlying Distribution Function for any classifier. The figure below shows the approximation to the first derivative of the main plot in the original rank and True Positive/False Negative domain.

This graph clearly illustrates for which rank values the classifier performs better than a random uniform classifier. The farther the blue line or point is from the red dotted line, the less random and more accurate the classifier is in correctly identifying data rank values.

Output Example.



.. image:: first_derivative.png
       :align: center


+++++++++++++++++++++++++++
Second Derivative of the TOC, the attractiveness analysis
+++++++++++++++++++++++++++

The Second derivative of the TOC. The Attractiveness analysis.


The Attractiveness analysis measures how the strength of attraction changes as we explore a rank value within its neighborhood. If the second derivative of the TOC, evaluated at any given rank, is greater than zero, it means that the variable reinforces attractiveness when we increase that value in its neighborhood. Conversely, if the second derivative is less than zero, the behavior is repelling.

The Second derivative for the attractiveness analysis of the variable is computed with::



The histogram of frequencies are plotted from the toc with::

   tocplus.plotAttractiveness()


Output Example.


.. image:: second_derivative.png
       :align: center


+++++++++++++++++++
TOC+ Quick Start
+++++++++++++++++++

Once TOC is installed.

Step 1. Import the tocp module::

   import tocplus as tocp

Step 2. Read or generate data::
   
   X = np.array([0,1,1,1,2,2,3,3,3,3,4,5,6,7,8,9])
   Y = np.array([1,1,1,1,0,1,0,0,0,0,1,0,1,0,1,0])

Step 3. Generate the TOC+ plot::

   T1 = tocp.TOC(rank = X, groundtruth = Y)
   T1.plot(filename='')

Output:
   
.. image:: tutorial_example.png
        :align: center


Textual description:

* The bottom axis tick labels represent the dataset size, indicating that we have 16 elements in this case.
* The upper axis tick labels show that the dataset ranges from 0 to 9 and illustrate the density of ranks within each interval. The greater the geometric separation between two consecutive ticks, the more ranks are contained within that interval.
* The left vertical axis represents the number of true positives in relation to the number of true positives and false negatives at the selected threshold, marked by one orange point.
* The 10 orange points correspond to the number of different ranks.
* The blue dotted line serves as a reference model for a uniform distribution, describing the total number of positive data elements with no specific preference for any rank value.

Regarding the Parallelogram Shape:

* The parallelogram denotes the feasible TOC space.
* The proportion of the parallelogram's base relative to the square's length indicates the balance or imbalance of the dataset. In this case, the parallelogram's base is more than half the length of the square's base, suggesting a slight imbalance with more negative-labeled data than positive-labeled data.   



.. rubric:: Footnotes
.. [#f1] TOC constructed with around 1 million datapoints in 5 seconds

Main Software Documentation
==========================

.. automodule:: src.tocplus
    :members:

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   module1
   module2


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
