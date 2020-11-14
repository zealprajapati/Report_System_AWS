# Report_System_AWS
•	For this project, first created IAM user on AWS. And downloaded Access key and private key to connect AWS services to our java application.
•	After that I created S3 bucket to store the excel and pdf files.
•	Created following AWS 4 SQS in us-east-region-1:
	Excel_Request_Queue
	Excel_Response_Queue
	PDF_Request_Queue
	PDF_Response_Queue
•	Created SNS topic: reporting-topic
•	Then from Excel_Request_Queue and PDF_Request_Queue , subscribed to AWS SNS topic-reporting-topic
•	In IntelliJ, added credentials to application.properties file.
•	Run the program and downloaded PDF and Excel file from website.
•	From IntelliJ added a project on GIT using version control.
•	Committed all files to GIT.
•	From IntelliJ imported project on GitHub using credentials.
•	On GitHub deleted the AWS credentials from application.properties file, as got the message from AWS that IAM Secret Key is publicly available online on GitHub.
•	And committed changes.

After doing changes:
1. ExcelServiceImpl: generateFile(): 
    Stored excel file in S3 bucket.
2. ReportServiceImpl: sendDirectRequests():
    Changed to parallel process using Threadpool and CompleatableFuture.
3. ExcelGenerationController: downloadExcel():
    File name cannot be hardcoded. So used StringBuffer as used for multithreaded environment.
4. application.properties:
    Used VM options in configuartaion for AWS Credentials.
5. Created AWS RDS table instaed of h2 table.
    
