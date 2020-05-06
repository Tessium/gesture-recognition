# gesture-recognition

### TITLE OF THE PROJECT:
# Object creation by voice and manipulation by gestures.
### PROBLEM STATEMENT:
   Using 3D CAD (Computer-Aided Design, computer graphics) you can create and animate objects as you want. However, is it so easy to imagine and visualize everything you want on your computer?  In addition, to create one 3d object you should use so many operations, remember hot keys, and rotate your view in 360 degree to check modifying object. And another difficulty we face is we cannot concentrate on work while modeling which leads to vanishing of ideas. 
   Nowadays companies trying to solve this issue with VR technologies using controllers (ex.: gravitysketch). But the huge drawback of it is comfort zone of the user: VR leads to slight headache and to an emetic response.
   To tackle those problems, we want to create more natural modeling environment for users.
### ABSTRACT:
Our project helps you to visualize and create objects in a new way by your voice, and manipulate using gestures. To alleviate these inconveniences, our team will first use voice recognition to transfer your commands to the platform you are working with (ex.: Blender – open source CAD). Therefore, you can create objects using your voice commands. After, with the help of motion recognition, we will detect gestures and apply them to the object that you have created (ex.: scale/move objects).
Architecture of end-to-end machine learning life cycle:
Our AI system provides a more natural modeling environment for 3D artists. Currently, to become a 3D artist, you must re-learn all the basics of modeling in order to move to a new environment (computer interface). The main goal of this project is to flatten this transition so that the artist remains in his environment, while computer learns to understand the human environment.

Computer have to recognize specific gestures in different conditions (bright/dark environment lighting, noise in web-cam and so on using ML and CV). An engineer would have to do it manually, by reconstructing every frame of the video. In our case using huge amount of data we will train machine to recognize gestures by itself. 
In order to do one modeling operation in a computer interface user must perform at least four operations in a specific order (ex.: create a cube: navigation panel -> create -> mesh objects -> cube). It is time-consuming and hard to remember, as a result, an artist is distracted from creative work.  In our case, these kinds of operations will be done by voice commands. (ex.: create a cube – that’s it).
As a result, human effort per process is reduced from (4-10 per 1) to (1 per 1). 
In the case of 3d modeling error rate from humans comes from unawareness of order of operations and operations itself which leads to a complete halt of the project. By providing speech and gesture recognition tools we give an intuitive environment where users can figure out what should be done by themselves. One more error comes from camera and microphone setup which creates barrier for gesture and voice recognition. By computing bigger data sets machine will handle these problems. 


#### Define datasets with specification of data sources and types of data.

Data set	Item	Data to be collected
Basic Information	Palm of the user	Number of fingers, palm to camera location
Gesture set	Set of gestures to be performed by user	User gestures
Environment	Camera
gestures performed in front of the camera from different angles and perspectives
	Environment lighting	The direction of light to palm from a different location in the environment
	Microphone	Microphone placed in various surroundings (crowdy place, inside of the box, windy environment)
	Background color	Background color for masking

Camera is our main source for collecting the datasets. Our major source of datasets are:
1.	Gestures performed by the user;
2.	Camera setup – for better gesture recognition our model will be trained from various camera setups (camera resolution, palm to camera location, etc.)
3.	Environment lighting – light is the major source of environment dataset formation. Model trained in different light setup will be able to recognize gestures no matter to lighting errors.
4.	Microphone – commands provided from user will be extracted for command comparison.

5.	Background color – some background colors (close to skin tone) are real challenge for CV (computer vision). And we need this dataset for gesture detection.

#### Methods to collect the datasets

Data is collected from standard webcam and microphone of PC/laptop. 
• Camera should have capability to capture video at least at 30fps frame rate with capture resolution of 720p. 
• Microphone preferably should be omnidirectional and must have at least 80Hz to 15 kHz of frequency response for better voice detection, as well as SPL (sound pressure level) in average of 100dB(decibels) for loud environment noise (this way it will be easier to extract clear voice).

Using these input devices, we will be able to detect gesture, motion and commands performed verbally.

Methods to store the collected data 

For real time motion/gesture detection we need parallel-processing system and IMDG (In-Memory Data Grid) is best choice for us. Because it provides ultra-high data availability by storing data in random access memory in a distributed state. IMDG is the support of transactionality that meets the requirements of ACID (atomicity, consistency, isolation, durability). 

Data processing and discovery technologies for the collected and stored datasets.

For datasets which we are collected beforehand, we can use image processors from SciPy and Keras libraries. First of all, for data augmentation, in order to create more datasets. Add some filters, such as color changing, background changing and etc. All these operations will help us to generate more datasets, moreover it will guarantee that our model won’t be over fitted.



Design and implementation of deep learning for the Big data analytics
There three types of algorithms, which can be applied for Deep Learning. Such as: DNN, CNN, RNN.
•	DNN (Deep Neural Network) - Fully Connected, All connections between two-layer nodes
•	CNN (Convolutional Neural Network) - Multiple nodes share a weight, Zoom out with Max pooling
•	RNN (Recurrent Neural Network) - Return the output value and status value of one node and input it further. Effect with simple storage device
For our project, we are going to use hand images as datasets. Therefore, features we are going to extract are gestures of hand itself. It could be finger positions combination, number of fingers etc.
 
 
From Deep Learning algorithms, we are going to use CNN (Convolutional neural networks) as it is used widely over projects in collaboration with Computer Vision. There are several reasons why we choose CNN algorithms. First, it significantly reduced complexity due to partial connection (convolution) structure using convolution operation. The main building block of CNN is the convolutional layer. Convolution is a mathematical operation to merge two sets of information. In our case, the convolution is applied on the input data using a convolution filter to produce a feature map. After a convolution operation we usually perform pooling to reduce the dimensionality. This enables us to reduce the number of parameters, which both shortens the training time and combats overfitting. Pooling layers down sample each feature map independently, reducing the height and width, keeping the depth intact.
How to resolve the complexity of the feature engineering for your application
Feature engineering is the process by which knowledge of data is used to construct explanatory variables, features, that can be used to train a predictive model. Engineering and selecting the correct features for a model will not only significantly improve its predictive power, but will also offer the flexibility to use less complex models that are faster to run and more easily understood.

To resolve the complexity of the feature engineering for our application we decided to use Automated Feature Engineering. There has been some progress made in the automation of feature engineering. FeatureTools for example is a python framework for transforming datasets into feature matrices. 
Types of learning:
1.	Supervised Learning: The feature vector X and the objective value Y are given. Classified by regression and classification problem
2.	Unsupervised Learning: The feature vector X is given, but the objective value Y is not given. Clustering task (customized publicity application based on customer orientation). Density estimation, feature space transformation task
3.	Reinforcement Learning: Although the objective value is given, it is different from supervised learning. Each sample of the game should be given a objective value.
4.	Semi-supervised Learning: Some have both X and Y, others have only X
5.	Transfer Learning: Learning new tasks relies on the previous learned tasks
Open issues and the next step
Issues
•	Bad camera quality
•	Low network bandwidth (if application will be served as cloud app)
•	Background
Next Steps
•	Integration of voice recognition, for wider functionality
•	Integration with popular 3D modeling applications
•	Integration AR technology
Final remarks
In the end, it should be remarked that our project helps you to visualize and create objects in a new way by your voice, and manipulate using gestures. Therefore, you can create objects using your voice commands. After, with the help of motion recognition, we will detect gestures and apply them to the object that you have created (ex.: scale/move objects).

