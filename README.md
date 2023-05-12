# MLFinalProjectParkinsonsVoiceCatagorization
Members:  Meadow Bradsby, Dhimiter Cobani,  Hao Yu

Problem statement: 

Parkinson's disease is the second most common neurodegenerative disorder, and is characterized by significant impairment to movement and in later stages, cognitive function[1]. Despite its prevalence and damage, errors in diagnosis can be as high as 24%.[2]  In our project we investigated a potential additional way to look for evidence of Parkinson’s disease: the sound of the patient's voice. We used the University of California Irvine's machine learning dataset on Parkinsons to attempt to correctly predict whether these vocal features indicate Parkinson's Disease. This dataset extracts features of the 195 voices recorded (such as average fundamental frequency, variations from fundamental frequency and variations in amplitude). We compared and evaluate the efficacy of three different classification algorithms, KNN,tree-based models, and SVM, in correctly predicting whether or not these voice features indicate Parkinsons.
 
Dataset https://archive.ics.uci.edu/ml/datasets/Parkinsons 

Baseline (decision_trees.ipynb): 

While we don’t have a good way to evaluate maximum performance we used logistic regression to create a baseline performance. Since this model is one of the simplest models that is appropriate for this form of data,we have deemed it to be our baseline and will evaluate the efficacy of our other models in comparison to how much value the greater complexity increases the accuracy. The accuracy was determined to be 80% with simple linear regression. 

Tuning Architecture, Regularization:

KNN (KNearestNeighborsParkinsons .ipynb): 
One algorithm we used is the K nearest neighbor algorithm(KNN). We have examined the basics of this algorithm in class but the general idea is that you calculate the distance from a datapoint to the center of a cluster established by the training data. The three possible metrics that can be used to tune this architecture are which measurement for calculating distance is used,what the k metric is and the weighting of the nearby points. We can attempt this with both the euclidean distance, which is more precise but more computationally intensive, or the “taxicab” distance which is less computationally intensive but also less precise. The k metric is the other tunable feature of this algorithm, one that defines the number of nearby points that are considered to be nearest neighbors. Too low of a value can cause high variance and too high of a value can cause high bias. [3] It was found that with the scaled data, distance weighting with euclidean distance and a number of nearest neighbors of 1 or 2 (with uniform weighting and only considering the nearest neighbor had the same accuracy) lead to an accuracy of 93.9%, a significant increase from the 80% baseline. 

Tree based algorithms(decision_trees.ipynb):

For small and medium sized dataset, good predictive performance can be achieved by tree-based algorithms. In our case the dataset was able to acheive an accuracy of 87%, a significant increase from the 80% baseline. The Shapley values can provide further information about which of the parameters contribute most to the categorization of the voices as having Parkinson’s or not, which will be very useful in understanding what the categorization means. Shapley values are a way of assigning credit or importance to each feature in a machine learning model[4]. In doing so we find that features from nonlinear measures on the sound contribute to the high predict accuracy, and maximum vocal fundamental frequency contributes the most. Features from measures of variantion in fundamental frequency are less important. 


SVM:
Another classification algorithm we plan to use is support vector machine (SVM). SVM simply works by finding a hyperplane that maximizes the distance between data points of two or more classes, in our case being Parksinsons or no Parksinsons. An important feature of SVM are support vectors which refer to data points closer to the hyperplane and these points play a critical role in positioning the plane. To maximize the distance or margin between these two classes, a loss function is used. To help optimize our SVM, we will use L1 and L2 regularization methods.

[1] Wong, S., Gilmour, H., & Ramage-Morin, P. (2014). Parkinson’s Disease: Prevalence, diagnosis and impact. Health Reports / Statistics Canada, Canadian Centre for Health Information = Rapports Sur La Santé / Statistique Canada, Centre Canadien d’information Sur La Santé, 25, 10–14. https://doi.org/10.13140/2.1.4842.9767
[2]Tolosa, E., Wenning, G., & Poewe, W. (2006). The diagnosis of Parkinson’s disease. The Lancet Neurology, 5(1), 75–86. https://doi.org/10.1016/S1474-4422(05)70285-4
[3]What is the k-nearest neighbors algorithm? | IBM. (n.d.). Retrieved April 11, 2023, from https://www.ibm.com/topics/knn
[4]Lundberg, S.M., Erion, G., Chen, H. et al. (2020). From local explanations to global understanding with explainable AI for trees. Nat Mach Intell 2, 56–67. https://doi.org/10.1038/s42256-019-0138-9 
