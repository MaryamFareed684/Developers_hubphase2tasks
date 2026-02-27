Multimodal Housing Price Prediction (Images + Tabular Data)
 Objective

The objective of this project is to build a multimodal machine learning model that predicts housing prices using:

Structured tabular data (housing features)
House images

Unlike traditional regression models that use only numerical features, this project combines image features extracted using a Convolutional Neural Network (CNN) with structured housing data to improve prediction performance.
This project demonstrates the implementation of multimodal learning, feature fusion, and regression modeling using deep learning.

Dataset
The project uses:
Housing Sales Dataset (CSV)
Contains structured features such as:

Median income
Total rooms
Housing age
Ocean proximity

Other housing-related attributes
Target variable: median_house_value
Custom Image Dataset
One image per house
Images are resized to 224x224
Preprocessed for ResNet50

Methodology / Approach
The model follows a two-branch multimodal architecture:
Tabular Data Preprocessing
Removed missing values
Separated features and target variable

Applied One-Hot Encoding for categorical feature (ocean_proximity)
Scaled numerical features using StandardScaler
Split dataset into training and testing sets (80/20)

Image Processing
Uploaded and extracted image dataset
Renamed images to match dataset row indices
Resized images to 224×224
Applied preprocess_input() for ResNet50

Loaded images into NumPy arrays
Image Feature Extraction (CNN Branch)
Used pretrained ResNet50 (ImageNet weights)
Removed top classification layer (include_top=False)
Froze pretrained weights (trainable=False)

Applied:
GlobalAveragePooling2D
Dense(128, ReLU)

This branch extracts high-level visual features from house images.

Tabular Branch
Dense(128, ReLU)
Dense(64, ReLU)

This branch processes structured housing features.

Feature Fusion (Multimodal Learning)
Concatenated image features and tabular features
Passed through:
Dense(128, ReLU)

Final Dense(1) output layer

The model predicts a continuous value (house price), making this a regression problem.
Model Compilation & Training

Optimizer: Adam
Loss Function: Mean Squared Error (MSE)
Metric: Mean Absolute Error (MAE)
Epochs: 10

Batch Size: 32

Validation split: 10

Model Evaluation
The model was evaluated using:
MAE (Mean Absolute Error)
RMSE (Root Mean Squared Error)

Final Results:

MAE: 156,545

RMSE: 186,712

 Key Observations
The multimodal architecture successfully integrates image and tabular features.
Image features were extracted using transfer learning (ResNet50).
Model performance indicates that prediction error is still relatively high.

Possible improvements:

Increase number of epochs

Fine-tune ResNet50 layers

Use data augmentation

Increase dataset size

Apply regularization techniques

Skills Demonstrated
Multimodal Machine Learning
Convolutional Neural Networks (CNNs)
Transfer Learning (ResNet50)
Feature Fusion (Image + Tabular Data)

Regression Modeling

Model Evaluation (MAE, RMSE)
Data Preprocessing & Scaling

Deep Learning with TensorFlow & Keras

Technologies Used
Python
TensorFlow / Keras
OpenCV
NumPy
Pandas
Scikit-learn
Matplotlib

Project Structure (Suggested)
Multimodal-Housing-Price-Prediction/
│
├── housing.csv
├── images/
├── notebook.ipynb
├── README.md
└── requirements.txt
 Conclusion

This project demonstrates the implementation of a real-world multimodal regression system that combines structured data and visual information to predict housing prices.

It showcases practical understanding of deep learning architectures, feature fusion, and evaluation techniques in machine learning.
