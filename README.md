# Computer-Vision
Hough Transformation:
Implementing some basic image processing algorithms and putting them together to build a Hough Transform based line detector.

Bag of words:
Building an end to end system that will determine which type of scene it is.
![image](https://github.com/zhaxuefan/image/blob/master/718.png)
Bag of Words represents a document as a vector or histogram of counts for each word that occurs in the document, as shown in Figure 2. The hope is that different documents in the same class will have a similar collection and distribution of words, and that when we see a new document, we can find out which class it belongs to by comparing it to the histograms already in that class.
![image](https://github.com/zhaxuefan/image/blob/master/7181.png)

There is 3 major part: 
Part 1: build a dictionary of visual words from training data.
Part 2: build the recognition system using visual word dictionary and training images.
Part 3: evaluate the recognition system using test images.
In Part 1, use the provided filter bank to convert each pixel of each image into a high dimensional representation that will hopefully capture meaningful information, such as corners, edges etc. This will take each pixel from being a 3D vector of color values, to
an nD vector of filter responses. Then take these nD pixels from all of the training images and and run K-means clustering to find groups of pixels. Each resulting cluster center will become a visual word, and the whole set of cluster centers becomes our dictionary of
visual words.
![image](https://github.com/zhaxuefan/image/blob/master/7182.png)

In Part 2, the dictionary of visual word you produced will be applied to each of the training images to convert them into a wordmap. This will take each of the nD pixels in all of the filtered training images and assign each one a single integer label, corresponding to the
closest cluster center in the visual words dictionary. Then each image will be converted to a “bag of words”; a histogram of the visual words counts. Use these to build the classifier.
![image](https://github.com/zhaxuefan/image/blob/master/7183.png)

In Part 3 will evaluate the recognition system built. This will involve taking the test images and converting them to image histograms using the visual words dictionary and the function you wrote in Part 2. Next, for nearest neighbor classification,  use a
histogram distance function to compare the new test image histogram to the training image histograms in order to classify the new test image. Doing this for all the test images will give idea of how good your recognition system.
![image](https://github.com/zhaxuefan/image/blob/master/7184.png)

In document classification, inverse document frequency (IDF) factor is incorporated which diminishes the weight of terms that occur very frequently in the document set.Improve system by IDF.



Image matching, stitching and homographies: 
proceeding towards showing how to transform between template images and source images, as is commonly used in panoramic photo stitching and augmented reality applications.
In this implement, The BRIEF descriptor encodes information from a 9 × 9 patch p centered around the interest point at the characteristic scale of the interest point. Also implement how to overcome rotation problem in BRIEF. Implement Homography based on RANSAC and put it togother to get VR trials.
Based on homography between two images, wrap image into the other one to get imageStitching.


3D Reconstruction:
Implement The Eight point algorithm and Seven Point Algorithm to get essential matrix and epipolar lines between to matched image. 
Matrix construction compute the camera matrices and triangulate the 2D points to obtain the 3D scene structure. To obtain the Euclidean scene structure, first convert the fundamental matrix F to an essential matrix E. Examine the lecture notes and the textbook to find out how to do this when the internal camera calibration matrices K1 and K2 are known.Then get 3D visualization for plot.Bundle adjustment: RANSAC method seen in class can be applied to the problem of fundamental matrix estimation.


Lucas Tracking: This is divided into three part: first is implement a simple Lucas-Kanade (LK) tracker with one single template; Secondly, the tracker will be generalized to accommodate for large appearance variance. The third part is to implement a motion subtraction method for tracking moving pixels in a scene. Finally studying efficient tracking which includes inverse composition and correlation filters.
