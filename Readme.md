# Deep Learning to predict root cause 

## Problem statement

ITSM received multiple incident tickets every day. The incidents usually state the symptoms that are observed by the users. Technical teams may further analyse the problem to identify more symptoms. Then comes the analysis process of narrowing down the symptom to its root cause. here I have used Deep learning to predict which kind of root cause it is based on given symptoms.

**Incident Reports in ITSM usually states the symptoms. Identifying the root cause of the symptom quickly is a key determinant to reducing resolution times and improving user satisfaction.**

## Dataset

Dataset link: [https://www.kaggle.com/datasets/anjolaoluwaajayi/root-cause-analysis-dataset/data](https://www.kaggle.com/datasets/anjolaoluwaajayi/root-cause-analysis-dataset/data)

Training data is collected about the symptoms seen for the problems reported. These symptoms are gathered by technical teams when a problem is seen by the users. 

To keep it simple, each symptom is a separate attribute. That is a flag with values one or zero to indicate if the symptom is seen or not. 

Total 1000 training examples are used to train the model. predictions will be much more reliable if training data is available with more number of symptoms.

 The symptoms are:

- CPU load
- Memory load
- Network delays
- Some of these specific error codes were seen in the log files
- Root cause:
    - the root cause attribute is the target variable that contains classes of root causes.

Note : This example uses a simple set of symptoms but in real-life scenarios there can be a large number of symptoms. Symptoms can further be broken down by where they are seen. Like for CPU load, was it at the load balancer or a specific microservice? Symptoms can also be isolated from general text using text mining. Let's now proceed to build a model based on this data set to predict the root cause based on the symptoms seen for the problem.

# Deep Learning to Predict Root Cause

![nn_architecture.png](Images%2000c499d7984646f0b4367be118995ff1/nn_architecture.png)

## Model Architecture:

![Screenshot 2023-12-29 at 11.41.50 AM.png](Images%2000c499d7984646f0b4367be118995ff1/Screenshot_2023-12-29_at_11.41.50_AM.png)

### Activation function used :

- hidden layers
    - `relu`
- output layer
    - `softmax`

### loss : 
- `categorical cross entropy`

### optimiser:
- `Adam`


# Model Performance

Training accuracy = `87%`

Validation accuracy = `81%`

![accuracy.png](Images%2000c499d7984646f0b4367be118995ff1/accuracy.png)

![loss.png](Images%2000c499d7984646f0b4367be118995ff1/loss.png)


# Deployment

![app_ss.png](Images%2000c499d7984646f0b4367be118995ff1/app_ss.png)