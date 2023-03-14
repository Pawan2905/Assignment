# TDK ASSIGNMENT
### Business Problem
We receive the raw data every day at 23:30 CET. We need to process the data and make it available in Oracle DB. Furthermore, need to update a few other summary tables which will be eventually consumed by visualization apps. Visualization application will be refreshed everyday at 03:00 AM CET.

### Task to Accomplish
1. Create pipeline for the above business case to support end-end.
2. Visualization tools need the below KPIs to show to business stakeholders.
- How many users are there?
- every user has made how many requests.
- Display total number of successful request.

### Data Available
- 182 log file shared 

### Data Dictionary
127.0.0.1 : This is the IP address of the client (remote host) which made the request to the server.

- : The "hyphen" in the output indicates that the requested piece of information is not available. In this case, the information that is not available is the RFC 1413 identity of the client determined by identd on the clients machine. 

2134: This is the userid of the person requesting the document as determined by HTTP authentication. 

[10/Oct/2000:13:55:36 -0700]: The time that the request was received. The format is: [day/month/year:hour:minute:second zone]

"GET /apache_pb.gif HTTP/1.0" : The request line from the client is given in double quotes. The request line contains a great deal of useful information. First, the method used by the client is GET. Second, the client requested the resource /apache_pb.gif, and third, the client used the protocol HTTP/1.0. 

200: This is the status code that the server sends back to the client. This information is very valuable, because it reveals whether the request resulted in a successful response (codes beginning in 2), a redirection (codes beginning in 3), an error caused by the client (codes beginning in 4), or an error in the server (codes beginning in 5). The full list of possible status codes can be found in the HTTP specification (RFC2616 section 10).

2326: The last part indicates the size of the object returned to the client, not including the response headers. If no content was returned to the client, this value will be "-". To log "0" for no content, use %B instead.


### Solution

- RAW DATA ----> ORACLE DB ----> VISUALIZATION TOOL

- Here we have used raw data (log files)
Step1. Aggregate the raw data
Step2. Extract the required key elements from the raw data
Step3. Transform the it into required format for such as date ,code etc
Step4. Load the data and find the required information from the data

#### Packages used 
Pandas,Numpy ,re,datetime

#### To run the scripts

Folder structure:
TDK_Assignment
    --> scr : contains srcipt for data preprocess and result (data_preprocess.py and result.py)
    -->logs : Raw data
    -->Output : preprocess data ,output with answer of all the question
    



