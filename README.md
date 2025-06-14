## Baltimore City Vacant Property Revitalization Data Hub

### Preliminary Research:
- Baltimore, MD has a significant challenge with vacant and abandoned properties, which contribute to blight, crime, decreased property values, and reduced quality of life for residents. 

### Goals: 
- Improve resource allocation
- Increase transparency and accountability 
- Empower community initiatives
- Enhance public safety

### Core Services 
- AWS S3 (Simple Storage Service): my central data lake
- AWS Glue: main ETL, handles reading data from S3, cleaning and transforming using PySpark, and finally writes a refineded version back to S3 
- Python: primary scripting lang., extracts from public APIs, orchestrating AWS services via boto3, and writing the transformation logic within my Glue jobs
- AWS Lambdas: serverless compute for automation for event-driven tasks (automatically triggering a Glue job when a new data file lands in S3, or fetchng small datasets on a schedule)
- AWS Athena: query engine for analytics 

### Essential Suuporting Services 
- AWS IAM (Identity and Access Management): security and permissions
- AWS CloudWatch: monitoring and logging 
- AWS SNS (Simple Notification Service) - alerts and notifications 