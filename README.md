# Face Detecton In Python Using OpenCV

# OpenCV

OpenCV stands as an open-source software library for computer vision and machine learning. Released under the BSD license, it's freely available for both academic and commercial use. Boasting over 2500 algorithms, OpenCV offers a rich toolkit encompassing machine learning for classification and clustering, image processing, vision algorithms, fundamental algorithms, drawing functions, as well as GUI and I/O functions for images and videos. Its versatile applications range from face detection and object recognition to 3D model extraction, image processing, camera calibration, and motion analysis.

Written in native C/C++, OpenCV supports interfaces in C++, C, Python, and Java, making it accessible across various programming languages. Its compatibility spans across major operating systems including Windows, Linux, macOS, iOS, and Android. Engineered for computational efficiency, OpenCV is tailored for real-time applications, leveraging optimized C/C++ code to harness the power of multi-core processing.

# Face Detection

Face detection has garnered significant interest due to its real-time applications, but it poses challenges for machines. Despite ongoing research, achieving efficient and accurate face detection remains complex. This difficulty arises from the diverse variations in image appearance, including pose variation (frontal or non-frontal), occlusion, image orientation, illumination changes, and facial expressions.

OpenCV provides numerous pre-trained classifiers for detecting faces, eyes, smiles, and more. These classifiers are stored as XML files in the opencv/data/ directory. Specifically for face detection, OpenCV offers two main pre-trained classifiers:

Haar Cascade Classifier
LBP (Local Binary Patterns) Cascade Classifier
In this tutorial, we'll delve into both of these face detectors to understand their functioning and usage.

# Haar Cascade Classifier

It is a machine learning based approach where a cascade function is trained from a lot of positive (images with face) and negative images (images without face). The algorithm is proposed by Paul Viola and Michael Jones.

The algorithm has four stages:

# 1.Haar Feature Selection:
Haar features are calculated in the subsections of the input image. The difference between the sum of pixel intensities of adjacent rectangular regions is calculated to differentiate the subsections of the image. A large number of haar-like features are required for getting facial features.
# 2.Creating an Integral Image: 
Too much computation will be done when operations are performed on all pixels, so an integral image is used that reduce the computation to only four pixels. This makes the algorithm quite fast.
# 3.Adaboost: 
All the computed features are not relevant for the classification purpose. Adaboost is used to classify the relevant features.
# 4.Cascading Classifiers: 
Now we can use the relevant features to classify a face from a non-face but algorithm provides another improvement using the concept of cascades of classifiers. Every region of the image is not a facial region so it is not useful to apply all the features on all the regions of the image. Instead of using all the features at a time, group the features into different stages of the classifier.Apply each stage one-by-one to find a facial region. If on any stage the classifier fails, that region will be discarded from further iterations. Only the facial region will pass all the stages of the classifier.

# LBP Cascade Classifier 

LBP is a texture descriptor and face is composed of micro texture patterns. So LBP features are extracted to form a feature vector to classify a face from a non-face. Following are the basic steps of LBP Cascade classifier algorithm:

# 1.LBP Labelling:
A label as a string of binary numbers is assigned to each pixel of an image.
# 2.Feature Vector: 
Image is divided into sub-regions and for each sub-region, a histogram of labels is constructed. Then, a feature vector is formed by concatenating the sub-regions histograms into a large histogram.
# 3.AdaBoost Learning:
Strong classifier is constructed using gentle AdaBoost to remove redundant information from feature vector.
# 4.Cascade of Classifier:
The cascades of classifiers are formed from the features obtained by the gentle AdaBoost algorithm. Sub-regions of the image is evaluated starting from simpler classifier to strong classifier. If on any stage classifier fails, that region will be discarded from further iterations. Only the facial region will pass all the stages of the classifier.

# Steps :

       # 1.Loading HaarCascadeFace Algorithm
       
       # 2.Initializing Camera
       
       # 3.Reading Frame from Camera
       
       # 4.Converting Color image into Grayscale Image
       
       # 5.Obtaining Face coordinates by passing algorithm
       
       # 6.Drawing Rectangle on the Face Coordinates
       
       # 7.Display the output Frame

# Output :

To see the output video, go to the media file and check the output video
