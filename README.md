# Looking for Suspicious Transactions

![Credit card fraudster](Images/credit_card_fraudster.jpg) 

*[Credit Card Fraudster by Richard Patterson](https://www.flickr.com/photos/136770128@N07/42252105582/) | [Creative Commons Licensed](https://creativecommons.org/licenses/by/2.0/)*

## Background

This analysis is requested by the firm's CFO. SQL skills to analyze historical credit card transactions and consumption patterns in order to identify possible fraudulent transactions. This analysis will help the firm to identify potential fraudulent credit card transactions. The reports are generated based on the fraud_detection database.

The following taks will be accomplished:

1. [Data Modeling](#Data-Modeling):
        Define a database model to store the credit card transactions data and create a new PostgreSQL database using the model.

2. [Data Engineering](#Data-Engineering): 
        Create a database schema on PostgreSQL and populate the database from the CSV files provided.

3. [Data Analysis](#Data-Analysis): 
        Analyzing the data to identify possible fraudulent transactions trends data and develop a report.

There are two prt to this analysis. File query.sql has snweres to each sections.
        Part 1 - has a section called *** Part 1.***  Each quection's answeres will be under this sections with questions as heading


#### Part 1:

* Some fraudsters hack a credit card by making several small transactions (generally less than $2.00), which are typically ignored by cardholders. 

  * How can you isolate (or group) the transactions of each cardholder?

    - **ANSWER:** See under section ***Part 1, Question 1*** in file - ***query.sql***

  * Count the transactions that are less than $2.00 per cardholder. 
   
    - **ANSWER:** See under section ***Part 1, Question 2*** in file - ***query.sql***
  
  * Is there any evidence to suggest that a credit card has been hacked? Explain your rationale.

    - **ANSWER:**  ***YES***. There are evidence of several small transactions (less than $2) on 53 credit cards. 
	  Six credit cards recorded 10+ small transactions. This indicates these credit cards may have been hacked. 
	  This conclusion is based on the result from question 2 above.


* Take your investigation a step futher by considering the time period in which potentially fraudulent transactions are made. 

  * What are the top 100 highest transactions made between 7:00 am and 9:00 am?

    - **ANSWER:** See under section ***Part 1, Question 4*** in file - ***query.sql***


  * Do you see any anomalous transactions that could be fraudulent?

    - **ANSWER:** See under section ***Part 1, Question 5*** in file - ***query.sql***
    
	  Based on the result from Question 4, there are 9 transactions have transaction amount greater than $100. The result of 91 transaction out of 100 have transaction amount less than $100, in fact, they are between $23.13 and $11.65 with a low spread. However, the top 9 transactions would be considered suspicious. The transactions jumped from $100 to $748, then there are several transactions in the range of $1000, and then to the maximum of $1894.

  * Is there a higher number of fraudulent transactions made during this time frame versus the rest of the day?

    - **ANSWER:** See under section ***Part 1, Question 6*** in file - ***query.sql***  
    
	  Query 1 reveals that 30 potentially fraudulent transactions happened between 7am to 9am and averaging 15 transaction per hours block. Query 2 reveals that 320 potentially fraudulent transactions happened outside of 7am and 9am and averaging 14.54 transaction per hour block. Based on this data, we can see that the averages are very close. This tells us that there are potential fraudulent data occurring even outside of 7-9am.  But it is true that transactions are slightly higher during 7-9am windows
    

  * If you answered yes to the previous question, explain why you think there might be fraudulent transactions during this time frame.

    - **ANSWER:**  I think hackers may have picked this time of the day to make fraudulent transactions since customers are less likely to notice. The 7-9am usually a busy time  frame for people since its the start of the day. They generally busy getting ready for the day. During sleep time, it is awkward to see transactions like this since people are sleeping. So, 7-9am could be the best time for hackers.


* What are the top 5 merchants prone to being hacked using small transactions?
  
  - **ANSWER:** See under section ***Part 1, Question 8*** in file - ***query.sql*** 
  
    The top 5 Merchants that are prone to be hacked:
      <table>
        <tr>
          <th>Name</th>
          <th>Count</th>
        </tr>
        <tr>
          <td>Wood-Ramirez</td>
          <td>7</td>
        </tr>
        <tr>
          <td>Hood-Phillips</td>
          <td>6</td>
        </tr>
        <tr>
          <td>Baker Inc</td>
          <td>6</td>
        </tr>
        <tr>
          <td>Mcdaniel, Hines and Mcfarland</td>
          <td>5</td>
        </tr>  
        <tr>
          <td>Hamilton-Mcfarland</td>
          <td>5</td>
        </tr>   
      </table>
   
  
    
* Create a view for each of your queries.

  - **PART 1 Question 9 ANSWER:**  See section ***Create VIEWS for all queries*** in query.sql


---
