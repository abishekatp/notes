# Getting Started
Deep learning has power, flexibility, and simplicity. That’s why we believe it should be applied across many disciplines. 

## Goal
- Build and train deep learning models for computer vision, natural language processing, tabular analysis, and collaborative filtering problems
- Create random forests and regression models
- Deploy models
- Use PyTorch, the world’s fastest growing deep learning software, plus popular libraries like fastai and Hugging Face


## Tools
- Pytorch - works best as a low-level foundation library, providing the basic operations for higher-level functionality.
- Fastai - adding this higher-level functionality on top of PyTorch.
- Transformers - focused on natural language processing (NLP) using transformers models
- Jupyter Notebook - is the most popular tool for doing data science in Python.


## Machine Learning Vs Deep Learnin
- **Deterministic Computation**
    - ```Input -> Program(Deterministic set of instructions) -> deterministic output```
    - Most of the software we wrote so far will come under this category.
    - All the functions and methods we wrote will take some input, compute based on some deterministic logic and give an output.
- **Probabilistic Computation**
    - ```Input -> Model(Deterministic set of instruction with probabilistically trained weights) -> probabilistic output```
    - Machine Learning or Deep Learning Models take input, do some mathematical computations and give some output number. 
    - The output number will be used probabilistically to describe out desired outputs.

### Machine Learning(Manual Feature Detection)
- This approach was slow because we needed to label the features explicitly and use them as input while training a machine learning model.
- In future, if we want to make prediction, then we have to provide these features for our inputs
- Sometimes we needed hundreds of such features based on the complexity of the task.
- For example, if you train a machine learning model to predict bird image, then you have to define features like mouth, legs, body, surrounding, bird location on the image, etc.

### Deep Learning or Deep Neural Networks(Automatic Feature Detection)
- We feed in the inputs and model detects patterns or features in the input to make an accurate prediction. 
- When researchers took a computer vision model and drew a pictures of their weights, each set of weights actually worked together to find a specific feature of a image. 
- They automatically adapted to this technique to predict the correct final output.
- We only needed to lebel the images as bird image or not. The neural network was able to locate birds coordinates and spot the patterns to predict whether an image is bird image or not.
- If the first layer of the deep neural network detects small features like edges or colors, then the next layer combined those features to detect more visible patterns. As we go deeper other layers learn to recognise the patterns like part of the bird or other objects in the image.
- In future, if you have some new image, then we can just imput that image to the model and the model will tell whether that image is bird image or not.


## Deep Learning Traning Process
- **Data Preparation:** First prepare the input data. 
    - Clean it to match our purpose.
    - Label them based on what we want to predict.
    - Neural network modesl can only accepts numbers as input. The output also will be a number. 
    - So input should be converted to number and output should be again converted back to our desired format.
- **Data Split:** Split the data into training and validation(testing) set.
    - Using this testing data we could find whether model is over fitted to the training data. 
    - If it works perfectly for training data and performs worstly, then it is overfitted.
    - If it performs worstly for both training and test data, then model is not properly trained at all.
- **Model Selection:** Select a suitable model for our use case.
    - While choosing the model we can use already pretrained model and fine tune it for our specific set of inputs.
    - For example, a model which already has general idea about how process images can be easily trained to predict specific type of image task like detecting a bird image.
    - Also each type of task can be done by different kind of model which specialises in them.
- **Model Training** Choose a suitable training and testing method
    - **Loss Calculation** Loss tells how correct the model prediction is. This will be some probabilistic value.
    - **Weight Updation** Based on the loss each weight of the model will be adjusted to minimise the loss.

- **Deploy:** Optimise and deploy the model for the prediction.

- **A Few Applications**
    - **Computer Vision** Image recognition, Image Segmentation(Sement different parts of the image based on characteristics of each object), etc.
    - **Tabular Data Analysis** For realestate predictions, financial data analysis, Collaborative Filtering(recommendation systems - core idea is that people who agreed in the past will agree again in the future), etc.
    - **Natural Language Processing** Speech recognition, Lanagage Translation, Document Summarisation, etc.