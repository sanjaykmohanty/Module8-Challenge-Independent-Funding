# Module8-Challenge-Independent-Funding

## Overvirw
This project is an extension of the crowdfunding ETL project. The purpose of this project is to perform an ETL process on the backers dataset and a data analysis by using SQL queries. Backer’s contact information is extracted and transformed from a CSV file and added as a new table to crowdfunding_db database. Finally, a data analysis is done on the crowdfunding_db database by using SQL queries.

## Resources
Software: Python 3.9.12, Jupyter Notebook 6.4.12, pgAdmin 4 6.12

## Results
### Extract Data using Python dictionary methods
![image](https://user-images.githubusercontent.com/31812730/196046594-f856a75f-af97-40c4-b691-397b2ca6295c.png)


### Transform and Clean Data 
![image](https://user-images.githubusercontent.com/31812730/196046331-f3a8be90-835e-4f92-ad6d-cbb5fae10d9c.png)


### Create an ERD and a Table Schema and Load the Data
![image](https://user-images.githubusercontent.com/31812730/196045941-d6916745-7d1f-423d-9670-cad8533d3cae.png)

### SQL Analysis 

    SELECT * FROM backers 
    LIMIT(10);

![image](https://user-images.githubusercontent.com/31812730/196050860-e94ed552-22f0-4100-aaac-a163cadf9ea0.png)

    SELECT cf_id, backers_count 
    FROM campaign WHERE outcome = 'live' 
    ORDER BY backers_count DESC;

![image](https://user-images.githubusercontent.com/31812730/196050908-4f321840-34c1-4759-96ff-91f260e7f60d.png)

    SELECT cf_id, COUNT(backer_id) AS backer_count 
    FROM backers 
    GROUP BY cf_id 
    ORDER BY backer_count DESC;

![image](https://user-images.githubusercontent.com/31812730/196050989-e05ca158-3176-4a43-9cb5-26e3c97d59ba.png)

    SELECT C.first_name, C.last_name, C.email, (CA.goal - CA.pledged) AS "Remaining Goal Amount"
    INTO email_contacts_remaining_goal_amount
    FROM contacts C
    JOIN campaign CA
    ON CA.contact_id = C.contact_id
    WHERE CA.outcome = 'live' 
    ORDER BY "Remaining Goal Amount" DESC

![image](https://user-images.githubusercontent.com/31812730/196059737-79e18e23-d663-4e4a-8ffd-4ad6a20a6165.png)

    SELECT B.email, B.first_name, B.last_name, B.cf_id, C.company_name, C.description, C.end_date, (C.goal - C.pledged) AS "Left of Goal"
    INTO email_backers_remaining_goal_amount
    FROM  backers B
    JOIN campaign C
    ON C.cf_id = B.cf_id
    WHERE C.outcome = 'live'
    ORDER BY B.email DESC
    
![image](https://user-images.githubusercontent.com/31812730/196059897-b626c96b-ec6c-49b1-9152-28f823915bd0.png)

