Responses to GAN Tutorial Questions
1. Normalization of the images is done in order to prevent biases in the training process. Putting the values between [-1, 1] keeps the range of values small, which prevents bigger values from dominating.
What is the meaning of the BUFFER_SIZE and BATCH_SIZE variables?
2. BUFFER_SIZE refers to the amount of images in the whole dataset, and BATCH_SIZE refers to the size of individual buckets of data generated at any time that will be trained by the model.
3. The generator starts with a 100-dimensional random noise vector, which a Dense layer transforms into a (7, 7, 256) shaped tensor. This tensor gets passed into a few Conv2DTranspose layers, which increase the size of the images and also reduce the number of channels/features. Leaky ReLU allows a small portion of negative neurons in, which helps the generator to keep learning. Batch normalization is used to reset activation layers, which keeps the values of the model consistent. Stride is used when dealing with how many pixels to read when looking at an image. For example, a stride of (2, 2) means the model will read 2 pixels at a time. This works more or less like a zoom/stretch for the images used on the layer.
Explain the dropout layer in the discriminator model.

The dropout layer in the discriminator model uses the dropout layer to force the model to identify patterns in the image itself instead of patterns generated from the original data (overfitting).
