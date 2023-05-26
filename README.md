# roadbuddydetection

Task1 : Data Acquisition

In the data acquisition part, we find the images realated to the data we want to make a dataset.There are many sources we can use to find the data like kaggle or some google sites. Our group want to detect the car , human , and motorbike so find the picture from those classes. The pictures we got are raw pictures without any label beforehand.

Task 2  : Data Preparation

In this task, we use the roboflow to annotate and label the class. As i mentioned that there are three classes car, human, and motorbike. So, first we import all the data to the roboflow. Next, we draw a rectangle box to the class shown in the picture. After all the pictures are annotated and the class are labeled, we can now split the data into train , valid , and test. After that we will augment the dataset we have by stretching , shrinking , rotating the dataset randomly. After the augmentation we will gain a lot more dataset. Finally, we have 2000 images dataset.

Task 3 : Model Training and Deploy

After we augment the data from roboflow we can download the generated dataset. The dataset comes with three foldes train , test , and valid. Each folder comes with two subfolders images and labels.

We will use yolov5 to train the model. First, we will clone the yolov5 to colab. Second, we will install all the required packages from the requirements.txt . Third, login to the website weight and biases to observe the training performance. Fourth, we will edit the files coco.yaml and yolov5s.yaml to be related with the classes we want. Lastly we will use the train.py which is the sample code from yolo to train the model. In train.py we set the parameter to train the image with size of 640x640 and train it for 100 epochs according to classes clarified in coco.yaml and yolov5s.yaml.

After the training is done, we can test the model by using the another sample code from yolov5 which is detect.py to simply draw a rectangle and label the class it detected. We can also observe the performance of the model from the summary report in the colab in the train.py cell. Moreover, the performance is also shown in the weight and biases website or wandb with a graphic visualization. 

After the training is done we can test with the code prepared. The python code is using the webcam and detect each object frame by frame so it would need a really high performance computation power to run this code smoothly.

Task 4 : 

After training in our computer, we can now copy the code and model to the raspberry pi via flashdrive. We are required to install some necessary packages that yolo required to use the model like torch, opencv for open the camera, etc. We can do it all on terminal. To make the code run smoothly on raspberry pi which is not a very high performance device compared to the computer, we need to use the neural compute stick or NCS that is plugged into the raspberry pi to make computing this kind of work faster. After installing everything, we can test the code by running python modeltest6.py which is the code name and test it. The result may looks pretty laggy due to the lack of compatibility from the code with the NCS, which makes the NCS not working at all.
