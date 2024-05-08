This research endeavors to alleviate the manual screening challenges associated with hand Osteoarthritis (OA) by presenting an automated algorithm tailored for joint detection in X-ray images. 
The project unfolds through the introduction of two distinct methods: Method 1, rooted in computer vision techniques, and Method 2, harnessing machine learning with prominent deep learning models. 
Leveraging a dataset comprising 3588 X-ray images, both solutions undergo meticulous evaluation using a dedicated testing set for comparative analysis.

Method 1:
The essence of the proposed algorithm lies in its ability to iterate through images within a specified directory, resizing each to 700x900 pixels, and storing them in a newly designated directory named "presol1". 
Key to the process is the utilization of the Mediapipe library for detecting hand landmarks within the images. For each detected hand, the algorithm meticulously iterates through specified joint indices, calculating relative positions and angles between adjacent joints. 
This results in the drawing of yellow circles at joint positions and angled rectangles.

Moreover, the algorithm extracts normalized x and y coordinates of the landmarks, converting them into pixel coordinates relative to the image size. 
Notably, a specific block of code is executed when processing the 5th landmark, extracting its x and y position, computing the angle between this landmark and a specified target landmark, and subsequently drawing a circle and an angled rectangle based on this information. 
Ultimately, all processed images are systematically saved to the designated "solution1" folder.

Method 2:
Method 2 leverages machine learning techniques, commencing with the dataset split into 85% training and 15% testing subsets. 
The testing data retrieval process involves reading both image and text files, extracting 32x32 images corresponding to each center point mentioned in the text file. 
Similarly, for training data, the algorithm reads image and text files and extracts 32x32 images corresponding to each center point mentioned.

Key to Method 2 is the utilization of Convolutional Neural Network (CNN) architecture. Following the importation of necessary libraries, the model architecture is meticulously crafted. 
Categorical crossentropy serves as the loss function, with the Adam optimizer employed for optimization. Evaluation of model performance is facilitated through the Adam metric.

The sequential neural network comprises multiple layers, starting with convolutional layers (Conv2D) for feature extraction, followed by max-pooling layers (MaxPooling2D). 
The model culminates with dense layers (Dense) for classification, totaling 123,715 trainable parameters.

In terms of performance metrics, the model demonstrates an overall accuracy of 33.88%, indicating the proportion of correctly classified instances. 
Precision, gauging the accuracy of positive predictions, stands at 33.38%. The F1 score, encapsulating both precision and recall, is calculated at 17.75%. 
Additionally, the model exhibits a recall rate of 46.4%, signifying its ability to identify all relevant instances.





