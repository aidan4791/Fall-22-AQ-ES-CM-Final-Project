# Fall-22-AQ-ES-CM-Final-Project
In this project, we will be exploring autonomous vehicles and how they can detect objects on the road while driving. For this project, we will only be using stop signs as the object that will be detected. We will conduct this by using a code that will let the car know of each detection and what to do when the car comes across the objects and road signs. Testing the model will be done by inputting images that were not part of the training datasets to see if the model can be used outside of its training.

Our model was based on a concept called “YOLOv4”. It stands for You Only Look Once, and it's an object detection system that recognizes objects more rapidly and precisely than other recognition systems. It was created by Alexy Bochkovskiy, Chien-Yao Wang, and Hong-Yuan Mark Liao.YOLOv4 identifies both seen and unseen objects in a single enclosure and it is twice as fast as EfficientDet. It is mostly used throughout cameras for real-time detection but is also used for single captured moments for analysis. Completely based on CNNs, YOLOv4 has about 137 layers within its programming.

When given an image, YOLOv4 divides the image into regions and predicts bounding boxes and probabilities for each region. By doing this, it converts the image into an S x S grid and holds each grid cell responsible for predicting the object centered in that cell. The confidence of each cell is scored and reflects how confident the model is in determining the overall object. 

There are three parts to YOLOv4: the Backbone, the Neck, and the Head. The backbone is CSPDarknet53, which is a unique backbone that augments the learning capacity of the CNN model. CPSDarknet53 employs a CSPNet strategy to partition the feature map of the base layer into two parts and then merge them through a cross-stage hierarchy. The neck, which is composed of a spatial pyramid, pools additional modules and a PANet path-aggregation, its purpose is to collect feature maps from different stages of the backbone and is essentially the pipeline for all the calculations to go through. The head is composed of YOLOv4’s predecessor, YOLOv3. The head functions as the object detector region. It finds where the object might be present but doesn’t tell about which object is present in the region. So the head predicts where the desired object might be, but if the object is in a region already known and labeled, it will pass that on and not confuse the model anymore. 

For this project, we used a pre-trained YOLOv4 model and applied that to our created dataset. Doing this was the only way we could utilize this code with the hardware that we currently have, due to YOLOv4 being a heavy program. After training the model with our dataset we were able to use YOLOv4 to detect stop signs in the images provided. We also did two versions of this code. One with a batch size of 64 images for each iteration, and another with only 32 for the batch size. We found that the test with 64 images for the batch size provided a much more accurate detection, but took the longest to process. On the other hand, the test with only 32 images for the batch size was still quite accurate, but not as accurate as the other test, and only took about half the time of the other test. 
