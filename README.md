# Prediction_MachineLearning_PatriotFest

# Machine Learning Algorithm Documentation

## 1. Introduction
The purpose of a machine learning algorithm is to enable a computer system to learn from data and experience to perform a specific task or make predictions without being explicitly programmed for it. Instead of implementing specific rules or instructions, machine learning algorithms use mathematical and statistical models to find patterns and relationships in training data and then generalize this knowledge to make decisions or predictions on new, unknown data.

For this practical project, one of the main objectives was to create a model that takes multiple flow rate values from a device and predicts the next flow rate based on which the total energy consumption cost is calculated. Various types of models were considered for implementation, including linear regression, artificial neural networks, and decision trees.

- Linear regression is simple to learn and implement, suitable for problems with linear relationships between variables, but it may not capture complex correlations, and its performance may be limited with non-linear data.

- Decision trees are easy to understand and visualize, capable of handling various data types, but they tend to be sensitive to small variations in input data.

- Artificial neural networks can model more complex relationships between variables, learn high-quality representations from raw data, but require a relatively large dataset to avoid overfitting and can be challenging to train and optimize.

In this project, the machine learning algorithm was implemented using artificial neural networks, utilizing historical data for predictions. The programming language used is Python, in an object-oriented paradigm, along with the TensorFlow and Keras libraries, both specialized in machine learning.

## 2. Main Application Flow
To make the application user-friendly, a configuration file (`machine_learning.config`) was added, allowing the user to easily input desired data without extensive coding knowledge. Additionally, for transparency, the application that trains the model displays output in both the console and a logging file (`logfile.log`). Paths to these two files are provided as arguments to the main program responsible for training the model, namely `MainApplication.py`.

Once the model is trained, it is saved in the .onnx format and can run independently of the training application by executing `Main.py`. The output will be a list of predicted values, which will be further processed by Node Red and later uploaded to the Cloud database.

## 3. Used Modules
Among the modules used are:

- `os`: Interacts with the operating system to check the existence of files and create them if necessary.
- `enum`: Defines enumeration types, used for declaring constants such as different formats and a list and dictionary for data validation.
- `logging`: Records useful messages and information during program runtime.
- `json`: Works with JSON data, necessary for parsing configuration file data.
- `argparse`: Analyzes command-line arguments for ease of use.
- `pickle`: Serializes and deserializes Python objects for data transmission between applications.
- `pandas`: Efficiently manipulates and analyzes tabular data.
- `numpy`: Fundamental module for working with multidimensional data arrays and performing advanced mathematical and statistical operations.
- `tensorflow`: Open-source module for machine learning and artificial intelligence, used with the Keras interface.
- `sklearn`: Open-source library specialized in providing various functionalities for machine learning model development.
- `tf2onnx`: Open-source module for converting TensorFlow models to the ONNX (Open Neural Network Exchange) format.
- `onnxruntime`: Open-source library developed by Microsoft for running ONNX format AI models efficiently.

## 4. Application Flow Details
The application comprises two different programs: `MainApplication.py` and `Main.py`. The former is responsible for training the machine learning model, while the latter runs the trained model.

### MainApplication.py:
The application starts by parsing command-line arguments, initializing the logger file, validator, and an instance of the main object acting as an entry-point for the program. After these objects are initialized, the execution function is called to validate the existence of the configuration file and logging file, as well as the correctness of the configuration file data. If any validation condition is not met, the program stops and raises an error.

After successful validation, the configuration file is parsed, brought into the program's memory, and a database object is initialized for communication with the cloud database. The training data is retrieved locally as a CSV file, and the model training process begins in the `MachineLearning` class. The data is split into training and evaluation sets, the neural network model is defined with different activation functions, and the error is calculated. Finally, the model's performance is evaluated.

The defined neural network model is sequential, with several layers, each using different activation functions. After training and testing the model, it is converted to the ONNX format, and certain data is saved in PKL format for the next program to pick up.

### Main.py:
This program starts by retrieving data saved in PKL format and parsing the configuration file. It then attempts to predict the next flow rate value based on the last 30 real flow rate values. It performs 30 predictions, with each subsequent prediction using both real and previously predicted values for estimation. The predicted values are stored in a list and displayed on the screen, ready to be sent to Node Red.

