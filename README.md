# manifold-learning
Lie Groups + AI + Image Processing

## incorporating symmetry into "deep dynamics models"
https://arxiv.org/pdf/2002.03061.pdf

## Basic Spline on lie groups
https://openreview.net/forum?id=H1gBhkBFDH
> this paper uses alot of technical abstraction to justify their machinery, but it was unclear what benefit
> they acheived other than proving that it is possible to construct CNNs that embed incoming data to a manifold
> specified by the design of the NN. They did not elaborate on performance or practical reasons. Overall I learned
> a lot by reading it, but it was more on the theoretical/abstract side than offering practical advice.
> tl;dr "you can make a convolution kernel 'lie group equivariant', which means that the manifold being constructed
> when data passes into that convolution layer is faithful to the structure of the desired lie group. This guarantee is acheived via the technical application of basis-splines, which is beyond my scope. They argue that using a fourier basis
> to decompose incoming data is insufficient to construct a manifold with the correct lie-group invariance properties. 
> so you must use a basis-spline. I am not going to write this off entirely, but I have found cleaner expositions on
> lie-group manifold learning, that were more helpful to my understanding. It's really just a matter of selecting a 
> different convolution matrix than the usual one used for gaussian blur or kernel density smoothing, and the b-splines
> allow for a general framework of convolution/blurring matrices that can accomodate different group structures. 
> my intuition is telling me that this paper would be difficult to implement in practice. 

## Co-equivariant NN: focusing equivariance on transformations co-occurring in data:
https://arxiv.org/pdf/1911.07849.pdf

## Equivarification
https://arxiv.org/pdf/1906.07172.pdf

# Electron imaging with NN: compressed sensing methods referenced here in citations and used #
https://www.nature.com/articles/s41586-019-1319-8
# symmetry group factorization for network structure (anatomy of worm neural cortex) #
https://www.nature.com/articles/s41467-019-12675-8 #
# lie operators for compressive sensing #
http://people.csail.mit.edu/chinmay/files/papers/icassp_cslie.pdf
# Universal encoding strategies! #
> pros: huge citation count + very much an optimization/IE approach
https://arxiv.org/pdf/math/0410542.pdf
> The sparse encoder is not unlike a cost matrix
> the signal reconstruction process
is similar to solving an assignment problem, if not identical.
> Unlike Deep Learning, there is a mathematically provable
guarantee that the true signal will be recovered. Good for basic science.
> challenge: finding the sparse encoder is a domain-specific problem, but this is essentially a convolution
 filter.
>Would be interesting to look into the possibility of a hybrid strategy, like learning the sparse encoder in one phase of training and then passing the rest of to a compressed sensing phase to ensure that the true signal is being recovered and not an artifact as is the case in most NNs. 

