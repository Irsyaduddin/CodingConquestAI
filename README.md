# CodingConquestAI
Prep for Coding Conquest Brunei for December 2019

So far what I have researched are OpenCV and Google's TensorFlow machine learning platform.



### Regarding how OpenCV works: 

1. Use function SIFT detector, then if found draw region of interest (ROI). Then crop out the ROI and feed it to the SWIFT detector.
2. SIFT takes 2 input images: 
   - image where we look for the object
   - image template (trying to match to this template)
3. Then gray scale the 1st image & define the image template.
4. Then create a SIFT object and run the openCV SIFT detect & compute function.
   - This will then detect keypoints and compute the descriptors.
   - Descriptors are vectors which stores the information about the keypoints. 
5. Histogram of Oriented Gradients (HOG’s)
   - Calculates the image gradient vector of pixels inside a predetermined box.  
   - Gradient vector are sort of the direction or flow of the image intensity itself.  
     - This gradient vector is then represented as a histogram.    
     - Get the cell & split into multiple angular bins based on angle. E.g. 20o per bin   
6. HAAR classifiers
   - Inputs Haar features into a series of classifiers (cascade) to identify objects in an image.  
   - Extract features using sliding windows of rectangular blocks.  
     - These Haar features are single valued and are calculated by subtracting the sum of pixel intensities under the white rectangle from the black rectangles.    
   - But all this requires tons of processing & computation.    
   - Therefore Boosting was then used. 
     - To find the most informative features.   
     - Use weak classifiers to build strong classifiers. How?  
7. By assigning heavier weighted penalties on incorrect classifications.
8. With these features, we use the most informative feature first to check if the image can potentially have the object.
   - This is called “Cascade of Classifiers” 
   - And this file is stored as a .xml file (extensible markup language)
  
