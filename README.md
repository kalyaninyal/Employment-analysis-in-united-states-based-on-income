# Employment-analysis-in-united-states-based-on-income
Employment analysis in united states based on income in this project ETL is performed .

Extraction

We used 3 datasets from the public platform Kaggle and Data World. All of our data was based on county through all the States ranging over various years . These were the most recent ones we could find. The sources for our dataset are as follows
 
•	Diversity Index from Kaggle.
•	Unemployment from Kaggle.
•	Median Income by county from Data World.

Transformation

The  first steps in cleaning up the datasets involved figuring out which variables were not relevant. For the Median Income Dataset, dropped the columns County-State & State and renamed the State Code column to State. Then  split certain columns such as Location from Diversity table into County & State to make it easier to merge and group with the other 2 datasets. For the unemployment rate dataset, State column was in full name , we needed to abbreviate them to merge with the rest. To do this, a dictionary of states and their abbreviations were used with a loc loop to iterate through the dataset . Finally, grouped this dataset by State and County and averaged for each County

After cleaning the datasets and workable, the data were merged . To start, the Unemployment dataset and Median Income dataset were merged on State and County, using an inner join. The Diversity dataset was then merged on that by State and County again, using an inner join as well. With all the three datasets combined  into one universal table, the State and County index was reset turning them back into columns, and columns were reordered to a more logical format.

Load

The last step was to transfer the  final output into a DataBase.  created a database and respective tables to match the columns from the final Panda’s Data Frame using MYSQL and then connected to the database using SQLAlchemy and loaded the result. By this we were  able to perform multiple queries to suit a desired criterion. 
 
output:
The final output will help us to recognize which county, state that has the following. 

•	Most or Least Population. 
•	Median Household Income
•	Unemployment Rate
•	Diversity Index
•	Race Index 

These indices can be used to identify if any development aid/work are required for areas with high unemployment rate, low median income or with high population. 
If the population is high and if the schools/colleges/educational institutions are less, these indices can be used to build more educational institutions, which in turn create more employment opportunities. It is a cascading effect of more the population, more educational institutions, more employment, more household income.
