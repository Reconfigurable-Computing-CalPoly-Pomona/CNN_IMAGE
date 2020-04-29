# CNN_IMAGE
## Team Members:

1.	Andres Colon: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

2.	Jimmy Ngo: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

3.	Johnny Rivera: Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

4.	Tyler Solarz:  Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

## Supervising Professor:

**Mohamed El-Hadedy**: Assistant Professor, Electrical and Computer Engineering department, College of Engineering, California State Polytechnic University, Pomona.

## What is Convolution Neural Network(CNN)?

### Abstract
Convolution Neural Network, or CNN, is a type of machine learning. What it does is it takes a basic dataset, whether it be images, text, video, etc and it takes that dataset and trains itself to notice the items. Next, is that once it finishes learning all the data, we can then feed it an image and it will tell us how accurate it depicts after CNN recognizes it.   

### How CNN image classification works.

![](/Report/Read.md_figures/classification.jpg)
Figure 1: Demonstration for the CNN.

Image classification works by inputting an image into the program. The image applied to many different filters to create a map of the features. The image is then applied to a ReLu function to increase the non-linearity. Then it applied to a pooling layer to the mapped features. The pooled images are then flattened into a long vector. The inputs of that vector are fully connected to an artificial neural network. The final fully connected layer provides the “voting” of the classes that we’re after. This cycle repeats until we have a well-defined neural network with trained weights and feature detectors.

### Convolution
Convolution is a process in which a small matrix of numbers (filter) is passed over an image and transformed based on the values determined by the filter. Feature map values are calculated using the formula in the figure below, where the input image is denoted by f and the filter by h, meanwhile rows are m and columns are n.

![](/Report/Read.md_figures/featureExtraction.PNG)

Figure 2: Mathematical equation of the feature maps.

Once the filter is placed over a selected pixel, each value is multiplied in pairs corresponding to the values from the image. Lastly, everything is summed up and the result is placed in the output feature map. 

## Tutorial
### Setup Desktop/Laptop Virtual Environment
1. To access and keep our files from Jupyter Notebook we need to download Anaconda Navigator and create a virtual environment
   - Download link: https://www.anaconda.com/products/individual 
2. Once installed you will need to open the anaconda command prompt and enter the following commands in order to setup environment and install necessary libraries:
   - ```conda create --name PythonCPU```
     - You can use any name other than “PythonCPU” if you would like
   - ```activate PythonCPU```
     - Run this command anytime you want to access the environment in terminal
   - ```conda install python=3.6```
     - Keras only works with python 3.6 and below
   - To install the libraries enter the following commands separately
     - ```conda install -c anaconda keras```
     - ```conda install -c anaconda tensorflow```
     - ```conda install -c anaconda scikit-image```
     - ```conda install -c anaconda scikit-learn```
     - ```conda install -c anaconda matplotlib```
     - ```conda install -c anaconda numpy```
     - ```conda install -c anaconda py-cpuinfo```
3. You can now exit the terminal and open up Anaconda Navigator
4. You will need to change the “base(root)” environment to the one you created, in this case “PythonCPU”
5. Install Jupyter Notebook
6. Once you open up Jupyter Notebook you can upload the “CNN_Work” notebook and run it from there

### Access the PYNQ-Z1 board over a network connection from computer browser:
1. To get started you can follow the “PYNQ-Z1 Setup Guide” at the following link: https://pynq.readthedocs.io/en/latest/getting_started/pynq_z1_setup.html
2. In this project we will be accessing the board over a network connection
3. To communicate with the board in your browser type in http://pynq:9090
5. Password: Xilinx
### PYNQ-Z1 Board CNN Code
1. After connecting to the board, to access and run some CNN code you will need to download it first, Xilinx has their own version at the following link. Their tutorial discusses how to install and run on the PYNQ-Z1
   - https://github.com/Xilinx/BNN-PYNQ 

## Current State and Future Plans

The current state of the project is the Convolution Neural Network with image recognition runs as desired on the target systems. It takes the CIFAR-10 dataset and trains a model to determine the types of images. Upon training the dataset, we then input in an image and have it decipher what the image is. At the moment the accuracy is roughly 70%-80% and the processing speed is 1-3 images per second on the CPU. On the PYNQ-Z1 board with the FPGA overlay, it is exceptionally faster than the CPU. 

If we had more time on the project, we would try to do more with the PYNQ board and create our own custom hardware overlay, instead of using a premade one for comparison. After researching other related works, their accuracy was much higher than ours, which would be another target to reach. So having more time to troubleshoot and improve on would be helpful. Another factor we would like to test is using a Raspberry Pi. The Raspberry Pi also has an ARM processor similar to PYNQ. The last factor if we had more time to improve on it, would be to add more performance metrics. The performance metric took some time to find and implement, which ultimately led us to add what we could. 

