# Image classification of Google Images using Fastai v1
## How to quickly train an image classifier using images downloaded from the web

![Google Animal Images](images/animal_images.png "Google Animal Images")

## Credit

This notebook is provided by Jeremy Howard's fastai [deep learning course](http://course.fast.ai/ "Fastai"). I've applied it to a new set of images downloaded from the web.

## Packages

This notebook uses the newly released fastai v1 library, which contains many useful data loading and computer vision functions.

## Motivation

If you want to train your own computer vision model, how do you go about getting all of the images you need and placing them in a folder structure that's expected by the model? This notebook walks through a clever way of grabbing the URL paths from Google Images and saving them as a .txt file. For this sample project, I downloaded about 300 images each of kangaroos, panda bears, and koalas. Then I read each category of image into its own folder and trained ResNet34 on the images.

## Files

The main file is **download_images-cpm.ipynb**, which walks through grabbing the URL paths from Google Images and then using ResNet34 to classify the images.

## Results

### How well did ResNet34 do on 3 classes of images?

![Confusion Matrix](images/confusion_matrix.png "Confusion Matrix")

The model only made 6 mistakes!

### Let's look at the 6 mistakes

![6 Mistakes](images/top_losses.png "6 Mistakes")

Five of the six mistakes are much different than typical nature images. Four of the images are cartoons or dolls. In the image with the tree, the leaves almost completely obscure the animal. These are all artifacts of doing a bulk pull from Google Images. If we wanted, we could easily clean up the data set to focus only on animals in the wild.
