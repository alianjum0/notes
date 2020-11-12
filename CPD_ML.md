# CPD Machine Learning Lecture
## Basic Machine Learning
* What is Learning
Tom M. Mitchell definition:
"A computer program is said to learn from experience E with respect to some
task T and some performance measure P, if its performance on T,  as measured by
P, improves with experience E."
* Learning autonomously based on experience
Artificial Intelligence -> Machine Learning -> Deep Learning
DL is a subset of ML and ML is a subset of AI
Artificial Intelligence includes ML, NLP, Expert system, vision, speech,
robotics, planning
* Machine learns by identifying features and patterns of knowledge same as
  humans.
1) example of showing pear to a kid who has never seen it. She will predict it as apple.
2) second example of devil vs angel. Our cognition knows from experience how these looks like.
3) example of fruits that you have not seen before. chom chom (Indonesia), dorian (Vetinam), 
Types of data for training
Training data, Testing data
-> feed data -> machines learns -> check accuracy
- example of predicting rain
## Classification of ML
* Supervised Algorithms: provide labeled data
* Unsupervised Algorithms: Clustering, Separate on the basis of similarities and patterns
* Reinforcement Algorithm: improve by giving positive or negative feedback
### Supervised Algorithms
* KNN
* Naive Bayes Classifiers
* Linear Regression
* Logistic Regression
* SVM
* Decision Trees
* Random Forest
#### KNN
based on the similarities between the data points
plot on features, find Euclidean distance and find nearest k points
It classify to the class with most nearest points in k
example: k=3, blue=2, red=1, point -> blue
In advance form it uses different formula for calculating distance than
Euclidean
#### Naive Bayes Classifier
probabilistic classifier
example:
classes: Male, Female
features: height, weight, foot size
calculate mean, variance of each feature
since posterior numerator(female) is greater in the case of female, new data is
female
### Unsupervised Algorithms
K-means clustering
we take the k value to the different type of clusters/classes
calculate the centroid until changes are minimised
### Artificial Neural Networks
3 different layers
Input layer: data enter
Hidden layer: processing 
Output layer: output
difference between neural and deep learning is the depth of hidden layers(more than
2 is deep)
CNN:
the layers are defined in 3 or more dimensions and all neurons are not connected
pixel is in 2d and voxel is in 3d

# Part 2
## Brain-Computer Interface
signal from human brain to control device
Berger in 1924 record signal from brain first time
### Human Nervous System
Central Nervous System: Brain, Spinal Cord
Peripheral Nervous System: Nerves
EMG-based prosthesis
EMG, Electromyography system
Myography = mind signal
Electrography = electric signal
example of wrist and hand motion
previously taking signals from muscles
now next thing is to get signals from brain
Signal Processing
- Pre-processing -> Feature extraction -> Classification
Brain Imaging
Structural Imaging- structure of brain, check brain clot etc
Functional imaging: when an activity is performed what metabolic changes is
done
Invasive: open brain and plant inside
ECoG, Implanted Electrodes
Non invasive: from outside
EEG MEG, fNIRS, fMRI
### Invasive BCI
electrode in motion cortex to control a mouse
invasive BCI control by a Monkey
in 2008 brain control robotics by monkey
Nature, on of the top journal of the world 
In 2012 drank coffee controlling robotics from brain
### ECoG-based 
placed on the surface of the brain
no pain in the brain, because no pain sensors
surgery is required
### EEG based 
wheel chair control using EEG 
EEG based system wear on head for home automation
EEG based game control
Limitation
consistency is still an issue
signal issue is a lot
use of conductive gels
recognition and patterns matching
### fMRI- based BCI
control robot from Israel to France
- control of lower limb
fNIRS-based BCI
infrared light based 
other application
* Binary decision decoding: coma 
all input are present but no output
think in brain for yes and no
* Multiple choice question decoding
When more choices were present than accuracy was decreased
* Lie detection system
80 to 96 percent accuracy after using brain signals
polygraph: eye blink, blood pressure, pulse, respiration and skin conductivity
* Drowsiness detection
sleeps while driving on motorways
check oxygen level to set an alert system
when person is close to sleep, oxygen level is low
* Automatic detection of heart diseases from ECG signals
We can detect 5 common heart diseases with accuracy of 98% from ECG

### Computer-controlled brain
move real mouse by giving signal to brain
by negative and positive feedback
pain and pleasure
noman.naseer@mail.au.edu.pk

Indirect brain signal: signals taken from muscles
