[#ImageDataset](https://drive.google.com/drive/folders/1SGSxJlWoKGafAp_QliqY6Tgj1oEu-0pL?usp=drive_link)


[#Laboratory Work 3 Activity](https://colab.research.google.com/drive/1PO6qKMWidP6CUo5DVqxbL0wDe0F5wZFJ?usp=sharing)


[#Laboratory Work 3 Activity Colab](https://colab.research.google.com/drive/1PO6qKMWidP6CUo5DVqxbL0wDe0F5wZFJ?usp=drive_link).


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
	
	>This technique artificially expands your dataset by flipping, rotating, or zooming into existing images. It forces the model to be less "picky" and prevents it from focusing on irrelevant details like the orientation of an object.

5. Application 

○ Suggest a real-world application for your trained model. 
	
	>This model could be used for quality control in manufacturing (detecting defective parts) or a mobile app for plant identification to help gardeners identify pests.

○ How can this system be integrated into a mobile or web application? 
	
	> Web: Use TensorFlow.js to run the model directly in a browser or host it as an API (using Flask or FastAPI) that a website calls to get predictions.

#Guide Questions (Student Explanation & Reflection) Students must answer: 

##Visualization & Overfitting 

1. What signs indicated overfitting in your first model? 

	>In the first model, the clearest sign of overfitting was a significant divergence between the training and validation curves. While the training accuracy continued to climb toward 100%, the validation accuracy typically plateaued or even began to decrease. This was mirrored in the loss plots, where the validation loss began to rise even as the training loss dropped, indicating that the model was memorizing the specific noise of the training data rather than learning general patterns.

2. How did data augmentation affect validation accuracy? 

	>Data augmentation typically increases validation accuracy and narrows the gap between training and validation performance. By showing the model modified versions of the same image (flipped, rotated, zoomed), the model can no longer memorize specific pixel coordinates. This forces it to learn the actual "features" (like shapes or colors) of the object, leading to better performance on new, unseen data.

##Model Improvement 

3. What is the purpose of dropout layers? 

	>The purpose of Dropout is to prevent co-adaptation of neurons. During training, it randomly "turns off" a fraction of neurons (in your code, 30% or $0.3$). This forces the network to find multiple independent pathways to solve the problem rather than relying on a few specific "expert" neurons. It acts as a form of regularization that prevents the model from becoming too complex and memorizing noise.

4. Why does data augmentation improve generalization? 

	>It improves generalization by artificially expanding the size and diversity of the training set. In the real world, an object won't always be perfectly centered or upright. By simulating these variations during training, the model becomes "invariant" to those changes, meaning it can recognize a cat whether it's facing left, right, or is slightly tilted.
##Performance Comparison 

5. Compare accuracy before and after improvements. 

	>Before the improvements, the model likely exhibited high training accuracy but significantly lower validation accuracy, which is a classic sign of an overfit model. After implementing data augmentation and dropout, the training accuracy might rise more slowly or stay slightly lower, but the validation accuracy improves and tracks much more closely with the training results. This result indicates a model that is more balanced and reliable for real-world use.

6. Which technique contributed most to improvement? 

	>This often depends on the dataset, but Data Augmentation usually provides the biggest boost for image classification. It addresses the root cause of overfitting (lack of data variety), whereas Dropout acts as a secondary safety net to keep the internal weights of the model in check.
##Deployment & Application 
7. Why is saving the model important? 

	>Saving the trained model is essential because the training process is computationally intensive and time-consuming. By using the model.save function, you can preserve the learned weights and reuse them instantly for future predictions without needing the original training data or a powerful GPU. This also ensures portability, allowing the classifier to be moved from a development environment to a production server or a mobile device.

8. How can this model be deployed in a real-world system?
	>A saved model can be integrated into various real-world systems, such as web applications that use an API to classify images uploaded by users. It can also be converted for use in mobile apps via TensorFlow Lite for real-time camera recognition or implemented in industrial automation systems. In a factory setting, for example, the model could be used to automatically identify and sort products on a conveyor belt using a high-speed camera feed.
