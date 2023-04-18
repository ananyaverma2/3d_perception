# 3D object classification

This repository contains the code to train and test the PointNet model on the ModelNet10 dataset. The ain idea of the project is to perform 3D object classification using 3D CAD models i.e. ModelNet dataset.

## ModelNet10 Dataset
The ModelNet10 dataset is a collection of 3D CAD models that are classified into 10 categories, including chairs, tables, desks, and other furniture items. The dataset comprises a total of 4,899 CAD models, which are split into training and testing sets.

The dataset is available for download at https://modelnet.cs.princeton.edu/. 

## PointNet Model
The PointNet model is a deep neural network designed for processing 3D point clouds. It has been used in various tasks such as object classification, segmentation, and detection.

This repository includes the implementation of PointNet in Keras (built on tensorflow). The model is trained on the ModelNet10 dataset to classify CAD models into one of the 10 categories.

## Methodology

* Import necessary libraries, including TensorFlow, Keras, trimesh, and numpy.
* Load a dataset of 3D object meshes. This code uses the trimesh library to read a 3D mesh file in OBJ format and then samples 2048 points from the surface of the mesh using the sample.sample_surface function. The sampled points are then stored in a numpy array (parse the data), and add noise to the data (data augmentation).
Sample 2048 points from the mesh and use them to generate a numpy array.
* Build the PointNet model using a combination of multi-layer perceptrons and max-pooling operations to extract features from individual points and a symmetric function to aggregate these features into a global feature vector.
* Compile and train the PointNet model on the dataset.
* Visualize the predictions of the trained model.
* Save the model

## Results
The model was trained for 25 epochs with a batch size of 32. The sparse_categorical_accuracy was 83.69% and val_sparse_categorical_accuracy was 79.30%.
