# Crowdfunding-ETL

Module 8 Notes

##Overview:

(This module is built around a project that mirrors a real-world scenario that would require data analysis and visualization)

In this module, as assigned Data Analyst, I will apply the extract, transform, and load (ETL) process, which are the three steps data engineers use when collecting, cleaning, and storing data in a database prior to performing analysis. In addition, I will use Python and Pandas to perform the extract and transform steps. Then, create a PostgreSQL database and table schemas by using an entity relationship diagram (ERD), and load the data into the database. Finally, I will use SQL to perform data analysis.

By the end of this module, you will be able to:
•	Create an ETL pipeline that moves raw data to a SQL database.

•	Extract data from an external file by using Python and Pandas.

•	Use regular expressions to extract numbers and text.

•	Clean and transform data by using Python and Pandas.

•	Design a database and a table schema by using an entity relationship diagram (ERD).

•	Load data into a PostgreSQL database.

•	Perform data analysis by using SQL queries.


##Purpose

As the assigned Data Analyst, I will be assisting the client, Britta, a junior SQL developer with the following tasks:

•	Extracting and transforming the data from the large Excel file into four separate CSV files

•	Creating a PostgreSQL database and tables by using an ERD

•	Loading the CSV files into the database

•	Performing SQL queries to generate reports for stakeholders


##Instructions


##Deliverable 1: Extract Data

Using your knowledge of Python, Pandas, and the extract and transform phases of ETL, you’ll extract the raw data and add it to a DataFrame for the transform phase.

1.	Download the backer_info.csv and Extract-Transform_starter_code.ipynb files into your Crowdfunding-ETL folder. Then rename the Extract-Transform_starter_code.ipynb file to Extract-Transform_final_code.ipynb.

2.	Import the backer_info.csv file into a DataFrame.

 ![image](https://user-images.githubusercontent.com/117233641/229209540-d77d5553-38f7-49a0-ade1-ea05df6c509c.png)


3.	Note that for this deliverable you have two options for extracting the data: use Python dictionary methods or use regular expressions. Choose your option.

4.	To use use Python dictionary methods, complete the following steps:

    o	Iterate through the DataFrame, and convert each row to a dictionary.

    o	Iterate through each dictionary, and do the following:

        	Extract the dictionary values from the keys by using Python list comprehensions.

        	Add the values for each row to a new list.

 ![image](https://user-images.githubusercontent.com/117233641/229209649-52dd2391-b921-4bb7-a765-0b9f5de017a8.png)


6.	Create a new DataFrame with the retrieved data.

 ![image](https://user-images.githubusercontent.com/117233641/229209680-8e0e3ca2-6296-4f88-95ab-894fc3ccee9f.png)




##Deliverable 2: Transform and Clean Data

Using your knowledge of Python, Pandas, and data cleaning strategies, you’ll transform the data via formatting, splitting, converting data types, and restructuring to create a DataFrame that can be loaded into a postgreSQL database as a CSV file.

1.	Continuing to use the Extract-Transform_final_code.ipynb file, check the data types of the columns, and convert the "cf_id" column to int64 if necessary.

 ![image](https://user-images.githubusercontent.com/117233641/229209708-e4599b1e-c9db-4d9b-94b3-bfa80b60c4d4.png)


2.	Split the names in the "name" column into first and last names, and add them to "first_name" and the "last_name" column, respectively, in the DataFrame.

 ![image](https://user-images.githubusercontent.com/117233641/229209738-1ffa43cc-7f6c-4670-b5fa-e99db1b8bd2d.png)


3.	Drop the "name" column in the DataFrame.
 
![image](https://user-images.githubusercontent.com/117233641/229209761-f6e7018e-1ceb-4e9a-920f-383f1ae26e03.png)

![image](https://user-images.githubusercontent.com/117233641/229209795-399905e9-0704-46a3-8001-eecc229d4fdd.png)

 

5.	Export the DataFrame as backers.csv.
 
![image](https://user-images.githubusercontent.com/117233641/229209813-59e62b66-d4fb-4fa8-b152-4abc1878bfdc.png)


## Deliverable 3: Create an ERD and a Table Schema and Load the Data

Using the ERD that you created in this module, you’ll create a backers table that has primary and foreign keys based on the summary information about the backers.csv dataset. You'll then export the updated database schema as a PostgreSQL file and use it to create the backers table in the crowdfunding_db database. Finally, you'll use pgAdmin to upload the backers.csv file into the backers table.

1.	Using the information from the backers.csv file, open the crowdfunding_db ERD that you created in this module and create a backers table.

    o	Make sure that each column has the appropriate data type, that the table has a primary and a foreign key, and that the foreign key references the relevant table.

 ![image](https://user-images.githubusercontent.com/117233641/229209835-e3ffdbf9-51e8-4ba3-99ef-7c2d25b7ead0.png)


2.	Save the crowdfunding relationship diagram as crowdfunding_db_relationships.png and the updated schema as a PostgreSQL file named crowdfunding_db_schema.sql.

3.	Using the crowdfunding_db_schema.sql PostgreSQL file, copy the schema for the backers table and the ALTER TABLE statement to add the foreign key constraint, paste them in the pgAdmin query editor, and then run the query.

 ![image](https://user-images.githubusercontent.com/117233641/229209867-275a66d9-7f84-458f-a14b-912c87230d7d.png)

![image](https://user-images.githubusercontent.com/117233641/229209887-8d80f7db-f274-492a-9369-da2cf47b5b0b.png)
 
4.	Refresh your schema in the crowdfunding_db database to confirm that the backers table was created.
 
 ![image](https://user-images.githubusercontent.com/117233641/229209922-2d000376-2384-4b88-aea6-3daf3586b38a.png)

 
5.	Upload the backers.csv file into the backers table.

6.	To check the import, enter the following in the query editor, and then run the query:
SELECT * FROM backers;

![image](https://user-images.githubusercontent.com/117233641/229209937-aeba525d-a224-441c-8f3d-d08efca58262.png)


8.	Save crowdfunding_db_relationships.png and crowdfunding_db_schema.sql in your Crowdfunding-ETL GitHub repository.
 
![image](https://user-images.githubusercontent.com/117233641/229209967-3e263590-8955-4f73-a4ad-87e8da70be37.png)



##Deliverable 4: SQL Analysis

1.	Download the ETL_SQL_starter_code.sql file, and rename it to crowdfunding_SQL_Analysis.sql.

2.	Write a SQL query that retrieves the number of backer_counts in descending order for each “cf_id” for all the "live" campaigns.

![image](https://user-images.githubusercontent.com/117233641/229210021-53c8321e-6c2e-47ef-b668-1ab04f2e04a5.png)

3.	Write a SQL query that uses the backers table to confirm the results from Step 2.

![image](https://user-images.githubusercontent.com/117233641/229210071-9f5b7e65-c2de-4773-9773-121bc1e31a57.png)

 

4.	You and Britta receive notification from her boss, who wants to send an email to each contact of every live campaign to inform them of how much of the goal remains. To allow them to do so, complete the following steps:

    o	Write a SQL query that creates a new table named email_contacts_remaining_goal_amount that contains the first name of each contact, the last name, the email address, and the remaining goal amount (as "Remaining Goal Amount") in descending order for each live campaign.

![image](https://user-images.githubusercontent.com/117233641/229210123-aa6b1aed-846f-49e8-a58a-3706a7c08a6f.png)

  •	Export the table as email_contacts_remaining_goal_amount.csv.
 
 ![image](https://user-images.githubusercontent.com/117233641/229210170-9f7d28f7-ec98-4e00-a51a-f93b308fe015.png)

5.	Britta informs you that her boss also wants to send an email to each backer to let them know how much of the goal remains for each live campaign that they’ve pledged. To allow them to do so, complete the following steps:

     •	Write a SQL query that creates a new table named email_backers_remaining_goal_amount that contains the email addresses of the backers, the first and the last name of each backer, the cf_id, the company name, the description, the end date of the campaign, and the remaining amount of the campaign goal as "Left of Goal". Sort the table by the last name of each backer, in descending order.
     
![image](https://user-images.githubusercontent.com/117233641/229210239-b1dd9441-b46d-46a0-8be0-f7715238c2ac.png)

![image](https://user-images.githubusercontent.com/117233641/229210292-64c94e6e-bf4e-473b-9150-ad0bef8e3956.png)


  o	Export the table as email_backers_remaining_goal_amount.csv.
 
![image](https://user-images.githubusercontent.com/117233641/229210338-84c0715c-ac46-48e4-b13f-134ac61e149b.png)

