
###Machine_learning_Network-No-Libraries-
In this code ,I use neural nets to recognize handwritten digits . you can test the network code by drawing number using Paint for example in windows , and save the PNG picture ...., more details keep reading please . I share this code with you to help learn more about AI DEEP LEARNING and Network .. This code may be usefule for teachers , students ..


------------

**There are 4 files :**
1. -machine_learning.py
2. -mnist.pkl.gz 
3. -mnist_loader.py 
4. -png_converter.py

------------

Inside machine_learning.py , you can find the heart of this project .it implement the stochastic gradient descent learning algorithm for a feedforward neural network. Gradients descent are calculated using backpropagation. In order to make this code simple , I have omit many desirable features.

-mnist.pkl.gz : this is MNIST data contains 50,000 pictures as a tuple , this is the training data

-mnist_loader.py : I use this code to load data and convert to more convenient format .

-png_converter.py : I use this code to convert a png picture (drawing number using Paint in Windows ) to Array of 728 pixls in order to test the network on data he never seen before .

## How to use the code :

1- open the command python and make sur that you are in the directory #import the importants files

import mnist_loader import png_converter import machine_learning from numpy import * # to avoid problems like INT64 not found import numpy as np

2- Tape this command in order :

  ```shell
  `training_data1, validation_data1, test_data1 = mnist_loader.load_data() # loading the MNISTDATA`
```


convert the data to more convenient format 
```shell
training_data1, validation_data1, test_data1 = mnist_loader.load_data_wrapper(training_data1, validation_data1, test_data1)
```

```shell
net = machine_learning.machine_learning_network([784, 30, 10]) #create a network object
```
 ```shell
net.stochastic_gradient_descent(training_data1, 30, 10, 3.0, test_data=test_data1) # start training 
```
 
 wait a few minutes or seconds it depend on your computer you should see somthing like this at the end .. 
1.  Epoch 24: 8618 / 10000 
2.  Epoch 25: 8603 / 10000 
3.  Epoch 26: 8621 / 10000 
4.  Epoch 27: 8607 / 10000 
5.  Epoch 28: 8611 / 10000 

  this mean that our network succesfly reconize correctly 8611 from 10000 (not good , not too bad ) Epoch 29: 8608 / 10000

-This mean that the training section is complete now , we test the network with our own pictures you can use the pictures from digitsImages folder or you can even make your own picture using Paint , make sur that the dimensions is 28*28 pixel ; and draw by your mouse any number , (5 for example ) use black color and white backgroudn . and save the picture in same directory as png_converter.py

I will test tow pictures
back to python command and tipe this commands:

 convert image to arrays of pixls
```shell
im1= png_converter.imageprepare('./image2.png')
im2= png_converter.imageprepare('./image4.png') 
```
 image2 is actually 2 , same for image4 B hold the correct output
```shell
B= np.array([2,4],dtype=int64)
```
A : hold the format array of our pictures
```shell
A = np.array([im1,im2],dtype=float32)
datacreat=(A,B) 
```
convert data to be more convenient as input to our network
```shell
datatestt = mnist_loader.data_converter(datacreat) 
```


And now finally we test our network , it should give us the correct answer if it's well trained the correct answer should be 2 and 4 , since that the two image represent the degit 2 and 4

net.test_network(datatestt) #we tape this command to test : and i get this result :

net.test_network(datatestt) network : the digit seems to me 8 ,but it should be 2 , I need more excercies coach network : the digit is 4 , i am well trained thanks coach

the network give us one answer correct ,and the other is false , why ? actually maybe our network need more training data or even improve the algorithme , also I test my network with pictures that I pained using Paint windows , or the data training from mnist certainly not made by PAINT .

#  Any questions ,don't hesitate : chawkijeder@gmail.com




