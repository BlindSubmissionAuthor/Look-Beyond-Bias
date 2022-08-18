Benchmark datasets for the paper "Look Beyond Bias with Entropic Adversarial Data Augmentation", published in ICPR 2022.

You can download the dataset at the following link: https://drive.google.com/file/d/1fndaXty3r_cpgySOSmUFH1abSoahoZkg/view 

### File Format ###

The file is a pickled dictionary with the following keys: 'train', 'val', 'test'. The value for each key is also a dictionary with the keys 'images' and 'labels', corresponding to, respectively, the images and the labels of the corresponding dataset. Inside these sub-dictionaries, images is a tensor of dimension N x 3 x 32 x 32, where N is the number of images in the dataset, and labels is a tensor of length N containing the classes from 0 to 9. The range value of the images is [-1, 1]. The file can be read with the torch.load() function.

### Example for the located CIFAR-10 dataset ###

The train (train) dataset contains CIFAR-10 images that were strongly biased by the addition of a patch in a class-correlated position. It is made from the original CIFAR-10 training set.

![alt text](https://github.com/liris-tduboudin/Look-Beyond-Bias/blob/main/image_0.png?raw=true)

The validation (val) dataset contains CIFAR-10 images with the same patch bias but coming from the original CIFAR-10 test set.

![alt text](https://github.com/liris-tduboudin/Look-Beyond-Bias/blob/main/image_1.png?raw=true)

The test (test) dataset contains CIFAR-10 images from the original test set. The added shortcut (or bias) is the average of all the patches (resulting in diffuse patches in all positions).

![alt text](https://github.com/liris-tduboudin/Look-Beyond-Bias/blob/main/image_2.png?raw=true)

### Misc ###

The colors used for the training set (for both the colored MNIST and CIFAR-10) :

{0:(255, 127, 127),
1:(0, 127, 127),
2:(127, 255, 127),
3:(127, 0, 127),
4:(127, 127, 255),
5:(127, 127, 0),
6:(0, 255, 255),
7:(255, 0, 0),
8:(255, 0, 255),
9:(0, 255, 0)}
