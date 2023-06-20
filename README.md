# ML_project_ricedata

2023.01~2023.03 머신러닝 수업 수강하며 진행한 프로젝트입니다. 

<Part 1 수행 내용>

-import all the packages needed for this notebook in one cell
-import the images. Data can be found from (downloading starts as you press the link) https://www.muratkoklu.com/datasets/vtdhnd09.php
-save the data folders "Arborio", "Basmati" and "Jasmine" in "data" folder
-take a random sample of 100 images from Arborio, Basmati and Jasmine rice species (i.e. 300 images in total)
-determine the contour of each rice (you can use e.g. findContours from OpenCV)
-plot one example image of each rice species, including the contour

[Feature extraction]

Color features (15)
-Calculate the following color features for each image, including only the pixels within the contour (you can use e.g. pointPolygonTest from OpenCV)
-Mean for each RGB color channel
-Variance for each RGB color channel
-Skewness for each RGB color channel
-Kurtosis for each RGB color channel
-Entropy for each RGB color channel
-Dimension features (6)

-Fit an ellipse to the contour points (you can use e.g. fitEllipse from OpenCV)
-Plot one example image of each rice species including the fitted ellipse
-Calculate the following features for each image (for details, see the original article)
    -the major axis length the ellipse
    -the minor axis length of the ellipse
    -area inside the contour (you can use e.g. contourArea from OpenCV)
    -perimeter of the contour (you can use e.g. arcLength from OpenCV)
    -roundness
    -aspect ratio
-Gather all the features in one array or dataframe: one data point in one row, including all feature values in columns.
-For each data point, include also information of the original image and the label (rice species). Save the data in "training_data" folder.


<Part 2 수행내용>

[Data exploration]

-Standardize the data
-Plot a boxplot of each feature
-Plot histogram of each feature, use a different color for each class
-Plot pairplot (each feature against each feature and the label against each feature)
-Discuss your findings from the above figures, e.g. can you spot features which might be very useful in predicting the correct class?
-Fit PCA using two components
-Plot the PCA figure with two components, color the data points according to their species
-Can you see any clusters in PCA? Does this figure give you any clues, how well you will be able to classify the image types? Explain.
-How many PCA components are needed to cover 99% of the variance?
-Make clear figures, use titles and legends for clarification

[Model selection]

-Select the best model for each classifier. Use 5-fold repeated cross validation with 3 repetitions (RepeatedKFold from sklearn). You can choose the hyperparameter ranges to use (i.e. from which values the best hyperparameters are selected if they are not stated below.)

-k Nearest Neighbors classifier: hyperparameter k
-random forest: hyperparameters max_depth and max_features
-MLP: use one hidden layer and Early stopping. Hyperparameters:
    -number of neurons in the hidden layer
    -activation function: logistic sigmoid function and rectified linear unit function
    -solver: stochastic gradient descent and adam
    -validation_fraction: 0.1 and 0.5
-For each classifier:
    -Report the best hyperparameter or the best combination of hyperparameters.
    -Plot the accuracy versus the hyperparameter/hyperparameter combination and highlight the best value.

<Part 3 수행내용>

[Performance estimation]
-Use the previously gathered data (again, use the standardized features).
-Estimate the performance of each model using nested cross validation. Use 10-fold cross validation for outer and
-5-fold repeated cross validation with 3 repetitions for inner loop.
-Select the best model in the inner loop using the hyperparameter combinations and ranges defined in the Part 2.
-For each model, calculate the accuracy and the confusion matrix.
-Which hyperparameter/hyperparameter combination is most often chosen as the best one for each classifier?

