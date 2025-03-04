# nosql-challenge
Overview

In this project, we are tasked with managing and analyzing food hygiene ratings data from the UK Food Standards Agency. The data is stored in a MongoDB NoSQL database, and the goal is to assist the editors of the food magazine Eat Safe, Love in evaluating establishments based on their hygiene ratings and other factors. The project is divided into three main parts:

Setting up the database and Jupyter Notebook environment.
Updating the database with new data and modifying existing records.
Conducting exploratory analysis to answer specific questions provided by the magazine editors.
Methodology

Part 1: Database and Jupyter Notebook Setup
Database Setup:
Import data from the establishments.json file into MongoDB, naming the database uk_food and the collection establishments.
Use Python libraries, such as PyMongo and Pretty Print (pprint), to connect to the MongoDB instance and interact with the data.
Confirm the database and collection exist by listing all databases and collections in MongoDB.
Use find_one to display a document from the collection and inspect the data.
Collection Setup:
Assign the establishments collection to a variable for further use in the analysis and updates.
Part 2: Update the Database
Adding New Data:
A new halal restaurant, Penang Flavours, located in Greenwich, is added to the database. The new restaurant's information is inserted with a "NewRatingPending" flag set to True.
Update the New Restaurant:
The BusinessTypeID for the "Restaurant/Cafe/Canteen" is fetched, and the new restaurant is updated with this BusinessTypeID.
Remove Unwanted Data:
Establishments in the Dover Local Authority are removed from the database. The number of documents before and after deletion is checked to confirm that the data was successfully removed.
Data Type Conversion:
Latitude and longitude values are stored as strings, but they should be numeric. The update_many method is used to convert these values into decimal numbers.
The RatingValue is also updated to ensure it is stored as an integer, converting any non-numeric values (like 'Pass') to null.
Part 3: Exploratory Analysis
Data Exploration:
Using the updated establishments collection, we perform an exploratory analysis to answer specific questions posed by Eat Safe, Love.
Answering the Questions:
Question 1: Find establishments with a hygiene score of 20 and display the count of matching documents, the first document, and the first 10 rows in a Pandas DataFrame.
Question 2: Find establishments in London with a RatingValue of 4 or higher, ensuring to handle partial matches in the local authority name using regular expressions.
Question 3: Identify the top 5 establishments with a RatingValue of 5, sorted by the lowest hygiene score, that are nearest to the new restaurant Penang Flavours.
We use geocode comparison to find the nearest establishments within 0.01 degree latitude and longitude of the new restaurant.
Question 4: Determine how many establishments in each Local Authority have a hygiene score of 0, sorting the results from highest to lowest and displaying the top 10 local authority areas.
Tools and Libraries Used:
MongoDB: For storing and querying the establishments data.
PyMongo: To interact with MongoDB from Python.
Pretty Print (pprint): For formatted and readable output of MongoDB query results.
Pandas: For manipulating and analyzing data, particularly when converting query results into DataFrames for analysis.
Matplotlib: For visualizing the results where needed.
Results

Part 1: Database Setup
The uk_food database was successfully created, and the establishments collection was populated with data from the provided establishments.json file.
The connection to the MongoDB instance was successfully established, and the existence of the database and collection was confirmed using PyMongo.
The first document in the establishments collection was displayed using pprint for inspection.
Part 2: Database Updates
The new restaurant, Penang Flavours, was successfully added to the database with the appropriate details, including the NewRatingPending flag set to True.
The BusinessTypeID for "Restaurant/Cafe/Canteen" was successfully fetched and used to update the new restaurant record.
Establishments in the Dover Local Authority were successfully removed from the database, and the count of documents before and after the deletion was verified.
Latitude and longitude values were successfully converted to decimal numbers, and the RatingValue was updated to store only integer values, with non-numeric entries handled as null.
Part 3: Exploratory Analysis
Hygiene Score of 20: We found the establishments with a hygiene score of 20 and displayed the number of matching documents, the first document, and the first 10 rows in a Pandas DataFrame.
London Establishments with RatingValue ≥ 4: We successfully identified the establishments in London with a rating of 4 or higher, using regular expressions to handle the longer local authority name.
Top 5 Establishments Near Penang Flavours with RatingValue 5: The top 5 establishments nearest to Penang Flavours were identified, sorted by hygiene score, using geocode comparisons.
Establishments with Hygiene Score of 0: We determined the number of establishments with a hygiene score of 0 in each Local Authority and displayed the top 10 local authorities with the highest number of such establishments.

References
Chatgpt 
Xpert Learning Assistance
The tutor Fred Logan
