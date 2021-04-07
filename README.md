# DDoS-detection-with-DeepLearning

Work : DDoS attack detection using Deep learning models with feature selection with Random Forest.  
Work Flow  diagram:   



![fig4](https://user-images.githubusercontent.com/52536269/113823493-895bfa00-97a0-11eb-8e18-e8d72860355b.png)  Fig: Complete work diagram of DDoS detection  
For my work I have chosen the Monday working hours sample from the main dataset which mainly focuses on the DDoS attack network traffic.  
Code Description:
1.	First necessary libraries were imported followed by loading the dataset in a Pandas dataframe. The dataset was then checked for null and infinite values.(Code cell 1-4)

2.	There were some infinite values in the dataset.Those values were converted to null and then those rows were removed.(code cell 16-17)
3.	‘Benign’ label was re labeled as 0  and DDoS attack labels were made as 1.(Code cell 18)
4.	Then  the dataset was checked for imbalance and it was found that that were a 1.75: 1 ratio between the majority and minority classes .(Code cell 19)
5.	Random under-sampling was performed for making the dataset balanced.(Code cell 20). Bar charts are also plotted  before and after performing under-sampling. 
6.	The feature named ‘’Desnitation Port ” bears no resemblance to the actual classification. This feature was removed from the dataframe. Then using sklearn the label was encoded.(Code cell 21)
7.	Using sklearn library the dataset was split into training and test dataset. 20% of the data was used for testing.(code cell 22)
8.	Using RandomForestClassifier from sklearn, the data was fit in a Random Forest for calculating feature importances. The features having feature importance less then 0.005 were discarded. The indexes of those selected features are shown and feature importance values are plotted as bar chart.(code cell 24)
9.	Now that the preprocessing and feature extraction is complete the modified dataset is trained in an Multi Layer Perceptron model .Keras was imported and used for this work.In the MLP , relu activation function was used in the hidden kayers followed by sigmoid activation function in the output layer. Binary crossentropy was used as loss function.(code cell 36)
10.	K fold cross validation is performed and accuracies in each  fold is shown.(37-38)
11.	The MLP model was trained separately while plotting loss and performance during training.(39)
12.	Perf_measure function is defined to calculate true positive,true negative,false positive and false negative values.(code cell 40)
13.	Finally the trained model was used for making independent classifications on the training dataset.(code cell 50)
14.	Performance of the model was graphically represented with confusion matrix and ROC curve (code cell 51,52 and 58)
15.	A 1d Convolutional Neural Network is then designed and trained on the training dataset and performance tested on the test dataset as was done like the MLP model. Confusion matrix and ROC curve are plotted for the graphical representation of the CNN model’s performance as well. (Code cell 56)  
Publication on this work: https://doi.org/10.1007/978-981-33-6835-4_8


