# Module8-Challenge-Independent-Funding
## Deliverable 1: Extract Data using Python dictionary methods
![image](https://user-images.githubusercontent.com/31812730/196046594-f856a75f-af97-40c4-b691-397b2ca6295c.png)


## Deliverable 2: Transform and Clean Data 
![image](https://user-images.githubusercontent.com/31812730/196046331-f3a8be90-835e-4f92-ad6d-cbb5fae10d9c.png)


## Deliverable 3: Create an ERD and a Table Schema and Load the Data
![image](https://user-images.githubusercontent.com/31812730/196045941-d6916745-7d1f-423d-9670-cad8533d3cae.png)

## Deliverable 4: SQL Analysis

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

![image](https://user-images.githubusercontent.com/31812730/196052853-9a23667e-dacd-46d3-ba9f-b3c713bed921.png)

![image](https://user-images.githubusercontent.com/31812730/196056897-3d0c2630-acc3-497e-970e-b69648c8e685.png)
