# Melanoma-Identification-with-Convolutinal-Neural-Networks

![Melanoma statistics](https://user-images.githubusercontent.com/113449546/206875921-e3fca595-13f7-41e3-9236-613555065715.jpg)

### Business Understanding
![8211-Skin_Cancer-_Facts_Statistics_and_You-1296x1270-Infographic-5](https://user-images.githubusercontent.com/113449546/206876845-59adf0c7-6f1b-4de2-b83d-4f9111612840.jpeg)

Skin cancer is the most common form of cancer in the United States. There are an estimated 9,500+ new diagnoses per day in the United States with an optimistic 99% cure rate. There are three types of skin cancer, Basal Cell Carcinomas (BCCs), Squamous Cell Carcinomas (SCCs) and Melanomas. Although all 3 must be surgically removed, BCCs and SCCs have slim to no chance of being fatal. Melanoma is the only form that has the capability to metastasize throughout the body and has a high probability of being lethal if not discovered early enough. 

![image](https://user-images.githubusercontent.com/113449546/206876294-217e3e37-f5a2-45bb-9e99-838fccd4a350.png)

While there are the basic ABCDE rules for identifying Melanoma, they do not encompass their complexity and diversity in presentation, and can even appear like a regular mole. Dermatologists use Dermatoscopes for better clinical evaluation and advise patients with increased risk of Melanomas to go to MoleSafe, where a full-body 3D scan evaluates all lesions on your body and can be used as a clinical aide. MoleSafe has been an incredible advancement in the treatment of skin cancer as doctors do not have to solely rely on their own eyes to properly diagnose. Although, giving a Dermatologist similar capabilities in the exam room would only lead to earlier detection of Melanoma and therefore improved patient outcomes. 

### **Stakeholder: Dermatoscope manufaturers**

Although MoleSafe has plenty of benefits, it is time-consuming and expensive (~$500) for a personal scan as insurance does not cover it. Effectively, MoleSafe is only used as a tool for those with extreme risk of Melanoma due to its cost. While it has undoubtedly saved many lives, I believe its limited use still means there are ways to improve early detection. I set out to create a neural network that could do the same evaluation as MoleSafe, but to be used inside a Dermatoscope while the doctor is in the room with the patient. The doctor would then have a live version of MoleSafe to be used as a clinical aide in their diagnosis. 
<img width="473" alt="Screen Shot 2022-12-10 at 4 51 17 PM" src="https://user-images.githubusercontent.com/113449546/206876611-9f3bde54-2f20-4f9c-b730-e2e4ef94b681.png">

### Dataset

I used the International Skin Imagining Collaboration 2019 Dataset from Kaggle which has 25,331 images of 8 different skin lesion types viewed through a dermatoscope. 
  > ![Skin_Cancers](https://user-images.githubusercontent.com/113449546/206876418-e96a331d-71c3-4ae1-b5e7-0d640f5325ca.jpg)

I ultimately decided to narrow my image classification down to differentiating between Melanomas (4,577) and benign moles (9,755). 
  > ![Mole v Mel w titles](https://user-images.githubusercontent.com/113449546/206876140-d33ae1e4-b955-47f1-a0bd-5a9d30e0dcc7.jpg)


### Modeling

The images were scaled and reshaped and then split into a train (9,550, 66.7%), validation (1,382, 9.6%) and test (3,385, 23.6%) sets and classified via a Convolutional Neural Network.

Throughout the modeling process I was concerned with both accuracy and recall, with a priority on recall. Obviously we want to get the correct diagnoses from the image, but I also wanted to focus on minimizing missing any possible melanoma diagnoses.

A one layer CNN was used as a baseline for the model. From there, dropouts, regularizers, optimizers, different augmentations and overall architecture of the network were manipulated to improve results.

### Evaluation

The final model's results are displayed below.

  > Recall: 83.1%

  > Accuracy: 77.9%

![Accuracy](https://user-images.githubusercontent.com/113449546/206875969-79c11ab7-5f4e-423e-9348-b34c7cd3b5fb.jpg)

![Recall](https://user-images.githubusercontent.com/113449546/206875966-b24fe8ac-1474-4769-a74c-1eee4691313b.jpg)


### Conclusion

**Model Performance**

While the results did improve throughout the modeling process once significant augmentations were applied, with the seventh model displaying the best balance of recall and accuracy, the model still could be improved. Ultimately, I would have liked to try applying different combinations of augmentations but the sheer size of the dataset limited some of those capabilities.

**Model Value and Limitations**

Even though the model could still be improved, I do believe the idea has significant clinical value. As the dermatolgoist is evaluating any lesion, they could use not only the dermatoscopic view but the algorithm as an aide in their diagnosis. 

Implementing the model on a larger, clinical scale requires much more complex image classification as there are multiple types of skin cancers and hundreds of different types of lesions. As well, this model only takes into account simple photos, where there is clearly one defined lesion, and does not encompass the possible complexities of clinical evaluation. 

### Next Steps

  - Be able to compound image evaluation with important factors like age, sex, body location and past skin cancer history

  - Only a subset of diagnoses analysed

  - Can only handle simple photos with one lesion in the area
  
![inc_anatomicalsite_melanoma_skin_as18](https://user-images.githubusercontent.com/113449546/206876647-ffca0e38-2ebd-4e65-bb2c-2fad45a927ca.jpg)

# Repository Structure
    ├── Photos
    ├── .gitignore
    ├── Binary Classification.ipynb
    ├── Melanoma Identification Slides.pdf
    └── Preprocessing.ipynb
    └── README.md
