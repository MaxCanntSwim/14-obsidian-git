- Convolutional Neural Networks
- Recurrent Neural Networks
___
# CNN
When used on RGB images, the MLP:
- **Scales badly** (increasing the dimensions of the images leads to a quadratic increase of inputs)
- **Ignores the spatial structure** (pixels in opposite parts of the image are connected in the same way as adjacent pixels)
- **Cannot handle translation** (if the network is shown a dog always in a specific corner of the image, it won't recognize it when shown in another part of the image)
## The convolution filter
![[Screenshot 2024-04-13 at 15.56.03.jpg]]
We perform element-wise multiplication between the elements of the filter and the intensity values of the image (e.g., in the case of RGB, the color intensity between 0 and 255) and sum the result, scanning the filter over the whole image.


![[Screenshot 2024-04-13 at 16.00.38.jpg]]
At every layer, an array of multidimensional filters are applied, to reduce the width and height of the feature map while increasing the depth. After the last layer of filters, the feature map is flattened to a 1-dimensional array which is used as input to a fully-connected MLP, whose weights are also learned during training. The output of the MLP is then compared to the desired output.