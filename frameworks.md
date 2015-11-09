<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. Overview</a></li>
<li><a href="#sec-2">2. Frameworks</a>
<ul>
<li><a href="#sec-2-1">2.1. Theano</a>
<ul>
<li><a href="#sec-2-1-1">2.1.1. Advantages</a></li>
<li><a href="#sec-2-1-2">2.1.2. Disadvantages</a></li>
<li><a href="#sec-2-1-3">2.1.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-2">2.2. Keras</a>
<ul>
<li><a href="#sec-2-2-1">2.2.1. Advantages</a></li>
<li><a href="#sec-2-2-2">2.2.2. Disadvantages</a></li>
<li><a href="#sec-2-2-3">2.2.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-3">2.3. Lasagne</a>
<ul>
<li><a href="#sec-2-3-1">2.3.1. Advantages</a></li>
<li><a href="#sec-2-3-2">2.3.2. Disadvantages</a></li>
<li><a href="#sec-2-3-3">2.3.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-4">2.4. OpenDeep</a>
<ul>
<li><a href="#sec-2-4-1">2.4.1. Advantages</a></li>
<li><a href="#sec-2-4-2">2.4.2. Disadvantages</a></li>
<li><a href="#sec-2-4-3">2.4.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-5">2.5. Mariana</a>
<ul>
<li><a href="#sec-2-5-1">2.5.1. Advantages</a></li>
<li><a href="#sec-2-5-2">2.5.2. Disadvantages</a></li>
<li><a href="#sec-2-5-3">2.5.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-6">2.6. Pylearn2</a>
<ul>
<li><a href="#sec-2-6-1">2.6.1. Advantages</a></li>
<li><a href="#sec-2-6-2">2.6.2. Disadvantages</a></li>
<li><a href="#sec-2-6-3">2.6.3. Dependencies</a></li>
</ul>
</li>
<li><a href="#sec-2-7">2.7. Scikit-learn</a>
<ul>
<li><a href="#sec-2-7-1">2.7.1. Advantages</a></li>
<li><a href="#sec-2-7-2">2.7.2. Disadvantages</a></li>
<li><a href="#sec-2-7-3">2.7.3. Dependencies</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</div>

# Overview<a id="sec-1" name="sec-1"></a>

After looking through available options, I feel that we would be best served by
choosing a framework built on top of Theano. Theano itself is probably a little
too low-level for the amount of time we have and what we're hoping to
accomplish, but choosing a framework built on top will allow us to leverage its
advantages.

In terms of dependencies, most Python ML frameworks generally require NumPy,
SciPy, and a C and C++ compiler.

Some of the frameworks are packaged in PyPI, but generally must be built from
source with bleeding-edge versions of Theano (i.e. Clone and build from git
repo).

After spending some time investigating, I'd say that I liked Keras the best,
followed by Lasagne. OpenDeep seems like a good choice as well, but the library
might still be too immature to start using.

Mariana seems easy to use, but I'm not sure how expressive it can be, or how
well supported it is compared to other options.

Pylearn2 seems like it might be hard to use and extend, requiring its own
markup language to define the architecture, and becoming difficult if you need
to access internals.

Scikit-learn seems like a popular option, but doesn't have great support for
Neural Networks by itself, poor support for optimization, and is more of a
black box.

# Frameworks<a id="sec-2" name="sec-2"></a>

## Theano<a id="sec-2-1" name="sec-2-1"></a>

Library for defining, optimizing, and evaluating mathematical expressions
involving mutli-dimensional arrays.

License: Permissive license. See:
<http://deeplearning.net/software/theano/LICENSE.html>

Website:
<http://deeplearning.net/software/theano/index.html>
<https://github.com/theano/theano>

### Advantages<a id="sec-2-1-1" name="sec-2-1-1"></a>

-   Powerful primitives for defining mathematical computations.
-   Generates C code for fast execution.
-   Transparent use of GPU for optimization.

### Disadvantages<a id="sec-2-1-2" name="sec-2-1-2"></a>

-   Quite low level. Mostly a mathematical expressions library rather than an ML
    framework.
-   Might be hard to learn.
-   Only real GPU support uses CUDA, and therefore requires an NVIDIA GPU. OpenCL
    support is minimal.

### Dependencies<a id="sec-2-1-3" name="sec-2-1-3"></a>

1.  Required

    -   Python 2.6+ or Python 3.3+
    -   g++, python-dev
    -   NumPy >= 1.7.1
    -   SciPy >= 0.11
    -   Basic Linear Algebra Subprograms (BLAS) installation.

2.  Optional

    -   Sphinx >= 0.5.1, pygments (Documentation generation)
    -   NVIDIA CUDA drivers or libgpuarray (Required for GPU code
        generation/execution)

## Keras<a id="sec-2-2" name="sec-2-2"></a>

Theano-based Deep Learning library.

License: MIT

Website:
<http://keras.io/>
<https://github.com/fchollet/keras>

### Advantages<a id="sec-2-2-1" name="sec-2-2-1"></a>

-   Easy and fast prototyping.
-   Good documentation with lots of examples.
-   Many network architectures available, including CNNs and RNNs.

### Disadvantages<a id="sec-2-2-2" name="sec-2-2-2"></a>

-   Need to use bleeding-edge version.

### Dependencies<a id="sec-2-2-3" name="sec-2-2-3"></a>

1.  Required

    -   Theano and its dependencies. (Bleeding-edge)
    -   PyYAML
    -   HDF5 and h5py

2.  Optional

    -   cuDNN (If we use CNNs)

## Lasagne<a id="sec-2-3" name="sec-2-3"></a>

Lightweight library to build and train neural networks on top of Theano.

License: MIT

Website:
<https://github.com/Lasagne/Lasagne>
<http://lasagne.readthedocs.org/en/latest/index.html>

### Advantages<a id="sec-2-3-1" name="sec-2-3-1"></a>

-   Offers a variety of different NN architectures (FFNs, CNNs, RNNs with LSTM,
    or any combination).
-   Easy to use API for creating neural networks.

### Disadvantages<a id="sec-2-3-2" name="sec-2-3-2"></a>

-   Requires at least some knowledge of Theano.

### Dependencies<a id="sec-2-3-3" name="sec-2-3-3"></a>

1.  Required

    -   Python 2.7 or Python 3.4
    -   Theano and its dependencies (Tight version coupling).

## OpenDeep<a id="sec-2-4" name="sec-2-4"></a>

General purpose deep learning library built on Theano with a focus on
flexibility and modularity.

License: Apache 2

Website:
<http://www.opendeep.org/>
<https://github.com/vitruvianscience/opendeep>

### Advantages<a id="sec-2-4-1" name="sec-2-4-1"></a>

-   Easy to use. Good flexibility.
-   Easy to add new models and link them together.
-   Nice primitives for creating Neural Networks.

### Disadvantages<a id="sec-2-4-2" name="sec-2-4-2"></a>

-   In Alpha stages. Might be unstable or have some missing documentation.
-   Requires some knowledge of Theano for implementing models.

### Dependencies<a id="sec-2-4-3" name="sec-2-4-3"></a>

1.  Required

    -   Theano and its dependencies (Bleeding-edge)
    -   Pillow (PIL)

2.  Optional

    -   PyYAML (For YAML config files)
    -   Bokeh (Live charting/plotting during training)

## Mariana<a id="sec-2-5" name="sec-2-5"></a>

Machine learning library build on top of Theano that focuses on ease of use.

License: Apache 2

Website:
<http://bioinfo.iric.ca/~daoudat/Mariana/>
<https://github.com/tariqdaouda/Mariana>

### Advantages<a id="sec-2-5-1" name="sec-2-5-1"></a>

-   Ease of use. Intuitive Neural Network construction.
-   Extensible.

### Disadvantages<a id="sec-2-5-2" name="sec-2-5-2"></a>

-   Relatively newer project.
-   Must be built with bleeding-edge Theano.

### Dependencies<a id="sec-2-5-3" name="sec-2-5-3"></a>

1.  Required

    -   Theano and its dependencies.

## Pylearn2<a id="sec-2-6" name="sec-2-6"></a>

A machine learning research library.

License: 3-clause BSD

Website:
<http://deeplearning.net/software/pylearn2/>
<https://github.com/lisa-lab/pylearn2>

### Advantages<a id="sec-2-6-1" name="sec-2-6-1"></a>

-   Lots of machine learning primitives.
-   Uses a YAML-based markup language to describe Models, Training Algorithms,
    Cost Functions, and Datasets. No Python required.

### Disadvantages<a id="sec-2-6-2" name="sec-2-6-2"></a>

-   Large framework, so it will take some time to see what's available and to
    learn it.
-   Will have to learn the markup language, which might cause difficulty.
-   Using the library as a Python library is not as well supported.
-   Must be built from source (No PyPI package).

### Dependencies<a id="sec-2-6-3" name="sec-2-6-3"></a>

1.  Required

    -   PyYAML
    -   matplotlib for some plotting functionality.
    -   Theano and its dependencies. (Potentially needs bleeding-edge version)

## Scikit-learn<a id="sec-2-7" name="sec-2-7"></a>

Machine learning library build on top of SciPy.

License: 3-clause BSD

Website:
<http://scikit-learn.org/stable/>
<https://github.com/scikit-learn/scikit-learn>

### Advantages<a id="sec-2-7-1" name="sec-2-7-1"></a>

-   Many canonical machine learning algorithms.
-   Easy to use.

### Disadvantages<a id="sec-2-7-2" name="sec-2-7-2"></a>

-   Not a lot of Neural Network implementations. (RBMs only)
-   Only has well-established algorithms.
-   No GPU support.
-   Built as more of a black box.

### Dependencies<a id="sec-2-7-3" name="sec-2-7-3"></a>

1.  Required

    -   Python 2.6+ or Python 3.3+
    -   NumPy >= 1.6.1
    -   SciPy >= 0.9
    -   C or C++ compiler.
    -   C BLAS library.
