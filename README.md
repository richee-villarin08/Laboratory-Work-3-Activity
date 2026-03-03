[#ImageDataset](https://drive.google.com/drive/folders/1SGSxJlWoKGafAp_QliqY6Tgj1oEu-0pL?usp=drive_link)


[#Laboratory Work 3 Activity](https://colab.research.google.com/drive/1PO6qKMWidP6CUo5DVqxbL0wDe0F5wZFJ?usp=sharing)


## Guide Questions (Student Reflection & Explanation) 
Students must answer the following: 
1. Dataset Preparation 
○ How did you organize your dataset in Google Drive? 
	>The dataset is organized using a subfolder-per-class structure. Inside a main directory (e.g., ImageDataset), each plant species has its own folder containing only images of that species.
○ Why is folder structure important for TensorFlow image loading?
 	>Functions like image_dataset_from_directory use the directory structure to automatically infer labels. Each subfolder name becomes a class name, and the images within are automatically mapped to that numerical index. This eliminates the need for a separate manual labeling file (like a CSV).
2. Model Training 
○ What is the role of convolutional layers in image classification?
	>Convolutional layers act as feature extractors. They use filters to scan images for patterns. Early layers detect simple edges and textures, while deeper layers combine these into complex shapes like leaf margins or petal patterns.
○ Why do we split data into training and validation sets?
 	>The training set is used to teach the model. The validation set acts as a "practice test" using data the model hasn't seen during training. This helps us monitor if the model is actually learning general patterns or just memorizing the training images.
3. Performance Analysis 
 
 ○ What accuracy did your model achieve?
	>
○ How did the number of images affect the model’s performance? 
	>Deep learning is data-hungry. A larger number of images (like the 250+ requested) provides more variations of each plant (different lighting, angles, etc.), which helps the model build a more robust mathematical representation of the class.
4. Critical Thinking
○ What challenges did you encounter while using your own dataset? 
	>Common challenges include class imbalance (some folders having fewer images), noisy data (blurry or irrelevant images), and the slow upload speed to Google Drive for large datasets.
○ How can data augmentation improve your model? 
	>
4. Application 
○ Suggest a real-world application for your trained model. 
	>
○ How can this system be integrated into a mobile or web application? 
	>

#Guide Questions (Student Explanation & Reflection) Students must answer: 
##Visualization & Overfitting 
1. What signs indicated overfitting in your first model? 
2. How did data augmentation affect validation accuracy? 
Model Improvement 
3. What is the purpose of dropout layers? 
4. Why does data augmentation improve generalization? 
Performance Comparison 
5. Compare accuracy before and after improvements. 
6. Which technique contributed most to improvement? 
Deployment & Application 
7. Why is saving the model important? 
8. How can this model be deployed in a real-world system?
