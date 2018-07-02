This repository is for Predictive Maintenance (PdM).

Run the Predictive Maintenance application from `flask_api/flask_apis_alchemy.py`

### Machine learning for predictive maintenance
To build a failure model, we require enough historical data that allows us to capture information about events leading to failure.In addition to that, general “static” features of the system can also provide valuable information, such as mechanical properties, average usage and operating conditions. When collecting data to support a failure model, it is important to make an inventory the following:

What are the types of failure that can occur? Which ones will we try to predict?
How does the “failure process” look like? Is it a slow degradation process or an acute one?
Which parts of the machine/system could be related to each type of failure? What can be measured about each of them that reflect their state? How often and with which accuracy do these measurements need to be performed?

### Problem Framing
When thinking about how to frame a predictive maintenance model, it is important to keep a couple of questions in mind:

1.  What kind of output should the model give?
2.  Is enough historical data available or just static data?
3.  Is every recorded event labelled, i.e. which measurements correspond to good functioning and which ones correspond to failure? Or at least, is it known when each machine failed (if at all)?
4. When labelled events are available, what is the proportion of the number of events of each type of failure and events of well functioning?
5. How long in advance should the model be able to indicate that a failure will occur?

With all this information at hand, we decided Random forest modelling strategy fits best to the available data and the desired output, or at least which one is the best candidate to start with. There are multiple modelling strategies for predictive maintenance and we will describe four of them in relation to the question they aim to answer and which kind of data they require:

1. Regression models to predict remaining useful lifetime (RUL)
2. Clasification models to predict failure within a given time window
3. Flagging anomalous behaviour
4. Survival models for the prediction of failure probability over time.
