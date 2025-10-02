#### Why is the quantity of data important (not ignoring quality)
- The ability to generalise
	- A larger dataset gives a more significant representation of underlying patterns and variability in the data which lets the model generalise better
	- Also helps avoid overfitting
- Allows for more complex models
	- More data lets us train more complex models with a larger number of parameters without overfitting
	- Complex models (like deep neural networks) often need large amounts of data to learn effectively.
- Robustness to noise and outliers
	- More data means the effects of noise or erronous pounts are less significant.
	- The model can also learn to identify and ignore these outliers!

#### An example of classification! Spam detection:
- Learn a mapping from input to output f: X -> Y
- X: emails, Y: {spam, notSpam}

#### Our intuition on how we can detect spam:
- Think about the word usage! Spam emails likely have lots of words like "money", "free" and "bank account" whereas regular emails likely have a more spread out word usage
-  Here we can assign "weights" to each likely spam word, and multiply it by how often it shows up and it will spit out a decimal >0, if it's abnormally high it's probably spam! 
- We can pick our "words" using previous known spam emails
- This isnt a confidence guarantee however

#### Classification
- Consider something like chess, each position is a class (it's classification because there isnt a smooth transition between 2 classes) 
	- AKA you cant be halfway between 2 squares

#### Types of learning:
- Supervised learning
	- Training data includes desired output (like a pic of a cat and the word "cat")
	- Training data is provided in pairs (x,y) where the goal is to predict an output y from input x
	- Output y for each input x is the "supervision" given to the algorithm
	- Often obtained by the manual "annotation" of input X
		- This is costly to do
	- 2 Main types of supervised learning
		- Classification (discrete numbers, think ints) -> each number is mapped to a label
		- Regression (continuous numbers, think reals)

- Unsupervised learning
	- Training data does NOT  include desired outputs

- Weakly / semi supervised learning
	- Training data includes only a few desired outputs

- Reinforcement learning
	- Rewards from a sequence of actions
	- E.G:
		- Theres only one supervised signal at the end of chess (+1 if win, -1 if loss)
		- You need to make a move at ever step
		- Reinforcement learning deals with "credit assignment" -> a function designed to provide reward based on how close to a desirable output it is
		- It aims to maximise its cumulative reward

#### Important Machine Learning Application Areas: 
*(note this is a very crude example)*
- Supervised Learnin
	- X -> Classification -> Y (Discrete)
	- X -> Regression -> Y (Continuous)

- Unsupervised Learning
	- X -> Clustering -> Y  (Discrete)
	- X -> Dimensionality Reduction -> Y (Continuous)

#### Image classification, as an example, is not easy because you must consider:
- Viewpoint Variation
	- AKA things dont look the same from different viewpoints
- Scale Variation
	- 2 of the same thing may be different sizes
- Deformation
	- What if its positioned weirdly? 
- Occlusion
	- What if some of it is hidden?
- Background clutter
	- What if you cant differentiate the foreground and background easily? 
- Illumination conditions
	- What if the different lighting conditions make things look drastically different?
- Intra-class variation
	- What if many items in the same "classification" look wildly different? 

#### Regression (supervised)
- Similar to classification, but the output Y has the form of 1+ real numbers
- The goal is to predict for an input x, an output f(x) that is close to the true Y
- Aka learn a continuous function
- 2 types of regression [Think line of best fit]
	- Linear regression (A straight line)
	- Nonlinear regression (Not a straight line)

#### Clustering (unsupervised)
- Grouping together SIMILAR items
	- Finding group structure in data
	- Data in one cluster is to be considered similar to others in the same cluster
	- Data in different clusters are to be considered dissimilar
	- To define similarity however is not always trivial
- 2 types of clustering: 
	- Flat (K-known or K-means)
		- Splits each cluster into its own distinct, non overlapping thing
	- Hierarchical (Tree structure)
		- Splits each cluster into subclusters also, which can be represented with a tree-like diagram.

#### Dimensionality Reduction (Unsupervised)
- Finding a lower dimensional representation of data
	- Useful for compression, visualisation or noise reduction
	- Unlike regression, the target values are not given, thus its unsupervised