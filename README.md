
FACE DETECTION SYSTEM WITH FACE RECOGNITION MODEL

ABSTRACT
 
Face recognition has been one of the most interesting and important research fields in the past two decades. The reasons come from the need of automatic recognition and surveillance systems, the interest in human visual systems on face recognition, and the design of human-computer interface, etc. These researches involve knowledge and researchers from disciplines such as neuroscience, psychology, computer vision, pattern recognition, image processing, and machine learning, etc. A bunch of papers have been published to overcome different factors (such as illumination, expression, scale, pose) and achieve better recognition rate, while there is still no robust technique against uncontrolled practical cases which may involve all kinds of factors simultaneously. In this report, we will go through general ideas and structures of recognition, important issues and factors of human faces, critical techniques and algorithms, and finally give a comparison and conclusion. To be announced, this report only focuses on color-image-based (2D) face recognition, rather than video-based (3D) and thermal-image-based methods.


Table of content:
Introduction to face recognition: Structure and Procedure.
Fundamental of pattern recognition.
Techniques and algorithms on face feature extraction and face recognition.
Application and Limitation.
Conclusion.
 
Introduction to Face Recognition: Structure and Procedure
 
In this report, we focus on image-based face recognition. Given a picture taken from a digital camera, we would like to know if there is any person inside, where his/her face is located, and who he/she is. Towards this goal, we generally separate the face recognition procedure into three steps :  Face Detection, Feature Extraction, and Face Recognition  (shown at Fig. 1). Face Detection Feature Extraction Face Recognition Image Verification/ Identification
 


 Figure 1: Configuration of a general face recognition structure
 ![Block-Diagram-of-Face-Recognition-System](https://user-images.githubusercontent.com/115110413/225956436-2c250f1d-a01c-4022-b557-4db6b166d63d.png)

Face Detection:
The main function of this step is to determine (1) whether human faces appear in a given image, and (2) where these faces are located at. The expected outputs of this step are patches containing each face in the input image. In order to make further face recognition systems more robust and easy to design, face alignment is performed to justify the scales and orientations of these patches. Besides serving as the pre-processing for face recognition, face detection could be used for region-of-interest detection, retargeting, video and image classification, etc. 

Feature Extraction:
After the face detection step, human-face patches are extracted from images. Directly using these patches for face recognition have some disadvantages, first, each patch usually contains over 1000 pixels, which are too large to build a robust recognition system1 . Second, face patches may be taken from different camera alignments, with different face expressions, illuminations, and may suffer from occlusion and clutter. To overcome these drawbacks, feature extractions are performed to do information packing, dimension reduction, salience extraction, and noise cleaning. After this step, a face patch is usually transformed into a vector with fixed dimension or a set of fiducial points and their corresponding locations. We will talk more in detail about this step in Section 2. In some literature, feature extraction is either included in face detection or face recognition.
 
Face Recognition:
After formulating the representation of each face, the last step is to recognize the identities of these faces. In order to achieve automatic recognition, a face database is required to build. For each person, several images are taken and their features are extracted and stored in the database. Then when an input face image comes in, we perform face detection and feature extraction, and compare its feature to each face class stored in the database. There have been many researches and algorithms proposed to deal with this classification problem, and we’ll discuss them in later sections. There are two general applications of face recognition, one is called identification and another one is called verification. Face identification means given a face image, we want the system to tell who he / she is or the most probable identification; while in face verification,
given a face image and a guess of the identification, we want the system to tell true or false about the guess.



Fundamental of pattern recognition 
The discipline, pattern recognition, includes all cases of recognition tasks such as speech recognition, object recognition, data analysis, and face recognition. In order to generate a system for recognition, we always need data sets for building categories and compare similarities between the test data and each category. A test data is usually called a “query” in image retrieval literatures, we can easily notice the symmetric structure. Starting from the data sets side, firstly performing dimension reduction on the stored raw data. The methods of dimension reduction can be categorized into data-driven methods and domain-knowledge methods. After dimension reduction, each raw data in the data sets is transformed into a set of features, and the classifier is mainly trained on these feature representations. When a query comes in,  the same dimension reduction procedure is  on it when a new picture comes in  and enters its features into the trained classifier.The output of the classifier will be the optimal class label or a rejection note.
  
 
Techniques and algorithms on face feature extraction and face recognition.

CMake Is a build system generator that generates build scripts for specific platforms from a high-level project description. It allows you to define the project's structure and the relationships between the various files in the project, and then generates the build scripts for you. This means that you only need to write the project description once, and CMake will generate build scripts for multiple platforms and compilers.
CMake uses a simple, easy-to-learn syntax for defining the build process, and it has a number of built-in commands and functions for defining common build tasks. It also has a number of advanced features, such as support for out-of-source builds, which allows you to build your project in a separate directory from the source code, and support for complex dependency management.
CMake can be used to build a wide variety of software, including libraries, applications, and executables. It can also be used to build software packages that can be installed and distributed to other users. CMake is widely used in the open-source community, and it is the build system of choice for many large open-source projects.

 
dlib Is a modern C++ library that contains machine learning algorithms and tools for creating complex software in C++ to solve real world problems. It is used in a wide range of applications including security, robotics, and machine learning.
Some of the features of dlib include:
A wide range of machine learning algorithms, including support vector machines, decision trees, neural networks, and clustering algorithms.
Tools for creating machine learning pipelines, including feature extraction and selection, dimensionality reduction, and model evaluation.
A set of C++ utility functions for performing common tasks such as reading and writing data, resizing images, and creating graphical user interfaces.
A set of tools for working with large datasets, including functions for loading and saving data, and tools for working with data stored in distributed systems.
A powerful numerical optimization library for solving optimization problems, including support for large-scale optimization and constrained optimization.
dlib is designed to be easy to use and integrate into your C++ projects. It is well-documented, with extensive documentation and examples available online.
 
face_recognition is a Python library that allows you to recognize and manipulate faces in pictures. It uses dlib and OpenCV to detect and extract facial features and compares them to a database of known faces to identify the person in the picture.
Some of the features of the face_recognition library include:
The ability to recognize faces in pictures and identify the person they belong to.
The ability to manipulate faces in pictures, including resizing, cropping, and rotating faces.
The ability to detect and extract facial features, such as the eyes, nose, and mouth.
The ability to compare faces to a database of known faces to determine if they match.
The face_recognition library is easy to use and can be integrated into your Python projects with just a few lines of code. It is well-documented, with extensive documentation and examples available online.
 
 
NumPy is a library for the Python programming language that allows you to work with large, multi-dimensional arrays and matrices of numerical data. It provides functions for performing mathematical operations on these arrays and matrices, and it also contains functions for working with large numbers of data in memory-efficient ways.
Some of the features of NumPy include:
Support for large, multi-dimensional arrays and matrices of numerical data
Functions for performing mathematical operations on these arrays and matrices
Functions for reading and writing array data to and from files
Tools for integrating C/C++ and Fortran code
Linear algebra operations, including matrix multiplication, singular value decomposition, and eigenvalue decomposition
Statistical functions, including mean, median, standard deviation, and correlation coefficients
Random number generation
NumPy is designed to be efficient and easy to use. It is an essential library for scientific computing with Python, and it is a key component of many other scientific libraries in the Python ecosystem, such as SciPy and scikit-learn.

 
OpenCV (Open Source Computer Vision) is a library of programming functions mainly aimed at real-time computer vision. It is designed for computational efficiency and with a strong focus on real-time applications. OpenCV-Python is a Python wrapper for the OpenCV library. It allows you to use the functionality of OpenCV in your Python scripts.
Some of the features of OpenCV include:
Image processing and computer vision algorithms, including object detection, image segmentation, and image enhancement
Video analysis, including object tracking and background subtraction
Camera calibration and 3D reconstruction
Support for machine learning techniques, including neural networks and decision trees
Functions for image and video input/output, including support for common image and video formats and image and video capture from cameras
OpenCV-Python is a popular choice for computer vision tasks in the Python ecosystem, and it is widely used in academia and industry. It is well-documented and has a large community of users and developers who contribute to the project.





Algorithm code explaination:

Define a function get_encoded_faces() that returns a dictionary of names and face encodings for all jpeg and png images in the "faces" directory.

Define a function unknown_image_encoded(img) that takes an image file name as input and returns the encoding for that image.

Define a function classify_face(im) that takes an image file path as input and returns a list of face names.

In the classify_face() function, get the list of known face encodings and names using the get_encoded_faces() function.

Read the image file specified in the input using cv2.imread().

Find the locations of the faces in the image using face_recognition.face_locations().

Get the encodings for the faces in the image using face_recognition.face_encodings().

Initialize an empty list for the face names.

Iterate over the list of unknown face encodings. For each encoding, compare it to the list of known face encodings using face_recognition.compare_faces().

If a match is found, get the index of the best match using np.argmin() and face_recognition.face_distance(), and get the corresponding name from the list of known names. If no match is found, label the face as "Unknown".

Draw a box around each face and label it with the corresponding name using cv2.rectangle() and cv2.putText().

Display the image with the labeled faces using cv2.imshow().
	
In an infinite loop, check for the 'q' key being pressed. If it is, return the list of face names and exit the loop.


Applications 
Ride-sharing companies can use facial recognition to ensure the right passengers are picked up by the right drivers.
IoT benefits from facial recognition by allowing enhanced security measures and automatic access control at home.
Law Enforcement can use facial recognition technologies as one part of AI-driven surveillance systems.
Retailers can use facial recognition to customize offline offerings and to theoretically map online purchasing habits with their online ones.


Limitations

Poor Image Quality - The effectiveness of facial-recognition algorithms is influenced by the image quality. When compared to a digital camera, the quality of the scanned video is relatively poor. Even high-definition video is typically 720p, but it can be as high as 1080p. These numbers correspond to around 2MP and 0.9MP, although a low-cost digital camera may capture 15MP.
Small Image Sizes - The recognized face is just 100 to 200 pixels wide due to the already modest image size and the target’s distance from the camera. Furthermore, it takes a lot of processing power to scan an image for different face sizes. To reduce false positives during detection and hasten image processing, the majority of algorithms allow for the choice of a face-size range.
Different Face Angles -  The relative angle of the target’s face has a significant impact on the recognition score. Usually, several angles are employed when enrolling a face in the facial recognition software. The algorithm’s capacity to create a face template is impacted by any view other than a frontal view. The rating of any resulting matches increases with the directness and the image’s resolution.  
Data Processing and Storage - The high-definition video takes up a lot of disc space despite having a resolution that is much lower than that of digital camera images. Processing every frame of video would be a huge job, thus typically only a small portion (10% to 25%) is subjected to a recognition system. Agencies may employ computer clusters to reduce overall processing time. However, adding computers necessitates a significant amount of data transfer through a network, which may be constrained by input-output limitations, further slowing down processing. Unfortunately, when it comes to facial recognition, people
outperform technology by a wide margin. However, when watching a source video, humans can only focus on a small number of people at once. Many people can be compared to a database of thousands of people by a computer.

 

Scope of Facial Recognition Technology in India

The world is using facial recognition technology and enjoying its benefits. Why should India be left out? There is a huge scope of this technology in India and it can help improve the country in various aspects. The technology and its applications can be applied across different segments in the country.
Preventing the frauds at ATMs in India. A database of all customers with ATM cards in India can be created and facial recognition systems can be installed. So, whenever a user enters an ATM his photograph will be taken to permit the access after it is being matched with stored photo from the database.
Reporting duplicate voters in India.
Passport and visa verification can also be done using this technology.
 Also, driving license verification can be done using the same approach.
In the defense ministry, airports, and all other important places the technology can be used to ensure better surveillance and security.
It can also be used during examinations such as the Civil Services Exam, SSC, IIT, MBBS, and others to identify the candidates.
This system can be deployed for verification and attendance tracking at various government offices and corporations.
 For access control verification and identification of authentic users it can also be installed in bank lockers and vaults.
 For identification of criminals the system can be used by police forces also.
 


CONCLUSION


Face recognition technology has come a long way in the last twenty years. Today, machines are able to automatically verify identity information for secure transactions, for surveillance and security tasks, and for access control to buildings etc. These applications usually work in controlled environments and recognition algorithms can take advantage of the environmental constraints to obtain high recognition accuracy. However, next generation face recognition systems are going to have widespread application in smart environments -- where computers and machines are more like helpful assistants.

To achieve this goal computers must be able to reliably identify nearby people in a manner that fits naturally within the pattern of normal human interactions. They must not require special interactions and must conform to human intuitions about when recognition is likely. This implies that future smart environments should use the same modalities as humans, and have approximately the same limitations. These goals now appear in reach -- however, substantial research remains to be done in making person recognition technology work reliably, in widely varying conditions using information from single or multiple modalities
