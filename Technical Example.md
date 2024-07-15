CUSTOMER OBESSION 

Describe a situations when you have a very difficult customer or describe a situations where you negotiated a win win 

1) Situation: An e-commerce company suffers downtime and performance issues during peak seasons, causing revenue loss and customer dissatisfaction due to an inability to handle traffic spikes.

Task: As a DevOps engineer, enhance the website's reliability and performance during peak periods by implementing AWS solutions to improve customer trust and satisfaction through better performance.

Action :
Scalable Architecture: Use AWS Auto Scaling for dynamic EC2 instances and ELB for traffic distribution.
CDN: Deploy Amazon CloudFront to cache static content and reduce origin load.
Database Optimization: Migrate to Amazon RDS with read replicas and use DynamoDB for high-demand, low-latency data.
Monitoring and Alerts: Implement Amazon CloudWatch for real-time monitoring and alerts.
Disaster Recovery: Use multi-AZ deployment and AWS Backup for high availability and quick recovery.
Cost Management: Utilize AWS Cost Explorer and Trusted Advisor, and apply Reserved Instances or Savings Plans.


Result:
Improved Reliability: Scalable infrastructure and optimized performance increase availability during peak periods.
Enhanced User Experience: Reduced downtime and faster load times boost customer satisfaction and trust.
Business Impact: Improved website performance leads to higher revenue retention and customer loyalty, aligning with AWS's Customer Obsession principle by prioritizing customer needs and satisfaction.


2) Situation: The customer used On-Demand instances for development and staging, leading to high operational costs.

Task: My role was to reduce their costs while maintaining stability and efficiency.

Action: I analyzed their usage and recommended switching to Spot Instances. I explained the benefits and risks, guided them through the transition, and monitored the process to address any issues.

Result: The customer significantly reduced their costs without workflow disruption, stayed within budget, and our relationship strengthened due to our proactive support and commitment.


------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
OWNERSHIP 

Tell me about the tough decision you made during a project or descirbe a tough situations where you have to step into a leadership role.

Situation

After deploying a new microservices application on Amazon EKS, our team noticed intermittent service failures and network latency spikes, affecting 60% of their user experience.
Task

As the DevOps engineer, I needed to identify the root causes of these issues and stabilize the application to ensure high availability and improved performance.
Action

    Logs and Metrics Analysis: Analyzed pod logs and CloudWatch metrics, identifying OutOfMemoryError and network timeouts.
    Resource Utilization: Reviewed resource utilization, finding some nodes heavily loaded while others were underutilized.
    Network Configuration: Inspected network policies using kubectl get network policy and VPC settings, discovering inefficiencies in our network setup.

Root Cause Analysis:

    Incorrect memory requests and limits causing pod evictions.
    Improper HPA and pod affinity rules leading to uneven load distribution.
    Default service types causing network bottlenecks.

Resolution:

    Adjusted memory requests and limits.
    Reconfigured HPA and pod affinity rules for balanced load.
    Optimized network configuration by changing service types and implementing network policies.

Result

    Improved Stability and Performance: No more pod crashes and balanced resource usage.
    Reduced Network Latency: Enhanced user experience with efficient traffic handling.
    Increased Customer Satisfaction: Positive feedback due to improved application reliability and performance.

By taking ownership, analyzing the problem, and implementing targeted solutions, I stabilized our EKS deployment and enhanced application performance.

— — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — — —
Situation

Our EKS-based application experienced downtime and performance degradation during peak traffic hours, impacting business revenue and customer satisfaction.
Task

As the lead DevOps engineer, I needed to identify and resolve the root causes of the downtime and performance issues to ensure the application could handle peak loads effectively.
Action

    Monitoring and Analysis: Reviewed CloudWatch metrics, application logs, and resource utilization.
    Root Cause Identification: Found issues with HPA not scaling pods quickly enough, low resource limits causing pod throttling, and insufficient node capacity.
    Resolution Implementation:

    Adjusted HPA settings for quicker scaling.
    Increased CPU and memory limits for pods.
    Deployed Karpenter to dynamically manage node scaling and ensure sufficient capacity during traffic spikes

4. Testing and Validation: Conducted load testing and set up enhanced monitoring and alerting.
Result

    Improved Performance and Availability: Application handled peak traffic without downtime or performance issues.
    Scalable Infrastructure: Optimized autoscaling and resource management, including Karpenter, ensured dynamic adjustment to traffic changes.
    Increased Customer Satisfaction: Enhanced performance and reliability led to higher customer satisfaction and fewer support tickets.

By taking ownership of the issue and implementing targeted solutions with Karpenter, I ensured our EKS-based application could reliably handle peak traffic, improving performance and customer satisfaction.



-----------------------------------------------------------------------------------------------------------------------------------------------------------------

Invent and simplify 

Situation:
A new CloudFormation stack needed to be created for a backend EC2 instance that was not previously part of any stack.
The stack required a new VPC, subnet, security group, and autoscaling group launching an EC2 instance based on the original instance's AMI.
After deploying the CDK app, all requests to the new instance's endpoints failed with the error: connect ECONNREFUSED.

Task:
Troubleshoot and resolve the connection issue with the new EC2 instance to ensure it operates correctly.

Action:
Security Group Rules:

Verified inbound HTTP traffic on port 80 was allowed.
Confirmed outbound rules were correct.

Subnet and Internet Gateway:

Ensured the subnet had a route to an internet gateway.
Verified connectivity by pinging a sample URL from the EC2 instance.

Region and VPC Configuration:

Noted that the new EC2 instance was in a different region than the source EC2 and RDS instances.
Allowed all inbound traffic on the RDS instance temporarily for testing.

VPC Peering Setup:

Established VPC peering between the new and original VPCs.
Updated route tables to enable proper traffic routing between VPCs.

Application Configuration and Dependencies:

Checked application logs on the new EC2 instance for errors.
Ensured all dependencies and configurations from the original instance were replicated correctly.

Result:
Successful Communication: VPC peering and route table updates resolved the ECONNREFUSED error, enabling communication between the new EC2 instance and the RDS instance.
Operational Endpoints: The new EC2 instance's endpoints became accessible, serving requests correctly.
Scalable and Reliable Setup: The new stack improved the reliability and scalability of the backend infrastructure.

Using the AWS Leadership Principle: Invent and Simplify:
Streamlined the replication process of the backend infrastructure using CDK.
Simplified architecture with VPC peering and proper network route configurations, ensuring seamless communication and providing a scalable and efficient solution for future deployments.

-----------------------------------------

Situation: A company needed to manage and serve a large volume of static assets (like images, videos, and documents) for its web application. These assets were initially stored on a traditional on-premises server, which was costly to maintain and scale. The manual management of these assets was time-consuming, and the performance for end-users was inconsistent.

Task: As the DevOps engineer, the task was to find a more efficient, scalable, and cost-effective solution for storing and serving static assets. The solution needed to simplify the current setup, reduce costs, and improve performance.

Action:

    Identify the Requirements:

    Analyzed the storage needs, access patterns, and performance requirements.
    Considered factors like durability, availability, and security.

2. Leverage AWS S3:

    Proposed the use of Amazon S3 for storing static assets due to its scalability, durability (99.999999999%), and cost-effectiveness.
    Created an S3 bucket to store all static assets.
    Configured bucket policies and IAM roles to manage access and ensure security.

3. Simplify Asset Management:

    Automated the upload process using AWS SDKs and CLI to ensure assets were automatically uploaded to the S3 bucket.
    Implemented lifecycle policies to transition older assets to infrequent access or archive storage classes to save costs.

4. Enhance Performance with CloudFront:

    Set up Amazon CloudFront as a content delivery network (CDN) to cache and serve the static assets from edge locations around the world, reducing latency and improving user experience.
    Configured CloudFront distribution to use the S3 bucket as the origin.

5 . Monitor and Optimize:

    Enabled logging and monitoring to track access patterns and performance.
    Used S3 analytics to gain insights into storage usage and optimize costs further.

Result:

    Cost Savings: The transition to S3 significantly reduced storage costs compared to on-premises servers.
    Improved Performance: Users experienced faster load times due to CloudFront’s global edge locations.
    Simplified Management: Automating asset uploads and implementing lifecycle policies reduced the manual effort required for asset management.
    Scalability and Reliability: The solution provided a highly scalable and reliable storage solution, capable of handling future growth without additional operational overhead.

