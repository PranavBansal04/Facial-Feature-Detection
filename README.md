# Facial Feature Detection

LIBRARIES USED : -<br /><br />
1.	Dlib :  dlib is, to directly quote its creators, a modern C++ toolkit containing ML algorithms and tools for creating complex software to solve real-world problems.<br /><br />

2.	OpenCv: OpenCv (Open Source Computer Vision Library) is a library for Computer Vision with machine learning modules that offers C++, Python, and Java interfaces and supports Windows, Linux, Mac OS, iOS, and Android. As the creators say, it was created for computational efficiency and a strong focus on real-time tasks – it’s blazing fast as a result.<br /><br />

3. Argparse:The argparse module makes it easy to write user-friendly command-line interfaces. The program defines what arguments it requires, and argparse will figure out how to parse those out of sys.argv. The argparse module also automatically generates help and usage messages and issues errors when users give the program invalid arguments.<br /><br />

4. Imutils :A series of convenience functions to make basic image processing functions such as translation, rotation, resizing, skeletonization, displaying Matplotlib images, sorting contours, detecting edges, and much more easier with OpenCV and both Python 2.7 and Python 3.<br /><br />
<br />

FUNCTIONS:- <br />
<br />

1.dlib.get_frontal_face_detector() : Returns the default face detector.<br />
<br />

2.dlib.shape_predictor(): This object is a tool that takes in an image region containing some object and outputs a set of point locations that define the pose of the object.it identify the locations of important facial landmarks such as the corners of the mouth and eyes, tip of the nose, and so forth.<br />
<br />

3. cv2.VideoCapture(0): This will return video from the first webcam on your computer.<br />
<br />

4. imutils.resize() : it evaluate width only but not height. Imutils never used height all times. While OpenCV used both width and height or either height or width. <br />
<br />

5. cv2.cvtColor(image, cv2.COLOR_BGR2GRAY): For color conversion, we use the function cv2.cvtColor(input_image, flag) where flag determines the type of conversion. For BGR -> Gray conversion we use the flags cv2.COLOR_BGR2GRAY. Similarly for BGR -> HSV, we use the flag cv2.COLOR_BGR2HSV.<br />
<br />

6. face_utils.shape_to_np(shape): For each face region, we determine the facial landmarks of the ROI and convert the 68 points into a NumPy array<br /><br />

7. face_utils.visualize_facial_landmarks(image, shape): facial landmarks can be used to align facial images to a mean face shape, so that after alignment the location of facial landmarks in all images is approximately the same.<br /><br />

8. cv2.imshow() :  to display an image in a window. The window automatically fits to the image size.First argument is a window name which is a string. second argument is our image. You can create as many windows as you wish, but with different window names.<br /><br />

9. cv2.destroyAllWindows() simply destroys all the windows we created.<br /><br />

10. cv2.waitKey() is a keyboard binding function. Its argument is the time in milliseconds. The function waits for specified milliseconds for any keyboard event. If you press any key in that time, the program continues. If 0 is passed, it waits indefinitely for a key stroke.<br />
<br />
<br /><br />


Summary: <br /><br />
<br />

The working of the code depends on facial landmark indexes. The facial landmark detector implemented inside dlib produces 68 (x, y)-coordinates that map to specific facial structures. These 68 point mappings were obtained by training a shape predictor on the labeled iBUG 300-W dataset.<br />

Facial regions can be accessed via simple Python indexing:<br />

![alt text](https://github.com/PranavBansal04/Facial-Feature-Detection/blob/master/face.PNG)

<br />
<br />

•	The mouth can be accessed through points [48, 68].<br />

•	The right eyebrow through points [17, 22].<br />

•	The left eyebrow through points [22, 27].<br />

•	The right eye using [36, 42].<br />

•	The left eye with [42, 48].<br />

•	The nose using [27, 35].<br />

•	And the jaw via [0, 17].<br />


These mappings are encoded inside the FACIAL_LANDMARKS_IDXS  dictionary inside face_utils of the imutils library.<br />
dlib’s pre-trained facial landmark detector is used for detecting these facial features. <br />
Firstly our code detects faces in the image and then it loops over every face to detect its facial features. These functions are performed for every frame and then it is shown in the output.<br /> 
The facial features that the code detects are:<br />
-	Left eyebrow<br />
-	Right eyebrow<br />
-	Left eye<br /><br />
-	Right eye<br />
-	Nose<br />
-	Mouth<br />
-	Jawline<br />
The visualize_facial_landmarks function which is already included in the imutils library helps to visualize each of the facial feature and overlay the results on the input image. <br />



Results on images:<br /><br />
1.
![alt text](https://github.com/PranavBansal04/Facial-Feature-Detection/blob/master/sample1.jpeg)
<br />
2.
![alt text](https://github.com/PranavBansal04/Facial-Feature-Detection/blob/master/sample2.jpeg)
<br />
3.
![alt text](https://github.com/PranavBansal04/Facial-Feature-Detection/blob/master/sample3.jpeg)
