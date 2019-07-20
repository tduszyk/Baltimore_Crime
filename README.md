# Baltimore Crime and CCtv Cameras

## Team 007

### Contributors
Tom Duszyk<br/>
Karla Pratts

### Data sources

Baltimore CCTV locations. from data.world : <br/>
https://www.kaggle.com/sohier/crime-in-baltimore
2019 Baltimore Crime data. from kaggle:<br/>
 https://www.kaggle.com/sohier/crime-in-baltimore 

Both datasets were formatted as CSV’s 
We extracted them and mostly work with them through IPA keys and then download the files to a local folder.

### Data Transformation
To be able to use the data sets we had to make some changes and clean up.
One of the challenges was that the original CCTV locations data set had a location column for Latitude and Longitude.
to be able to understand better the meaning of that we required geocoding to transform those location from Lat and Long to addresses.
we created a lost for each and loop through the rows, while separation the values on the ',', we used the command 'except' to allow the code to run if there was an error or empty values.
this that, we were able to isolate Lat and Long to use a simple code block to return addresses using the geopy dependency.

We used a Relational databases, PostgreSQL, to store data in tables and rows. we stored the original set and the cleaned up sets.

### This is or raw CCTVdata table
 ![pgAdmin CCTVTable](https://user-images.githubusercontent.com/46768393/61580745-2b2a4780-aae3-11e9-9d0b-6d47ba59f5ed.png)

### And this is our clean CCTV data table
  ![cctv_clean_tables](https://user-images.githubusercontent.com/46768393/61580606-24e79b80-aae2-11e9-9324-c93762233e9c.png)

### Raw Crime table
 ![pgAdmin CrimeTable](https://user-images.githubusercontent.com/46768393/61580772-5f056d00-aae3-11e9-90ec-2948cfe1b2b9.png)

### Clean Crime table
 ![crime_clean_tables](https://user-images.githubusercontent.com/46768393/61580776-6cbaf280-aae3-11e9-93d4-95a17b208d46.png)




