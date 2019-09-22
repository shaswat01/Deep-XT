# Deep XT
A BigRedHacks project by:
*Shaswat Rajput, Mingli Yang, Yuzhi Yao, and Ali Yaqoob*

Pneumonia is a common disease, affecting 5 million Americans per year, and is the 6th leading cause of death in the United States. Patient survival improves significantly when pneumonia is diagnosed and treated within 4 hours of the patient arriving at the hospital. And a key part of the diagnostic algorithm is accurate and timely interpretation of chest radiographs. 

- **Help radiologists improve their working efficiency.**
Our machine learning model can be a support tool to help radiologists diagnosis X-ray picture. Given the X-ray picture, our model will return the probability of most common thoracic diseases observed in chest X-rays. 
Our deep learning model can help radiologists/ doctors find the lesions that are hard to find by eyes.
- **Reliable computer diagnosis of pneumonia can help with patients in underserved or remote areas**
For patients in remote or rural areas, access to a clinic or small hospital with basic x-ray machinery is relatively available.
 It can still be difficult for those patients to have their images interpreted within the preferred 4-hour window. 


## Part 1

**Aims:**
1. To  reduce the time it would take for a doctor to analyze patient lung x ray scans. 
 It recognizes first whether the the x-ray being examined is _healthy or un-healthy_ . 
2. Then it checks whether the x-ray shows, with reasonable accuracy:
 + **Atelectasis** - is a complete or partial collapse of the entire lung or area (lobe) of the lung. It occurs when the tiny air sacs (alveoli) within the lung become deflated or possibly filled with alveolar fluid. Atelectasis is one of the most common breathing (respiratory) complications after surgery.
 + **Infiltration** - is a pulmonary infiltrate is a substance denser than air, such as pus, blood, or protein, which lingers within the parenchyma of the lungs.
 + **Effusion** - is the condition of accumulation of fluid in an anatomic space, usually without loculation. 
 
We do this by creating two image classification models using IBM Watson's Core ML. We do this by training the first model to differentiate between a healthy and a diseased lung and the second model to differentiate between three common lung conditions: atelectasis, infiltration and effusion. 

**Challenges:**
The original data had 16 image classifications and each image had the possibility of being labeled by two labels. For example, an x-ray could show carteglamy and effusion. We decided, because of the time constraint of our project, that it would be best to take the most common diseases and help develop an algorithm to quickly identify between three different types of diseases. This can be improved with further training and more accumulation of data. 


## Part 2

**Aims:**
1. Detect lesions from CT Images. Lesions are cancerous areas in the cells that are not visible to eye on CT Scans of different organs. 
2. Detect the location of the lesion and display it in a way that helps the physician identify its most probable location. 

To do this we used a U-Net Network, which is a convolutional neural network that was developed for biomedical image segmentation. The network is based on the fully convolutional network and its architecture was modified and extended to work with fewer training images and to yield more precise segmentations.

- **Model Stats**
Highest accuracy Achieved at **35th epoch**
- **Loss:** -0.0467
- **Binary Accuracy:** 92.2%
- **True Positive Rate:** 63.43 %
- **Validation Binary Accuracy:** 88.72%
- **Validation True Positive Rate:** 57.44%

**Challenges:**
1. Determining what deep learning model to use on the type of data we were to work with. 
2. Normalizing for the images in the data to be the same size. 
3. Radius of the legion was not explicitly mentioned and had to be calculated.
4. The x, y and z location variables of the lesion were to be extracted from a single column in the dataset.
5. Not being able to establish pipelines between other parts of the projects. 


 **References:**
 1. [NIH Clinical Center provides one of the largest publicly available chest x-ray datasets to scientific community](https://www.nih.gov/news-events/news-releases/nih-clinical-center-provides-one-largest-publicly-available-chest-x-ray-datasets-scientific-community)
