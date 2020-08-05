# Siamese-Network-Deep-Learning

Siamese Networks are a class of neural networks capable of one-shot learning.
A Siamese neural network (sometimes called a twin neural network) is an artificial neural network that uses the same weights while working in tandem on two different input vectors to compute comparable output vectors.

Let us assume we have a company of 1000 employees. We decide to implement a facial recognition system to record the attendance of your employees. If we were to use traditional neural networks, we will have to face two main problems. First one would be the dataset. It would be nearly impossible to assemble a huge collection of dataset from each of our employees, we would end up with a maximum of 5 photos of each of our employees. But a traditional CNN(Convolutional Neural Networks) won’t be able to learn features with such small collection. We’ll also end up with 1000 output classes. Let’s consider that somehow we got a huge dataset from each of our employees and we trained a really good CNN model. What happens when a new employee joins our organization? How can we include the person into our facial recognition system? All these shortcomings can be overcome using siamese networks. In this post, we will experiment with one-shot learning using Siamese networks that concentrate on the difference rather than feature matching.
Rather than using huge data for each of the class, we calculate the similarity scores between images of different classes. The input to this network will be two images either belonging to the same class or different class. The output will be a floating-point number ranging between 0 and 1, wherein 1 indicates that that the two images are of the same class and 0 indicating they are from different ones. Let me start by explaining how it is different from image classification using CNN Architectures.

## Architecture

In case of a CNN model, you have a series of convolutional and pooling layers followed by some dense layers and an output layer probably with a softmax function. The convolutional layers here are responsible for feature extraction from the image, whereas the softmax layer is responsible for providing a range of probability for every class. We then decide the class of the image with the neuron that has the highest probability value.

With siamese networks, it has a similar constitution of convolutional and pooling layers except we don’t have a softmax layer. So, we stop with the dense layers. As explained before since the network has two images as inputs, we will end up with two dense layers. Now we calculate the difference of these two layers and output the result to a single neuron with sigmoid activation function(0 to 1). Thus the training data to this network must be structured in such a way that there is a list consisting of two images and a variable either 0 or 1.

The below diagram shows the structure of siamese network.
![1_eMehqF0SloigS1tppMEiEw](https://user-images.githubusercontent.com/50628520/89387985-0c651600-d723-11ea-8044-01268305fba0.png)

There is only one network and both the images are passed through the same network. It’s just that there are two inputs. Thus, both the inputs will be passing through the same weight matrix from the convolution and dense layers.

But how do siamese networks work? Siamese networks basically consist of two symmetrical neural networks both sharing the same weights and architecture and both joined together at the end using some energy function, E. The objective of our siamese network is to learn whether two input values are similar or dissimilar. Let’s say we have two images, X1 and X2, and we want to learn whether the two images are similar or dissimilar.

Siamese networks are not only used for face recognition, but they are also used extensively in applications where we don’t have many data points and tasks where we need to learn similarity between two inputs. The applications of siamese networks include signature verification, similar question retrieval, object tracking, and more.

![0_0rWCqe27kKdp2y73](https://user-images.githubusercontent.com/50628520/89388384-ac22a400-d723-11ea-920e-746d4cd052d9.png)
