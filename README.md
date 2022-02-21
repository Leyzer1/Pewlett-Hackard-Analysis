# Pewlett-Hackard-Analysis

# Overview

In this challenge we received 6 different csv files that contain different types of employee data from Pewlett Hackard. We then used PostgreSQL to determine the number of retiring employees and identified which employees can be considered for a mentorship program.

# Results

To get the results we need we need to understand how our data is related to each other. Using https://www.quickdatabasediagrams.com/
we were able to visualize all our tables and make relationship connections. All shared a primary key column being the unique employee number and the department number. 

![EmployeeDB](https://user-images.githubusercontent.com/95899763/154882270-52054eb6-6207-4099-b9c1-be5df1fce221.png)

Using inner joins between the employees table and the titles table we get the count of retires by title:

![retirement_titles](https://user-images.githubusercontent.com/95899763/154884346-aa8eebaf-452e-458d-acc0-eed5b4021819.PNG)

Using DISTINCT ON we are able to remove all duplicate rows form our tables:

![unique_titles](https://user-images.githubusercontent.com/95899763/154884064-587ab017-2c73-45d4-a583-99b5ed12fb9a.PNG)

From the tow results above we can now create the summarized ritering_titles table:

![retiring_titles](https://user-images.githubusercontent.com/95899763/154882547-3d2e7bd3-9800-4ca9-a702-0d88f850a65f.PNG)

Using distinct ON to get unique employee data, we double inner join with the dept_emp table and the titles table with the condition in which the birth date is from the year 1965 and are not retired yet. This will give us the mentorship_eligibility table:

![mentorship_elegibility](https://user-images.githubusercontent.com/95899763/154882809-da57d75a-9189-4523-a29a-6bc1b0e2c42c.PNG)

# Summary

How many roles will need to be filled as the "silver tsunami" begins to make an impact?
- Senior Engineers: 29,414 
- Senior Staff: 28,254
- Engineers: 12,243
- Technical Leaders: 4,502
- Assistant Engineers: 1,761
- Managers: 2
- Total: 90,398

Are there enough qualified, retirement-ready employees in the departments to mentor the next generation of Pewlett Hackard employees?
- There are a total of 1549 candidates for mentorship eligibility, and 90,398 positions to fill. That gives us a ratio of about 58.3 new employees per mentor. I believe we will not have enough mentors, because mentorship should be closer to 2 or 3 new employees per mentor for it to be a successful program. In this case we could expand the criteria of who is eligible to be a mentor in order to have a better ratio. 
