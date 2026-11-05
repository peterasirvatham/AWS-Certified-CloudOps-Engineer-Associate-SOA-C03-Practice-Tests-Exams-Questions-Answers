# REAS Corrected


### With the threat of ransomware viruses encrypting and holding company data hostage, which action should be taken to protect an Amazon S3 bucket?

- **Correct answer:** Enable Amazon S3 versioning on the bucket.


### A company has a mobile app that uses Amazon S3 to store images The images are popular for a week, and then the number of access requests decreases over time The images must be highly available and must be immediately accessible upon request A CloudOps Engineer must reduce S3 storage costs for the company. Which solution will meet these requirements MOST cost-effectively?

- **Correct answer:** Create a S3 Lifecycle policy to transition the images to S3 Standard-Infrequent Access (S3 Standard-IA) after 30 days.


### If your AWS Management Console browser does not show that you are logged in to an AWS account, close the browser and relaunch the console by using the AWS Management Console shortcut from the VM desktop. If the copy-paste functionality is not working in your environment, refer to the instructions file on the VM desktop and use `Ctrl+C`, `Ctrl+V` or `Command-C`, `Command-V`. Configure Amazon EventBridge to meet the following requirements. 1. Use the `us-east-2` Region for all resources. 2. Unless specified below, use the default configuration settings. 3. Use your own resource naming unless a resource name is specified below. 4. Ensure all Amazon EC2 events in the default event bus are replayable for the past 90 days. 5. Create a rule named `RunFunction` to send the exact message `{"name":"example"}` every 15 minutes to an existing AWS Lambda function named LogEventFunction. 6. Create a rule named `SpotWarning` to send a notification to a new standard Amazon SNS topic named `TopicEvents` whenever an Amazon EC2 Spot Instance is interrupted. Do NOT create any topic subscriptions. The notification must match the following structure: `Input path: {instance: detail.instance-id} Input template: The EC2 Spot Instance <instance> has been interrupted.` Important: Click the Next button to complete this lab and continue to the next lab. Once you click the Next button, you will NOT be able to return to this lab.

![Question 210](images/question210.png)

- **Correct answer:** In `us-east-2`, create an EventBridge archive on the default event bus with an event pattern for `source: ["aws.ec2"]` and a 90-day retention period. Create a scheduled rule named `RunFunction` with `rate(15 minutes)`, target the existing `LogEventFunction` Lambda function, and set constant JSON input to `{"name":"example"}`. Create a standard SNS topic named `TopicEvents`. Create an event-pattern rule named `SpotWarning` for `source: ["aws.ec2"]` and `detail-type: ["EC2 Spot Instance Interruption Warning"]`; target `TopicEvents` and configure the input transformer with `InputPathsMap` `{"instance":"$.detail.instance-id"}` and the template `The EC2 Spot Instance <instance> has been interrupted.` Do not create a topic subscription.


### A CloudOps Engineer configures `VPC` flow logs to publish to Amazon CloudWatch Logs. The CloudOps Engineer reviews the logs in CloudWatch Logs and notices less traffic than expected. After the CloudOps Engineer compares the `VPC` flow logs to logs that were captured on premises, the CloudOps Engineer believes that the `VPC` flow logs are incomplete. Which of the following is a possible reason for the difference in traffic?

- **Correct answer:** CloudWatch Logs throttling has been applied.


### Users are periodically experiencing slow response times from a relational database. The database runs on a burstable Amazon EC2 instance with a `350 GB` `General Purpose SSD (gp2)` Amazon Elastic Block Store (Amazon EBS) volume. A CloudOps Engineer monitors the EC2 instance in Amazon CloudWatch and observes that the `VolumeReadOps` metric drops to less than `10%` of its peak value during the periods of slow response. What should the CloudOps Engineer do to ensure consistently high performance?

- **Correct answer:** Convert the `gp2` volume to a `General Purpose SSD (gp3)` EBS volume.


### An application running on Amazon EC2 allows users to launch batch jobs for data analysis. The jobs are run asynchronously, and the user is notified when they are complete. While multiple jobs can run concurrently, a user's request need not be fulfilled for up to 24 hours. To run a job, the application launches an additional EC2 instance that performs all the analytics calculations. A job takes between 75 and 110 minutes to complete and cannot be interrupted. What is the MOST cost-effective way to run this workload?

- **Correct answer:** Run the application on On-Demand EC2 instances. Run the jobs on On-Demand EC2 instances.


### An e-commerce company wants to lower costs on its nightly jobs that aggregate the current day's sales and store the results in Amazon S3. The jobs are currently run using multiple on-demand instances and the jobs take just under 2 hours to complete. If a job fails for any reason, it needs to be restarted from the beginning. What method is the MOST cost effective based on these requirements?

- **Correct answer:** Submit a request for a one-time Spot Instance for job execution.


### A company wants to reduce costs on jobs that can be completed at any time. The jobs are currently run using multiple On-Demand Instances, and the jobs take just under 2 hours to complete. If a job fails for any reason, it can be restarted from the beginning. Which method is the MOST cost-effective based on these requirements?

- **Correct answer:** Submit a request for a one-time Spot Instance for job execution.


### A CloudOps Engineer is re-architecting an application. The CloudOps Engineer has moved the database from a public subnet, where the database used a public endpoint, into a private subnet to restrict access from the public network. After this change, an AWS Lambda function that requires read access to the database cannot connect to the database. The CloudOps Engineer must resolve this issue without compromising security. Which solution meets these requirements?

- **Correct answer:** Connect the Lambda function to the database `VPC`. Connect to the database using its private endpoint.


### A user has created a `VPC` with the public and private subnets using the `VPC` wizard. The `VPC` has `CIDR` `20.0.0.0/16`. The public subnet uses `CIDR` `20.0.1.0/24`. The user is planning to host a web server in the public subnet (port `80`) and a DB server in the private subnet (port `3306`). The user is configuring a security group for the public subnet (`WebSecGrp`) and the private subnet (`DBSecGrp`). Which of the below mentioned entries is required in the web server security group (`WebSecGrp`)?

- **Correct answer:** Configure port `80` inbound for source `0.0.0.0/0`.
