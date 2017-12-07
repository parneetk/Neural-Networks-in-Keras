# Neural-Networks-in-Keras
Keras is a python library for neural networks and provides a high-level inteface to Theano or Tensorflow libraries. The examples in this github repository assume that you are familiar with the theory of the neural networks. To learn more about the neural networks, you can refer the resources below.

## Installation Instructions
Installation instructions for Keras (includes links to Theano and Tensorflow installaion):
https://keras.io/#installation

To Use GPU, install CUDA: https://developer.nvidia.com/cuda-downloads

To resolve common installation issues, refer the [README](https://github.com/lgraesser/Neural-Networks-Workshop-Materials-WiMLDS) on Laura Graesser's Github repository.


## Using Tensorflow as backend
Keras uses Tensorflow by default. 
Check the contents of *~/.keras/keras.json*:
<pre><code>
{
    "image_dim_ordering": "tf",
    "epsilon": 1e-07,
    "floatx": "float32",
    "backend": "tensorflow"
}
</pre></code>


## Using Theano as backend
Edit the contents of *~/.keras/keras.json*:
<pre><code>
{
    "image_dim_ordering": "th", 
    "epsilon": 1e-07, 
    "floatx": "float32", 
    "backend": "theano"
}
</pre></code>

## Check the Backend being used
<pre><code>
from keras import backend as K
print K.backend()
print K.image_dim_ordering()
## Set image dimesnion order for Tensorflow, so that no modifications are required in the code
if K.backend() =='tensorflow':
    K.set_image_dim_ordering("th")
    print K.image_dim_ordering()
</pre></code>

## Using GPU
For tensorflow, GPU is used by default.
To use GPU for Theano, add this code in the beggining of the file:
<pre><code>
import os
os.environ["THEANO_FLAGS"] = "mode=FAST_RUN, device=gpu, floatX=float32"
</pre></code>

## Resources:
### Books:
* [Neural Networks and Deep Learning](http://neuralnetworksanddeeplearning.com/) by Michael Nielsen
* [Deep Learning](http://www.deeplearningbook.org/) by Ian Goodfellow, Yoshua Bengio and Aaron Courville

### Video Lectures:
* [Neural Networks for Machine Learning by Geoffrey Hinton](https://www.coursera.org/learn/neural-networks)
* [Stanford Course CS231n: Video Lectures (Winter 2016)](https://www.youtube.com/playlist?list=PLkt2uSq6rBVctENoVBg1TpCC7OQi31AlC)
* [Udacity's Deep Learning Course](https://www.udacity.com/course/deep-learning--ud730)
* [Hugo Larochelle's lectures](https://www.youtube.com/playlist?list=PL6Xpj9I5qXYEcOhn7TqghAJ6NAPrNmUBH)
* Videos from [Bay Area Deep Learning School](http://www.bayareadlschool.org/): [Day1](https://www.youtube.com/watch?v=eyovmAtoUx0), [Day2](https://www.youtube.com/watch?v=9dXiAecyJrY)
* [Machine Learning course by Nando de Freitas](https://www.cs.ox.ac.uk/people/nando.defreitas/machinelearning/)

### Blogs:
* [Article on Deep Learning](https://www.cs.nyu.edu/mishra/COURSES/15.Summer/lecun2015.pdf) by Yann LeCun, Yoshua Bengio and Geoffrey Hinton
* Christopher Olah's [blog](http://colah.github.io/)
* [Stanford Course CS231n: Course webpage](https://cs231n.github.io/) by Andrej Karpathy 
* [Overview of Gradient Descent Optimization Algorithms](http://sebastianruder.com/optimizing-gradient-descent/) by Sebastian Ruder

## Acknowledgements
Thank you to [Laura Graesser](https://learningmachinelearning.org/) for her [Neural Networks workshop](https://github.com/lgraesser/Neural-Networks-Workshop-Materials-WiMLDS) and [WiMDS](https://www.meetup.com/NYC-Women-in-Machine-Learning-Data-Science/events/235881587/) for organizing it.
