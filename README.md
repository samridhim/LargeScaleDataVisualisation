# Installation and Running Steps

## For putting historical data into server and displaying a line chart of values of the same on client side

1. Extract THERM0001.rar file in the same directory

2. Go to ServerSide folder and start node.js server by typing `cd ServerSide` & `nodemon` 
(NodeJS should be installed, if it isn't install it using sudo apt-get install nodejs)

3. Start mongo client by `sudo service mongod start` and  `mongo --host localhost`, this ensures that mongo is running on localhost and the default port is 3000.

4. Run the *split_data.py* script in the *Data_Preprocessing folder* to prepare the data to send to the Server running on localhost:3000 -> `cd Data_Preprocessing` & `python split_data.py`

5. A file called "data_agg.json" will be generated in the Data_Preprocessing folder itself, this is the file that is to be sent to the server to store in the mongodb database

6. Go to *ClientSide* folder and run the *index.html to begin demo*. Use the 'data_agg.json' file to send to server. 

7. To view the chart in getchart.html, give any start date and end date between **Feb 2015 - Feb 2016** only. The dataset does not have values beyond these two dates. 


## For real time data simulation and viewing the line chart on client side

1. Run the simulator.py file & keep it running indefinitely. This will send documents to the server at 10 second intervals.

2. To view the chart, open up realtime.html file in the ClientSide Folder. The initial chart takes 10 seconds to appear, after that the page is refreshed automatically to update the datapoints. 

3. To stop simulation, stop the execution of simulator.py

# Demo Pics
## Screenshot of Historical Chart for 13th Feb 2016 to 22nd Feb 2016

<img src="Screenshot_2019-04-07%20Screenshot.png" alt="drawing" width="800" height = "800"/>

## Gif of realtime updates using the simulated real time data

<img src="Peek 2019-04-07 11-07.gif" alt="gif" width="800" height = "800"/>
