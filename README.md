# Classification of Tennis Movements Project

This project was developed in Google Colab environment in Fall Semester 2024 and aims to perform learning-based classification by analyzing the movements of tennis players in videos through skeletal data. Its main purpose is the automatic classification of movements (Backhand, Forehand, Serve).

## General Purpose of the Project

Analyzing various hitting positions of tennis players (backhand, forehand, serve) through video data

Extracting skeleton keypoints with MediaPipe

Classification with deep learning models (3D CNN + LSTM)

Applying operations such as feature extraction, data balancing, feature reduction (PCA, LDA), data augmentation

Technologies and Libraries Used

The project was developed in Python language and Google Colab environment. OpenCV was used for video processing, MediaPipe for skeleton extraction, NumPy and Pandas for data processing. In the modeling phase, 3D CNN + LSTM architecture was built with TensorFlow/Keras, various machine learning techniques were applied with scikit-learn, data balance was achieved with imbalanced-learn and visualization was done with Matplotlib/Seaborn.

## Project Phases

 Data Preparation: Videos are in .avi format. Skeleton data was extracted every 10th frame. 3D coordinates of 33 points were obtained using MediaPipe. Data was saved in CSV and NPY formats.

 Data Preprocessing: Skeleton data were vectorized. Tagging was done from file names. Data augmentation techniques were applied, data balancing with SMOTE and normalization with MinMaxScaler.

 Feature Extraction and Dimensionality Reduction: PCA and LDA methods were used. All frames were transformed into a 33x33x3 tensor structure.

 Modeling: 3D CNN was used to extract spatial features and LSTM was used for time series relations. The model was tested with 10-fold cross validation. Alternatively, classical algorithms such as SVM, Random Forest, KNN and GBM were also applied.

  Performance Statistics

The accuracy of the model is above 90%. The F1 score ranged between 0.88 and 0.92. Precision, recall and AUC ROC values were calculated. The complexity matrix was used to analyze the level of confusion of the movements.

## Data Set Used

In this project, an open source dataset called THETIS Dataset was used. This dataset contains various strokes of tennis players, captured from the side and from above. The movements are categorized as backhand2h, foreflat and serflat. For more information: https://github.com/THETIS-dataset/dataset

## Learned

Efficiency of 3D CNN + LSTM architecture for motion classification

Benefits of skeleton extraction with MediaPipe

Impact of data augmentation

The roles of PCA and LDA in dimensionality reduction have been learned
