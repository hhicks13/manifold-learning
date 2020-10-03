# manifold-learning
Lie Groups + AI + Image Processing

## incorporating symmetry into "deep dynamics models"
https://arxiv.org/pdf/2002.03061.pdf

## Basic Spline on lie groups
https://openreview.net/forum?id=H1gBhkBFDH
> this paper uses alot of technical abstraction to justify their machinery, but it was unclear what benefit
> they acheived other than proving that it is possible to construct CNNs that embed incoming data to a manifold
> such that the computed representation of the data is invariant under the action of any desired lie group.
> For example if you specify the lie group of rotation matrices, then your new embedded representation will
> be the convolution of that image with all its rotated images (these correspond to neighbors in the lie-manifold)
> In a normal CNN the image is convolved with its neighbors, weighted by proximity up to linear transpose, so
> the further away a pixel, the *less* weight it will have in determining the new value of the pixel when it is mapped
> to the next layer. In manifold learning, the concept of a neighborhood is determined by the structure of the
> lie group which generates the manifold and proximity is quantified up to the action of this group. Take
>  the rotation group for example acting on some image X being fed to the CNN :two subregions of X will be convolved with another if they belong to the same orbit under rotation of X, but
> may not be convolved at all if they are neighboring pixels as translational proximity is not the group action being considered. This totally depends on the structure of the lie group and the manifold it generates.
> Comments:
> They did not elaborate on performance or practical reasons. Overall I learned
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

