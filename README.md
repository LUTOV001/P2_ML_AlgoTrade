# P2_ML_AlgoTrade
UCB FinTech Butlers - Project 2 : Machine Learning Algorithmic Trading

Objective
Build predictive models using machine learning algorithms for buy-sell decision making 

Definitions
Algorithmic trading relies on computer programs that execute algorithms to automate some or all elements of a trading strategy. Algorithms are a sequence of steps or rules designed to achieve a goal. They can take many forms and facilitate optimization throughout the investment process, from idea generation to asset allocation, trade execution, and risk management.

Machine learning (ML) involves algorithms that learn rules or patterns from data to achieve a goal such as minimizing a prediction error. 
We will illustrate how to apply ML algorithms ranging from linear models to recurrent neural networks (RNNs) to market and fundamental data and generate tradeable signals.

Technical-Trading-Bot (Future Release)
Trading Bot built using the Alpaca API in Python. 

Indicators used for Signal Generation: ATR, DEMA, EFI, EMA, EMV, Force Index, RSI, SMA_Fast, SMA_Slow, SSMA, TEMA, TRIMA,   StochRSI, and Stochastic Oscillator.

The Machine Learning Workflow
Developing an ML solution requires a systematic approach to maximize the chances of success while proceeding efficiently. It is also important to make the process transparent and replicable to facilitate collaboration, maintenance, and subsequent refinements.

The process is iterative throughout but these steps were followed:
Frame the problem, identify a target metric, and define success
Source, clean, and validate the data
Understand the data and generate informative features
Selected multiple machine learning algorithms suitable for the data
Train, test, and tune the models
Leverage the model to solve the original problem

Modeling
The following process has been followed to test and select the most suitable Models using the SPY and QQQ:

1. Data Loading
Prepared Train/Test datasets were loaded from saved files. Please see the Data Preparation README for details on the preparation of the datasets.

2. Model Training
2a. Sci-Kit Learn Modeling
An initial set of Machine Learning models were built using six different packages from the Scikit-Learn library:

Bagging Classifier
GaussianNB
Logistic Regression
Random Forest
SVM Classifier
AdaBoost Classifier
As the initial step in the building of all models a StandardScaler was instantiated.

There were 10-plus models built using different parameters. 
F1-score and AUC-ROC score were calculated to determine the predictive power of the model
2b. TensorFlow Modeling
A Deep Neural Network consisting of two Dense layers was designed with the intent of predicting portfolio performance. The following steps were involved in the training of the neural network. The steps were repeated twice, once for the full features dataset and once for the reduced features dataset:

A loop was used to perform the following steps once per portfolio:
StandardScaler() defined and fit to training data
Training data transformed by scaler
Test data transformed by scaler
Keras-Tuner Hypberband tuner was used to find the optimal combination of the following parameters:

Number of nodes for Dense layer 1
Number of nodes for Dense layer 2
Activation function for hidden layer 1
Activation function for hidden layer 2
learning rate for the optimizer
The model with the 'best' performance from all the model configurations was chosen

3. Model Performance/Selection
Models were evaluated using an ROC-AUC score and F1 score, with the F1 score being the primary metric.

Technologies
Details on asset performance are retrieved using the Yahoo Finance API.
The Machine Learning Models were built in Jupyter Lab, written in Python and leveraged GoogleColab to provide feedback from Contributors.
Visualizations are provided by the hvPlot and Matplotlib libraries.
The Pandas and Numpy libraries are used to work with the asset data retrieved from the API.

Installation Guide
The contents of the repository should be placed into the desired folder on the users computer, being sure to maintain the directory structure.

The following python packages must be installed to run the application locally:
pandas
matplotlib
yahoo_fin
numpy
hvplot
jupyterlab (only if the .ipynb file is used. running the .py file does not require jupyterlab)
These packages may be individually installed into the environment of your choice or you may create a new conda environment using the included environment.yml file.

conda env create -f environment.yml
If you prefer using pip, the included requirements.txt file may be used to install the required packages.

pip install -r requirements.txt

Contributors

Malika Ajmera
Matt Glasgow
Joseph Knight
Mike Nguyen
Michelle Silver
Luis Torres


License
License information can be found in the included LICENSE file.

Resources / Credits
Risk Analysis Survey was compiled based upon a survey provided by Lincoln Financial Group
Code for generating the Machine Learning Models was modified from code provided by UC Berkeley Extension FinTech Bootcamp
Research on trading factors and machine learning was modified from code for Machine Learning for Algorithmic Trading, 2nd edition by Stefan Jansen https://www.amazon.com/Machine-Learning-Algorithmic-Trading-alternative/dp/1839217715?pf_rd_r=GZH2XZ35GB3BET09PCCA&pf_rd_p=c5b6893a-24f2-4a59-9d4b-aff5065c90ec&pd_rd_r=91a679c7-f069-4a6e-bdbb-a2b3f548f0c8&pd_rd_w=2B0Q0&pd_rd_wg=GMY5S&ref_=pd_gw_ci_mcx_mr_hp_d 
Analysis of Financial Time Series, 3rd Edition, Ruey S. Tsay
Quantitative Equity Investing: Techniques and Strategies, Frank J. Fabozzi, Sergio M. Focardi, Petter N. Kolm

Future Research
Integrating Risk Tolerance Survey from Project 1
Explore other machine learning models
Runtime/ Resource efficiency
Test on other asset classes, stocks and sectors
Test on ‘paper trading’ mode

Future Releases
Add UI/UX
API integration
Deploy to the cloud
Blockchain record keeping 
Adding macroeconomic market information for the client
Improve visualizations


Disclaimer
The information provided through this application is for information and educational purposes only. It is not intended to be, nor should it be used as, investment advice. Seek a duly licensed professional for investment advice.
