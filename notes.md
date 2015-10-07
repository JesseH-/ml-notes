<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. Convolutional Neural Networks</a>
<ul>
<li><a href="#sec-1-1">1.1. Overview</a></li>
<li><a href="#sec-1-2">1.2. Technical Notes</a></li>
<li><a href="#sec-1-3">1.3. Papers</a>
<ul>
<li><a href="#sec-1-3-1">1.3.1. Convolutional Neural Networks for Acoustic Modeling of Raw Time Signal in LVCSR</a></li>
</ul>
</li>
<li><a href="#sec-1-4">1.4. Drawbacks</a></li>
<li><a href="#sec-1-5">1.5. See Also</a></li>
</ul>
</li>
</ul>
</div>
</div>

# Convolutional Neural Networks<a id="sec-1" name="sec-1"></a>

<https://en.wikipedia.org/wiki/Convolutional_neural_network>

## Overview<a id="sec-1-1" name="sec-1-1"></a>

CNNs are a type of feed-forward ANN where individual neurons are tiled in such
a way that they respond to overlapping regions. They consist of various
combinations of convolutional layers and fully connected layers.

CNNs do not rely on any prior knowledge, and the network itself is responsible
for learning its own filters (features).

## Technical Notes<a id="sec-1-2" name="sec-1-2"></a>

There are several different types of layer used in CNNs.

The parameters of the convolution kernels are learned as part of the
back-propagation algorithm. Their function is to extract different features from
the input. Each convolutional layer learns higher level features than the
previous ones. The first layers obtain low level features from which more
complicated ones are built up.

ReLU layers are also used. This is a layer of neurons that use the Rectified
Linear Units activation function, f(x) = max(0, x).

Pooling layers compute the max or average of a feature over a region in order to
reduce variance. This helps ensure that same result is obtained, even when
features have small translations.

Since we have many fully connected layers, CNNs are prone to overfitting. To
solve this problem, the dropout method is used. At each training stage, we
probabilistically drop nodes out of the net, and then train on the reduced
network. We then re-insert the nodes we removed with their original weights.

This method reduces overfitting in the network, and offers speed improvements
during training.

Finally, we may also introduce loss layers, with the loss function determined by
the task we are learning.

## Papers<a id="sec-1-3" name="sec-1-3"></a>

### Convolutional Neural Networks for Acoustic Modeling of Raw Time Signal in LVCSR<a id="sec-1-3-1" name="sec-1-3-1"></a>

Authors: P. Golik, Z. Tüske, R. Schlüter, and H. Ney.
Link: <https://www-i6.informatik.rwth-aachen.de/publications/download/974/Golik--2015.pdf>

This paper describes the application of CNNs to a LVCSR (Speech-to-text)
learning task. The interesting idea presented in the paper, is that they train
the CNN on the raw time signal data of the audio. This provides a parallel to
our own raw data.

1.  Background Reading

    -   **Band-pass filters:** <https://en.wikipedia.org/wiki/Band-pass_filter>
    -   **Acoustic Modeling with Deep Neural Networks Using Raw Time Signal for LVCSR:** <https://www-i6.informatik.rwth-aachen.de/publications/download/937/Tueske--2014.pdf>

## Drawbacks<a id="sec-1-4" name="sec-1-4"></a>

CNNs typically require a large amount of training data to avoid
over-fitting. This shouldn't be a problem for our application, as we have lots
of data available.

## See Also<a id="sec-1-5" name="sec-1-5"></a>

-   **Time delay neural networks:** <https://en.wikipedia.org/wiki/Time_delay_neural_network>
