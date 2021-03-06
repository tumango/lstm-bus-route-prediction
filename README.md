# Predicting metlink bus route data from historical ping data
Using Keras and Tensorflow LSTM to use bus ping sequences from Wellington, New Zealand to predict bearing, location, and delays.  This method has potential to be much more accurate in terms of arrival prediction than existing methods by incorporating historical data for delays and traffic.

##Dependencies

* keras
* tensorflow

Install Keras from [here](https://keras.io/) and Tensorflow from [here](https://www.tensorflow.org/versions/r0.12/get_started/os_setup). 

##Usage
The below graph shows the LSTM's ability to predict bearing changes at one time step ahead.  The blue line shows the bus's actual bearing changes.  The orange shows predicted bearing changes.  The model is trained on ~600 bus pings for the 83 bus.  If the model were retrained over a larger dataset, we would expect that our ability to predict bearing, speed, position, and delay would increase substantially.  

There is also strong potential for predicting the movements of things like wildlife migration, in order to reduce hazards associated with road crossings or shark attacks.

![Alt text](/accuracy-graph.png?raw=true "Prediction Accuracy - One time step ahead")

Run this using [jupyter notebook](http://jupyter.readthedocs.io/en/latest/install.html). Just type `jupyter notebook` in the main directory and the code will pop up in a browser window. 

In order to generate data run the python/stopstat.py.  this pulls data every 30 seconds from metlink for the specified bus.  Default is set to bus #83.  If data hasn't updated, it doesnt store it.  Data is appended to the bus.csv file.

LSTM run from jupyter notebook pulls a single column (bearing by default) and predicts bearing changes (turns) one time step ahead of bus current position.  


##Credits

Credits go to [jaungiers](https://github.com/jaungiers/LSTM-Neural-Network-for-Time-Series-Prediction).

Wrapper credit goes to Siraj Raval https://www.youtube.com/watch?v=ftMq5ps503w&t=521s

Metlink api info credit to https://github.com/reedwade/metlink-api-maybe



