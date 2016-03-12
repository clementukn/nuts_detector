Nuts detector - Proof of concept of Random Bin Picking feature

### How it works
It is using the train objet detector tool of the [Dlib](http://dlib.net/). It has been compiled on Windows platform using Gcc 5.3.0.
The tool implements a SVM (Support Vector Machine) to detect objects in a picture. The machine is trained on the training set included in the project directory.

### Usage
train the machine:  
`nuts_detector.exe -tv nuts.xml`   
or directly detect nuts since the svm file is in the project directory:  
`nuts_detector.exe untrained.jpg`

### Improvements
In order to work in a wide range of situations:  
* The training set needs to be much larger (different lighting, orientation, surface on which pieces are, ...)  
* The pictures of the training set must have a better resolution  
* The detection might be improved using a contour operation (such as the one in openCV) but the 3D features of eVisionFactory probably bring more informations to be used to better train the model.

### Note
Training the model with holes of the nuts doesn't improve the result. The holes don't contain enough informations and threads of the holes can be detected as screws.

# Result
Here is the detection of nuts on an untrained set:  
![alt tag](result/untrained_result.jpg)