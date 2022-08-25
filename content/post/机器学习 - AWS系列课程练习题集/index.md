---
title: Machine Learning - AWS series of course exercises
subtitle: This post is a set of exercises for AWS machine learning.

# Summary for listings and search engines
summary: This post is a set of exercises for AWS machine learning.

tags: 
- Machine Learning

categories: 
- Machine Learning

date: '2022-08-13'

math: true
---
This post is synchronously published on my CSDN blog:
https://blog.csdn.net/weixin_45766278
### [Module 2 - Introducing Machine Learning]

1. Machine learning is **scientific research on Algorithms and statistical models, which relies on reasoning rather than instructions to perform tasks**
2. **reinforcement learning** take actions that can obtain the maximum reward through interaction with the environment and learning
3. Create a machine learning solution for the call center. The system template is to transfer customers to the appropriate departments (there are eight possible departments in total)
This scenario describes the **multi category classification problem**
4. The system needs to respond to environmental changes to improve performance: **reinforcement learning**
5. In the **data preparation** stage of the machine learning pipeline, whether the design verification data are all of the same type
6. The data of multiple countries or regions are listed in the order of abbreviations and subtitles. Which stages involve converting these abbreviations into numerical values: **data preparation**
7. If a model performs well on the training data but performs poorly on the evaluation data, it belongs to the overfitting model **Correct**
8. Which resources are Python libraries used to deal with machine learning problems: **pandas, scikit learn**
9. Which Amazon service can be used to deploy machine learning instances and run jupyter notebooks: **Amazon Sagemaker**
10. What are the requirements for selecting machine learning as the development method: **large data sets containing a large number of variables**

### [Module 3 - Implementing a Machine Learning pipeline with Amazon SageMaker]

1. What resources help define machine learning problems: **access to marked data, domain experts to consult**
2. What attributes should the data prepared for monitoring classification learning have: **the data should be marked and the data should be the representative of production data**
3. What can be found by checking data statistics: **abnormal data found**
4. How to split training data for a preprocessed data set that can be used for training model: **80% is used for training, and the rest is split into test data (10%) and verification data (10%)**
5. Mechanical energy single model and multi model can be managed through Amazon sagemaker **Correct**
6. Role of confusion matrix: **show true false positive and true false negative**
7. What does the correlation Heatmap show: **correlation degree (positive correlation / negative correlation) between data set characteristics**
8. Which of the following file formats does pandas support importing data: **JSON, CSV**
9. Which Amazon service is used to deploy the machine learning instance and run the jupyter Notebook: **Amazon Sagemaker**
10. What is the goal of Amazon sagemaker super parameter tuning job: **optimize model parameters to generate the best model**

### [Module 4 - Implementing a Machine Learning pipeline with Amazon SageMaker]

1. What are the common patterns in time series data: **trend and seasonality**
2. Which use cases are suitable for prediction: **predict the necessary inventory of goods in the warehouse and predict the energy consumption of the Office**
3. Which data sets can be used as time series data sets (**core: including time**): **sales data including goods, purchase date and quantity; Web log with IP address, page and timestamp**
4. For the data set of temperature readings of a weather station (recorded every 5 minutes), several values are missing every day. What countermeasures can be taken: **fill the missing values forward / backward**
5. Which scenarios show appropriate downsampling examples: **use the mean function to convert the temperature reading per minute into an hour system; Use the sum function to convert the sales order information of the current day into the daily total**
6. What seasonal examples can be observed in the time series data: **every quarter, every year, spring, summer, autumn and winter**
7. Amazon forecast generates P10, P50 and P90 prediction results. If you use Amazon forecast to forecast the sales volume of shoes and boots, you can learn what information through P10, P50 and P90 (**core: P value indicates the percentage of true value will be lower than the predicted value**) **P10 indicates that the order volume is less than the predicted value within 10% of the time**
8. What data sets (**core: time series**) are needed to generate retail forecasts using Amazon forecast: **time series data including time stamps, goods and quantities**
9. What steps should be performed to generate the best model using the available data: **use pandas to split the data into training data sets and test data sets by time; Use the training data set in Amazon forecast by specifying the back test window; Test data sets are used to compare predicted and actual values**

### [Module 5 - Introducing Computer Vision (CV)]

1. What are the common use cases of computer vision: **image analysis, face recognition, family safety**
2. What is the object position in the image: **bounding box**
3. What functions does Amazon rekognition provide: **search for images and video libraries, identify faces, and perform Emotional Analysis on images**
4. When Amazon rekognition performs prediction, it also provides a score indicating the confidence of prediction **Correct**
5. What will Amazon rekognition do to the results after completing the video analysis: **publish the results to Amazon SNS queue**
6. What functions does Amazon rekognition custom labels have: the UI for marking images and defining bounding boxes **Automatic selection of machine learning algorithm**
7. To use Amazon sagemaker ground truth to automatically mark data, the minimum number of images required is **1250**
8. What is the confusion matrix: **determine the accuracy of the model in classifying objects**
9. What types of data are included in the Amazon sagemaker ground truth manifest file: **confidence value, creation date, and class name**
10. Which of the following steps are used to prepare custom data sets for object detection: **collect images and train models**

### [Module 6 - Introducing Natural Language Processing]

1. Which of the following is not the main challenge of natural language processing (NLP): **storage limitation**
2. What are the common preprocessing tasks of NLP applications: **eliminate noise and normalize similar words**
3. NLP appeared earlier than machine learning system **Correct**
4. What are the common machine learning models for NLP applications: **word bag, word frequency and inverse document frequency**
5. Which of the following does not belong to the text analysis category: **AutoCorrect text**
6. What functions does Amazon transcribe support: **convert streaming audio into text; Build multilingual subtitles**
7. How can I change how Amazon Polly pronounces words: **add speech synthesis markup language (SSML) tags to text**
8. Which functions belong to Amazon comprehensive: **identify the language used in the document; Identify the emotions contained in the document (positive, negative, neutral, or mixed)**
9. Which of the following AWS services can be used to start the workflow according to the input of Amazon Lex chat robot: **Amazon lambda**
10. When working for a company that builds applications for global audiences, what services can be used to analyze how customers use applications: **Amazon comprehensive, Amazon translate**