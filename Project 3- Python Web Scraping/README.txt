Performed Web Scrapping using following website:
https://www.careinsurance.com/health-plan-network-hospitals.html

Pre-requisites:
  1. os
  2. pandas
  3. requests
  4. mysql.connector
  5. bs4 - BeautifulSoup
  6. header = {'User-Agent': 'Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.75 Safari/537.36'}. You can get it on google search = "What is my user agent" and it will show a string.

For installing above required please find Requirements.txt

Scrapping Steps:-
  1. Understand how and what website looks like and look for the target data we want to scrape
  2. We can get that websites scraping code/html-elements in inspect(ctrl + shift + i).
  3. Now for scraping first we need to get html code from url-site to python notebook. So we make a function in which we input the url and get soup object and for that we need header as shown in pre-requisites.
  4. Here in our cases we need to store names of cashless hospitals and upload it to database. So we are starting with State-dropdown menu and fetch all the states from url using soup_() function, which we have created initially.
  5. Now while fetching States i have fetched states as well as option-tags values. This values are numerical in form and will help to manipulate url-link where we can show our dynamic nature of url-link for fetching other data like city and hospitals. So while fetching States I faced a problem where i want only names of states but the list consist of all other values also, so I scliced it and mapped it with integer to get integral values. Then we got the texts performed stripping and splitting on it for removing other noise in data.
  6. Similarly we performed for cities. But here(in cell number 4) you can see that we took help from state values(numerical value) by which we dynamically change the url-link and fetch the cities statewise. And again stored data in string as well as numerical form so that we can fetch hospitals in a city. Then in cell-5 I have created city_list dataframe so that we can easily get data from it because of its functionality.
  7. Here comes the time taking task in which it loops for one-state -> one-city -> one-page. But in our code it does not take much time and we performed similar code for fetching hospital. 
  8. Now created Dataframe consisting of columns=["States","City","Hospitals"] using above fetched data and checked for null or redundancies in data.
  9. Lets upload fetched data to database server using MySQL as well as SQLite3.
  10. Created a connection with mysql db, performed queries for creating table with same columns as our fetched data in DataFrame, inserting data into that table and viewing the table.
  11. Atlast saved fetched data into CSV file using pandas.

Concluded Files:
  1. cashless_CAREINSURANCE.csv
  2. Hospital_Data.db - Database created using SQLite3
  3. hospital_data_hospital.sql - Database created using MySQL