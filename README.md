# ClocksOrCrocs
Clock and crocodile recognition and classification on images using deep learning.

[Read this in Russian][russian]

## Task

To build a classifier that separates images from the given dataset: a crocodile or a clock. To specify the accuracy obtained of the model.

## Solution

To classify images, the dataset given was divided into training, validation and test samples in the ratio of `0.7`:` 0.15`: `0.15`, respectively. See more in [`dataset_preparation.ipynb`][dataset_preparation].

Based on the pre-trained VGG16 neural network, a classifier was constructed using the ** Keras ** library with the ** Tensorflow ** backend.

The classifier was trained, the accuracy obtained on the test data is `87.5%`. To increase the accuracy of the classification, fine-tuning of the last layer of the pre-trained VGG16 neural network was made. Achieved classification accuracy: `93.75%` on the test data. See [`NN_Train.ipynb`][train] with a detailed step-by-step description.

As a demonstration, the trained neural network was tested on random images of clocks and crocodiles found on the Internet. See more in [`NN_Test.ipynb`][test].

## Conclusions and future plans

The classifier performed well on the test dataset and even was able to recognize some random images from the Internet. To improve the results, it is planned to train this classifier on a more complex pre-trained neural network (InceptionV3), to do more detailed fine-tuning. To speed up the training process, it is planned to make feature analysis, when the pre-trained neural network extracts the features, and then the classifier learns on the features separately, which significantly speeds up the learning process.

## Repository structure
- [clocks_crocodiles][c_c] = Initial dataset from the given archive.
- [data][data] - Processed dataset, sorted by train, validation and test folders.
- [redist][redist] - Archives with datasets, convenient for downloading.
- [trained_net][t_net] - Saved trained model for fast loading into your projects. No need to train anew.

## Installation and usage
To use, you must install all dependency packages for Python3. Use `pip3` to quickly and easily install everything you need.

`` `bash
pip3 install -r requirements.txt
`` `

To train the neural network and evaluate it's accuracy, use [NN_Train.ipynb][train].

To test the trained model on any images, use [NN_Test.ipynb][test]

### Google Colaboratory
This neural network was trained and tested in the Jupyter Notebook analogue - the Google cloud API with GPU acceleration `Google Colaboratory`. It is recommended to train the neural network there, since it is faster. In notebooks (`* .ipynb`) there are code cells for normal work with Google Colaboratory. If you work on a local PC, do not execute these cells.

## Acknowledgments
While training a neural network, the author studied too, having completed the course on [building deep neural networks using Python](https://www.asozykin.ru/courses/nnpython) from Andrei Sozykin. The author was sometimes inspired from the code shown in  example sections in the course materials.

<!-- Links -->
[repo]: https://github.com/yozh2/ClocksOrCrocs
[russian]: https://github.com/yozh2/ClocksOrCrocs/Readme.ru-RU.md
[dataset_preparation]: https://github.com/Yozh2/ClocksOrCrocs/blob/master/dataset_preparation.ipynb
[train]: https://github.com/Yozh2/ClocksOrCrocs/blob/master/NN_Train.ipynb
[test]: https://github.com/Yozh2/ClocksOrCrocs/blob/master/NN_Test.ipynb
[c_c]: https://github.com/Yozh2/ClocksOrCrocs/tree/master/clocks_crocodiles
[data]: https://github.com/Yozh2/ClocksOrCrocs/tree/master/data
[redist]: https://github.com/Yozh2/ClocksOrCrocs/tree/master/redist
[t_net]: https://github.com/Yozh2/ClocksOrCrocs/tree/master/trained_net
