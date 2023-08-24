## objective
The objective of this project is realize supervised classification for dataset ‘heart’ with deferent
learning algorithms such as MLP classifier , RBF networks and Self-Organizing Maps (SOMs), for
classification tasks.

## Data Processing for classification
Let's prepare our input data. We went through the following stages:

Phase 1: 
visualize the summary statistics after loading the data.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/9be0f5da-af52-4187-8e57-4183fe9f87f7)

Phase 2:
Separate labels that will be predicted from the data we have in the shape of (303,14) for training and (303,1) for testing.

hase 3: 
Divide the data by 25% for testing and 75% for training, resulting in 277 and 76 samples.
Phase 4: 
The data are scaled using the sklearn StandardScaler() function Each feature is scaled by the StandardScaler() function . This keeps features with bigger scales from overwhelming the other features and ensures that each feature contributes evenly to the model.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/45135b35-7e4e-49ba-87e4-4591cd16b010)

Phase 5: In Graph, you may see test and train data.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/59f48935-4214-4463-9854-e32318dbabc3)
![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/8f2f3d3a-93aa-4ffc-8e11-29666d5c5291)

##Create and fit Models
MLP(multi-layer perceptron):
We created our mlp classifier from MLPClassifier class from the sklearn.neural_network module.the MLPClassifier class implements a multi-layer perceptron (MLP) neural network for classification. the MLP has three hidden layers with 10, 12, and 13 neurons, respectively. for the maximum number of iterations that the MLP can run for during training. it is set to 10000.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/85211273-6cfb-4add-bda6-f59e11093ae5)


RBF:
The model is kears model will be start with rbf layerinitialized with centers found using K-Means clustering on the training data . The network has several additional dense layers with different activation (‘relu’, ‘sigmoid’ ) functions and a final output layer with a sigmoid activation function. number of epoch is 1500.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/ae8cbd8a-6f62-4b84-aca9-7894d3fd308c)

SOM (Self-Organizing Map):
The SOM is initialized with 10 rows, 10 columns, and the same number of input features as the training data. For 100 iterations, the SOM model trains the SOM. the winner neuron is identified using the winner method for each training sample in X_train, and a black circle is plotted at the center of the corresponding neuron in the SOM grid.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/75a1d5f4-7ef4-410d-9a8b-a55a4f52553b)

After creating the Classifiesr objects, the .fit() method is called on the standardized training set X_train and the correspon

## Models Evaluation:
For model comparison and evaluation.  The confusion matrix for the predictions made by the trained models, as well as the accuracy of each model, are created in a plot that contrasts the predicted class labels (predictions) with the actual class labels for the testing set.

![image](https://github.com/ChelghoumMohammedWassim/RBF-MLP-SOM/assets/101805975/7954cd26-c1ea-4781-a463-f356a1dd6475)

## Conclusion
In conclusion, we point out that the rbf model, which has an accuracy of 84% and 11 errors out of 76 samples, is the best model for this dataset. Close results include rbf and mlp. On the other hand, the som map, which is accurate to 74% and has 58 errors out of 227 samples, represents the weakest model.



