# Deep Learning - CNN Architecture Exercise Related to Computer Vision

__Introduction:__

Deep neural networks have tremendous potential to learn complex non-linear functions, patterns, and representations. This includes real-world applications like image categorization and classification and the very popular concept of image artistic style transfer. Computer vision is all about the art and science of making machines understand high-level useful patterns and representations from images and videos so that it would be able to make intelligent decisions similar to what a human would do upon observing its surroundings. 

Convolutional neural networks or CNNs are extensively used for automated feature extraction in images.  In fact, CNNs are similar to the general deep neural networks, but with explicit assumption of input being a data set where which the location of a feature is relevant can be attempted via CNNs  like image, but not limited to then. Others examples are:
- ***Time series***: your data is well ordered. A time series problem would make a 1–d convolution the right choice.
- ***Weather***: Build a map of current weather conditions (location-based values, but not actual images). Add another dimension to it for the previous weather maps (in order) and you have a 4–d convolution problem to predict the weather.

This notebook explore convolutional neural networks through the task of image classification using publicly dataset  CIFAR-10. We will utilize our understanding of CNNs to then take on the task of style transfer and understand how neural networks can be used to understand high-level features. Through this notebook, we cover the following topics:
- Image classification use CNNs from scratch
- Transfer learning: image classification using pretrained models
- Neural style transfer using CNNs

For an in-depth understanding of CNNs applied for visual recognition take look on the [Stanford course material](http://cs231n.github.io/convolutional-networks). Let us see a little brief overview of its key concepts:
- ***A CNN is made up of Layers***: Every Layer has a simple API: It transforms an input 3D volume to an output 3D volume with some differentiable function that may or may not have parameters. the main layers are:
    - ***Convolutional Layer***: Is a set of slides or convolves learnable filters, also known as kernels or convolution matrix, to help capture spatial features. These cover the width, height and the full depth (color range) of the image. During the forward pass, we slide the filter across the width and the height of the image while computing the dot product between the filter attributes and the input at any position. The output is a two-dimensional activation map from each filter, which are then stacked to get the final output.
    - ***Pooling Layer***: These are basically down-sampling layers used to reduce spatial size and number of parameters by apply functions such as max, average, L2-norm, and so on. These layers also help in controlling overfitting.  These layers are insert in between conv layers or in the end of a sequence of them.
    - ***Fully Connected Layer***: This layer helps perform the tasks of classification. It is similar to fully connected layers in general neural networks. These have full connections to all neurons in the previous layer and can followed by a Dropout to help to reduce overfit.<p>
- ***Parameter Sharing***: Conv layers use same set of weights across the filters thus reducing the overall number of parameters required.

CNNs have gone through tremendous research and advancements have led to more complex and power architectures, like VGG-16, VGG-19, Inception V3, and many models that are more interesting.

Let's start our studies:
![image](https://github.com/Madhavan11601828/Deep-Learning---CNN-Exercise-Related-to-Computer-Vision/blob/main/ProcessOfconvnet.jpeg)
