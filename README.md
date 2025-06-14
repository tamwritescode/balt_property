## Baltimore City Vacant Property Revitalization Data Hub

This project tackles a critical challenge facing Baltimore: the widespread issue of vacant and abandoned properties. These properties aren't just empty spaces; they contribute to blight, increased crime, depreciating property values, and a lower quality of life for our residents. My aim with this Data Hub is to transform how the city and local communities understand and address this problem, turning raw data into actionable insights.

### Project Goals: 
- Improve resource allocation: By providing a clearer picture of the problem, we can help city agencies and community organizations identify and prioritize vacant properties for intervention, whether that's demolition, renovation, or greening initiatives.

- Increase transparency and accountability: The project aims to offer a transparent view of vacant property status, ownership, and ongoing revitalization efforts, making this vital information accessible to the public and ensuring greater accountability.

- Empower community initiatives:  Providing data-driven insights will equip neighborhood groups to advocate more effectively for specific actions and actively participate in revitalizing their areas.

- Enhance public safety: By addressing the root causes of blight through data-informed interventions, we can indirectly contribute to creating safer and more vibrant neighborhoods in Charm City!

## Technical Architecture and Core Services
To achieve these goals, I've designed a robust and efficient cloud-based data platform. Here's a look at the core services powering this Hub:

### Core Services 
- AWS S3 (Simple Storage Service): This is the heart of my data lake. All raw data flows into S3, and once cleaned and transformed, the refined, analysis-ready datasets reside here, optimized for quick access.

- AWS Glue: Serving as my main ETL (Extract, Transform, Load) engine, Glue is responsible for orchestrating the data journey. It efficiently reads raw data from S3, performs critical cleaning and transformation using PySpark (Python with Apache Spark), and then writes the refined data back to S3. Glue's Data Catalog also acts as a central registry, making all datasets easily discoverable.

- Python: My primary scripting language, Python is vital for various tasks, from fetching initial data from public APIs and orchestrating AWS services using boto3, to crafting the complex transformation logic within the AWS Glue jobs.

- AWS Lambda: These serverless compute functions are the backbone of my automation. Lambdas enable event-driven tasks, such as automatically triggering a Glue job the moment a new data file lands in S3, or regularly pulling smaller datasets on a schedule.

- AWS Athena: This is my go-to query engine for analytics. Athena allows me to run standard SQL queries directly against the processed data stored in S3, leveraging Glue's Data Catalog for schema awareness. It's perfect for ad-hoc analysis and preparing data for dashboards


### Essential Supporting Services
Beyond the core data flow, several crucial services ensure the Hub operates securely, reliably, and transparently:

- AWS IAM (Identity and Access Management): My foundation for security and permissions. IAM ensures that only authorized users and AWS services (like Glue and Lambda) have the necessary access to specific resources and data within the Hub.

- AWS CloudWatch: For comprehensive monitoring and logging. CloudWatch collects vital operational data from Lambda and Glue, enabling me to track performance, identify issues, and set up alerts for critical events.

- AWS SNS (Simple Notification Service): Integrated with CloudWatch, SNS is how I receive alerts and notifications about pipeline status or any potential failures, ensuring I can address issues promptly.

## Remarks
This Data Hub isn't just about technology; it's about leveraging data to build a stronger, healthier Baltimore. By making information on vacant properties more accessible and actionable, we can empower communities and accelerate vital revitalization efforts.