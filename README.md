# MultiClass Classification & Transfer Learning

This notebook contains an application of Multiclass Classification of images, using the concept of Transfer Learning.

### Transfer Learning:
Transfer learning is a machine learning technique where a model trained on one task is re-purposed on a second related task. We use an existing model that's trained on far more data, and use the features that that model learned, to help with our predictions.
We can lock the layers of the pretrained model instead of retraining them on our data, and have those just extract the features from our data using the convolutions that they've already learned. We will then add our own DNN at the bottom of these, which we can retrain to our data.

### Dataset Used:
**Fruits 360** - A dataset with 90483 images of 131 fruits and vegetables

Link: https://www.kaggle.com/moltean/fruits/download

### Pre-trained Model Used:
We use the **Inception Model** which has been pre-trained on a dataset from ImageNet, which has 1.4 million images in a 1000 different classes.

Link: https://storage.googleapis.com/mledu-datasets/inception_v3_weights_tf_dim_ordering_tf_kernels_notop.h5

Steps performed:

1. Load the pre-trained Inception Model Weights.
2. Freeze all the layers of the Inception Model to make them untrainable.
3. Select an appropriate layer from the pre-trained model as the last layer, after which we will stack it upon our own DNN.
4. Load Training and Validation data from directory using ImageDataGenerator.
5. Fit the Model on trining data.
6. Visualize Training vs Validation accuracy and loss.  