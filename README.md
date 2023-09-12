
# Azure Data Factory Assignment :
 You must create a pipeline that copies data from two Excel files from blob to Azure cloud SQL
tables. What are the necessary steps you need to take to ensure this pipeline will get executed
successfully?
Important points:
1. You can take any two sample excels with different columns. For example – Employee table
and payroll table
2. Mappingsfor columnsshould not be hard coded it should be coming dynamically from the
lookup table for both source and destination
Hint:
1. Create a table of source-to-destination mappings, source file name, and destination name.
2. Create a procedure to return dynamic JSON mapping.
Submission:
1. Create a video with the pipeline running and data getting copied to the database.
2. Submit the pipeline code on the GitHub repo and share the URL



# explaination 



Step 1: Blob Storage and Files

I've set up a Blob Storage, and I've given it the name "techome."
Inside this Blob Storage, I've placed two files: one called "employee" and the other called "payout."

Step 2: Metadata Activity

To understand more about these files, I've added a Metadata Activity.
This activity gathers details like file names, sizes, and modification timestamps, which I'll need for further steps.

Step 3: Lookup Activity

After collecting this metadata, I've introduced a Lookup Activity into the process.
This Lookup Activity will help me extract specific information from the metadata, like the file names or sizes, and make it available for other parts of the process.

Step 4: Employee Table - Source Data

I've defined the structure of my source data, which relates to what I call the "Employee" table.
This table contains fields like EmployeeID, FirstName, LastName, Department, Position, DateOfBirth, Email, and Phone.

Step 5: Payroll Table - Source Data

Additionally, I have another table known as the "Payroll" table.
It holds data such as EmployeeID, MonthlySalary, TaxDeductions, and NetSalary.

Step 6: Mapping Configuration - Payroll Table

For smooth data transfer, I've created a mapping configuration for the "Payroll" table, and I've expressed it in JSON format.
This configuration outlines how the data from the source should be matched to the target fields in the "Payroll" table. It's like giving directions to the system.

Step 7: Mapping Configuration - Employee Table

Similar to the "Payroll" table, I've also established a mapping configuration for the "Employee" table using JSON.
This mapping guides the system on how to take the source data and place it correctly into the "Employee" table. There's a special note here that the "DateOfBirth" field needs to be transformed from a string into a date format.
