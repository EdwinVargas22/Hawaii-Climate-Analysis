# Surfs Up!
![Hawaii](https://user-images.githubusercontent.com/60836219/99481944-1ac0f180-2910-11eb-9583-74c913129f4c.jpg)

Congratulations! You've decided to treat yourself to a long holiday vacation in Honolulu, Hawaii! To help with your trip planning, you need to do some climate analysis on the area. 

## Climate Analysis and Exploration
You will be using Python and SQLAlchemy to do basic climate analysis and data exploration of your climate database. All of the following analysis should be completed using SQLAlchemy ORM queries, Pandas, and Matplotlib.

* Use SQLAlchemy create_engine to connect to your sqlite database.
* Use SQLAlchemy automap_base() to reflect your tables into classes and save a reference to those classes called Station and Measurement.

### Precipitation Analysis
* Design a query to retrieve the last 12 months of precipitation data.
* Select only the date and prcp values.
* Load the query results into a Pandas DataFrame and set the index to the date column.
* Sort the DataFrame values by date.
* Plot the results using the DataFrame plot method.

![Precipitation](https://user-images.githubusercontent.com/60836219/99484269-dbe16a80-2914-11eb-8d5c-9740471c8ded.png)

* Use Pandas to print the summary statistics for the precipitation data.

![Summary statistics](https://user-images.githubusercontent.com/60836219/99484201-bc4a4200-2914-11eb-8599-5cc5f8bae646.PNG)

### Station Analysis
- Design a query to calculate the total number of stations.
- Design a query to find the most active stations.
  - List the stations and observation counts in descending order.
  - Which station has the highest number of observations?
  - Use a function such as func.min, func.max, func.avg, and func.count in your queries.
- Design a query to retrieve the last 12 months of temperature observation data (TOBS).
  - Filter by the station with the highest number of observations.
  - Plot the results as a histogram with bins=12.
  
![Temperature](https://user-images.githubusercontent.com/60836219/99484270-ddab2e00-2914-11eb-9971-5899ea6b0130.png)

## Climate App
Design a Flask API based on the queries that you have just developed.
* Use Flask to create your routes.

### Routes
- /
  - Home page
  - List all routes that are available.
- /api/v1.0/precipitation
  - Convert the query results to a dictionary using date as the key and prcp as the value.
  - Return the JSON representation of your dictionary.
- /api/v1.0/stations
  - Return a JSON list of stations from the dataset.
- /api/v1.0/tobs
  - Query the dates and temperature observations of the most active station for the last year of data.
  - Return a JSON list of temperature observations (TOBS) for the previous year.
- /api/v1.0/<start> and /api/v1.0/<start>/<end>
  - Return a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.
  - When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.
  - When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.
 
## Hints
* You will need to join the station and measurement tables for some of the queries.
* Use Flask jsonify to convert your API data into a valid JSON response object.
