# Detection-of-IoT-Botnet-Attacks

Abstract

This project of Detection of IoT Botnet Attacks was done using just the Jupyter notebook with no other external environments required.
It requires basic libraries like Tensorflow, SciPy (a scientific computation library) , Scikit-learn, OpenCV to read the CSV datasets, Pandas and Keras for the models, layers and callbacks. These can be imported with ease on the  Google Collab Notebook.

Methodology
We extracted 115 traffic statistics and split the dataset in the ratio 80:20 (train: test)
Next we trained an Anomaly Detector and used a threshold value to detect the anomaly of the network. 
3 proposed neural networks Hyperbolic tangent activation function for hidden neurons, Softmax function to the last layer and Categorical cross-entropy as a loss function is used for the attack classification to classify which type of attack is occurring i.e.Botnet attack type or the Mirai attack(SCAN, ACK, SYN, UDP, UDPPlain) type classification.

Python dependencies
The python dependencies are listed in `requirements.txt` file and have to be installed.

Download the dataset

Use `download_data.py` script

Then extract rar files into respective `{device_name}/gafgyt_attack/` and `{device_name}/mirai_attack/` directories

Run the training and evaluation script.

train.py

You can specify if you just want to use just top N features by passing an argument.

train.py 5

Run just the test for the existing model

As input give it the top number of features to use and the name of the model to load

test.py 5 'model_5.h5'

Results

For all features, trained for 20 epochs for 42 mins.
Results are:

Model evaluation

Loss, accuracy
[0.0010332345978360195, 0.9998208877454652]

So, accuracy on test set is 0.99982

Confusion matrix

Benign     Gafgyt     Mirai
[[111369    114      2]
 [    34 567253      7]
 [     9     87 733647]]

For top 5 features, trained for 5 epochs
Loss, accuracy 
[0.004696070021679117, 0.9991879772492039]

Confusion matrix
Benign     Gafgyt     Mirai
[[111436     40      9]
 [   647 566647      0]
 [    63    388 733292]]

For top 3 features, trained for 5 epochs, 99s per epoch
Loss, accuracy 
[0.0032474066202494442, 0.9994704507257232]

Confusion matrix
benign  gafgyt  mirai
[[111439     40      6]
 [   460 566834      0]
 [    80    162 733501]]

For top 2 features, trained for 5 epochs, 99s per epoch
Loss                   Accuracy
[0.33539704368039586, 0.8430219139947991]
Confusion matrix
benign  gafgyt  mirai
[[ 58989  52297    199]
 [   523 436574 130197]
 [   486  38033 695224]]
The folder ‘Jupyter’ has all the main notebooks where we have estimated the above mentioned details of the project and the folder ‘Modals’ in ‘Jupyter’ consists of all the dataset used for the anomaly detection.

Figures

Filename

Fig 1: Autoencoder Training Curve                       jupyter/anomaly.ipynb

Fig 2: Attack detection on test data set                jupyter/anomaly.ipynb

Fig 3: Botnet classification learning curve             jupyter/botnet_type.ipynb

Fig 4: Botnet classification confusion matrix           jupyter/botnet_type.ipynb

Fig 5: Mirai attack classification learning curve       jupyter/mirai_attack_type.ipynb

Fig 6: Mirai attack classification confusion matrix     jupyter/mirai_attack_type.ipynb

Fig 7: LIME explanation for attack detection            jupyter/anomaly.ipynb

Fig 8: LIME explanation for botnet classification       jupyter/botnet_type.ipynb

Fig 9: LIME explanation for Mirai attack type UDP       jupyter/mirai_attack_type.ipynb

The dataset used for the analysis is: https://archive.ics.uci.edu/ml/machine-learning-databases/00442/
