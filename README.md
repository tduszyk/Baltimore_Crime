# Baltimore Crime and CCtv Cameras

## Team 007 <br/>
## ETL Project

### Contributors
Tom Duszyk<br/>
Karla Pratts

### Data sources

Baltimore CCTV locations. from data.world : <br/>
https://www.kaggle.com/sohier/crime-in-baltimore <br/>
baltimore/baltimore-cctv-locations

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

### This is our raw CCTVdata table
 ![pgAdmin CCTVTable](https://user-images.githubusercontent.com/46768393/61580745-2b2a4780-aae3-11e9-9d0b-6d47ba59f5ed.png)

### And this is our clean CCTV data table
  ![cctv_clean_tables](https://user-images.githubusercontent.com/46768393/61580606-24e79b80-aae2-11e9-9324-c93762233e9c.png)

### Raw Crime data table
 ![pgAdmin CrimeTable](https://user-images.githubusercontent.com/46768393/61580772-5f056d00-aae3-11e9-90ec-2948cfe1b2b9.png)

### Clean Crime data table
 ![crime_clean_tables](https://user-images.githubusercontent.com/46768393/61580776-6cbaf280-aae3-11e9-93d4-95a17b208d46.png)


### Challenges
1. First of our datasets contains street address while the second contains geolocation grid (latitude and longitude).
2. We used package geopy.geocoders to translate latitude and longitude into street address. This package appears to be a "frontend" to Google API. Quickly we ran out of API requests and had to put our project on hold for 24 hours. This is also a reason why we decided to upload to the database, dataset with addresses, without cleaning the data first. We did it as a precaution.
3. Our address translations came in different format than the one we had in other table. This is a reason why we decided to capitalize neighborhood names.

### Final thoughts
We didn't join our tables, becasue we decided that joined table will be inconclusive and cannot be used for data analysis. 

### Next Steps
If we continued this project, we would scatter plot CCTV and Crimes across neghborhoods and check if any correlation exists. Also we would add third dataset with arrests data, and try to see if there is correlation between CCTV and arrests. And also if arrests are happening in the same neighborhoods as commited crimes.
As a bonus to the presentation we would add intercative map using Folium.

