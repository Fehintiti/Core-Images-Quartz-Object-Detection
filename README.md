

# Quartz Detection in Core Images using YOLOv8 and Roboflow

## Work Process

During the examination of the core images, it became evident that they were not analytically ready as described in the [Datarock article](link). Despite this limitation, I proceeded by manually cropping out tables and extraneous materials from the images, which was a time-intensive task. I attempted to automate the cropping process with an algorithm, but this approach failed due to the inconsistent pixel dimensions across the images. *(Suggestions for improvement are welcome!)*

## Roboflow Process

Following the image preprocessing, I utilized [Roboflow](https://roboflow.com/), a platform that facilitates the development and deployment of computer vision models, to annotate 919 images. The annotation process involved analyzing the lithology descriptions in the metadata associated with each drill hole to accurately pinpoint the locations of quartz. The workflow in Roboflow included the following steps:

1. **Data Upload**: Importing the core images into the platform.
2. **Annotation**: Creating bounding boxes around the identified quartz regions.
3. **Analytics**: Defining train-test split ratios for model validation.
4. **Data Generation**: Applying preprocessing techniques such as orientation adjustments, auto-resizing, and data augmentation.
5. **Model Training**: Selecting and training the model.
6. **Deployment**: Deploying the model for testing on new data.

After the annotation process, it was found that only 283 out of 919 images contained annotated quartz, representing approximately 31% of the dataset, resulting in an unbalanced dataset. Following the annotation, I trained the selected model in Roboflow. The platform provided visualizations of the Training and Loss Graphs, which demonstrated the model's performance *(see below for details)*.

## Roboflow Metrics

Subsequently, the trained model was evaluated on unseen core images, with the results available in my [GitHub repository](link).

## Ultralytics YOLOv8 Process

In addition to Roboflow, I explored the use of [Ultralytics](https://yolov8.com/#:~:text=YOLOv8%20is%20a%20new%20state,as%20a%20command%20line%20interface.)' YOLOv8, a state-of-the-art computer vision model. I downloaded the dataset, including training, test, and validation splits, along with the necessary YAML configuration file. The YOLOv8n model was then used to train the data, and the best-performing model was applied to test it on unseen data.

## Results

Analysis of the MAE (Mean Absolute Error) and loss graphs for both the Google Colab implementation and the pretrained Roboflow model revealed similar performance, with both showing a decreasing loss trend, indicative of a well-performing model. Below are the detection results for both the Roboflow and Ultralytics YOLOv8n models on unseen images:

- **Roboflow Detection**: Displays a higher detection rate.
- **Ultralytics Detection**: Allows fine-tuning of 'confidence' and 'iou' parameters for optimal accuracy.

## Conclusion

This mini-project demonstrates the potential application of data science in geoscience, specifically in the automation of core logging. The ability to automate the identification and metadata linkage of quartz minerals in core samples, bypassing the need for manual inspection, represents a significant advancement in the industry. This project is the initial step towards more accurate, automated quantitative core logging, with further research planned to enhance the precision and efficiency of this approach.

## Hashtags

#DataScience #Geoscience #MachineLearning #ComputerVision #YOLOv8 #Roboflow #CoreLogging #QuartzDetection #Automation #Ultralytics #DataAnnotation #Lithology #GitHubProjects #DataMining
