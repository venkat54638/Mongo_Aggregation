

# Easy Assignment:
i.) The aggregation query to find all documents where the category is "Electronics".
Here we use the $match
command:
![image](https://github.com/user-attachments/assets/bbe32f90-e042-483a-ad18-67b043c2a6fb)
ii.)  I have Written an aggregation query to count how many products belong to each category.
here we will use the $group and $sum 
command:
![image](https://github.com/user-attachments/assets/1fa78a4b-b8f5-45ad-8bd0-8b85193af84c)
iii.)  I have Written an aggregation query to display only the name and price of each product, sorted by price from highest to lowest. Do not include the _id field.
Here we use the $project and $sort:
![image](https://github.com/user-attachments/assets/b77ec9af-21aa-4d28-819d-d020f8f00cb5)

# Medium Assignment
i.) I have Written a  aggregation query to calculate the total quantity of products supplied by each supplier.name. 
here i have used the  $group on supplier.name and $sum on quantity.
below we have the command and output.

![image](https://github.com/user-attachments/assets/11f0c37e-ddc1-4349-84d4-326089937563)

ii.) I have written an aggregation query to find the average price of products associated with each tag. List the tag and its average price, sorted by average price in descending order.
Here I have used Use $unwind on tags, then $group on tags, and $avg on price. Finally, $sort.
![image](https://github.com/user-attachments/assets/b785869b-683f-47e8-b6af-ed7b3e3048f2)

iii.)I have written query for List the name, category, and the date_added (formatted as "YYYY-MM-DD") for products added in February 2023.
Here I have used $match with date range conditions on date_added. Then use $project with $dateToString to format the date.

![image](https://github.com/user-attachments/assets/7ea00178-196f-42dc-a5ca-2af3c98e9377)

# Hard Assignment

i.) Here ,After we have the total value of each category, we utilize $project with a $switch statement to classify values: categories above 10,000 are classified as "High Value", categories above 5,000 as "Medium Value", and all else as "Standard Value". Then, the output is structured so only the categoryName, totalInventoryValue, and its valueClassification remain, for easy comparison of the economic importance of each category.

![image](https://github.com/user-attachments/assets/6d8e3c23-58dd-4a65-8a9f-cb0662c105e0)
![image](https://github.com/user-attachments/assets/98286bb6-87e9-4c6e-beef-a69140ce94ed)


ii.) This accumulation finds each supplier's most costly product by sorting all products by supplier.name and price in descending order so that the costliest item comes first for every supplier. We then use $group on supplier.name to take the first product's name and price with $first, which is the highest-priced one since we sorted beforehand. The last $project step renames the output into neat field names: supplierName, mostExpensiveProductName, and maxPrice.

![image](https://github.com/user-attachments/assets/57fc6498-b801-42b9-b6d3-fe18ccd32535)
![image](https://github.com/user-attachments/assets/0df9c2c1-f4bb-4d19-a584-695098a5d734)

iii.)Here this query filters the products to return only those that include "portable" in their tags array and do not include "computer". The $all: ["portable"] ensures "portable" is present, and $not with $elemMatch: { $eq: "computer" } ensures "computer" is not. The final $project outputs only the name and tags fields for clarity.



![image](https://github.com/user-attachments/assets/79278228-8444-446a-9306-e67c6ab55c73)

 


