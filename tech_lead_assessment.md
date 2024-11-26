# Slick Requirements (DRAFT)

Notes:
- Where should I put information about package/module management with NPM workspaces and shared code?

## Certifications
- AWS Certified Developer, AWS Solutions Architect Associate  

---

## Basic Understanding

### 12-Factor Application
**Maestro - Study Orchestration**  
- Assisted in design of Temporal Workflows to orchestrate clinical trial data, ensuring easy scalability and reliability via a **distributed and microservice** architecture. Temporal Workflows were utilized for automatic updates to system data via triggers and schedules, managed by a **plugin architecture** system.
- Automated release processes using **GitHub Actions** and Kubernetes rollout strategies via Argo CD and Gitub Actions, maintaing parody between environments with environement variables. System settings were stored in a repository, which is monitored by Argo CD for dynamic updates to environments.
- Utilized backing services such as S3 to manage plugins for Plugin Architecture in system. Also used S3 to store all actions between Temporal Workflows for transfering large amounts of data between Temporal activities -- this also had the benifit of storing all activity data for autiting perposes.
- Maintained **disposability and robusteness**  of temporal worker by designing a remediation mechanism into system startup. On startup, application would pull all existing plugins from S3 to create/delete any workflow schedule that may have been out of sync if system was offline.

**SRE Responsibilities & IMS**  
- Adhered to **externalized configurations** and environment variable management using Heroku for event-driven microservices.  
- Utilized **stateless services** for Lambda functions interacting with SNS and SQS queues.
- Maintained **disposability and robusteness** with a remediation Lambda that would scan for ownership status if Ownership System was offline during resource collection.
- Created **admin specific** page within app to update critical data. Admin page would check JWT for correct Azure group before allowing access to page. Admin could update important system data for Heroku Stack lifecycle updates. Admin could also stage outdated and unclaimed Heroku applications for spindown.

**Data Marketplace**  
- Deployed a responsive React frontend with configurations managed through environment variables for seamless development and production transitions.  
- Automated deployments and releases with AWS CodePipeline, adhering to 12-factor principles.  

---

### Deployment, Scaling, and Management of Containerized Applications
**Maestro - Study Orchestration**  
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling.  
- Utilized KCL(Kinesis Client Library) with Kinesis Streams to process streaming data reliably at scale and manage sharding.

**SRE Responsibilities & IMS**   
- Migrated enterprise React applications to ECS with automated pipelines for CI/CD using GitHub Actions.  
- Used SNS, SQS and Lambdas for resource collection, which allowed for scaling of compute processes during resource scanning and DB updates. 
- Used Lambda API and Dataloader for cached querying to SQL database.

** SRE Resposibilities **
- Deployed and managed mutliple containerized application that managed multiple SASS products that Client was using. Utilized health checks and rolling updates to ensure system stability.

---

## Strong Understanding

### Performance Tuning
**LillyDev SRE Responsibilities & IMS**  
- Optimized DynamoDB queries by redesigning table structures and indexing strategies, reducing read costs by 20%.  
- Reduced Heroku app utilization by consolidating redundant services and migrating legacy dependencies.  

**Maestro - Study Orchestration**  
- Improved workflow execution speed by optimizing Temporal plugin queries and utilizing batched data fetches.  
- Streamlined data storage by restructuring DynamoDB schemas, reducing storage overhead by 25%.  

### Business Analysis
**Maestro - Study Orchestration**  
- Conducted application design sessions with product owners to refine business rules for non-technical user configurability.  
- Created dynamic workflows for trial coordinators to adapt patient activities based on clinical protocol requirements.  

**Data Marketplace**  
- Collaborated with UX teams to align evolving user interface designs with business objectives, ensuring rapid prototyping.  
- Delivered iterative updates to meet changing marketplace requirements.  

### Infrastructure as Code
**LillyDev SRE Responsibilities & IMS**  
- Wrote CloudFormation templates to automate ECS service deployments and resource provisioning.  
- Automated secret rotation and access management using AWS Secrets Manager within IaC templates.  

**Maestro - Study Orchestration**  
- Managed Kubernetes deployments through Helm charts, enabling version control and consistent application setup.  
- Designed infrastructure using OpenShift templates to simplify container management.  

### Test-Driven Development
**Maestro - Study Orchestration**  
- Developed unit tests for Temporal workflows using **pytest** to validate plugin behavior and ensure data integrity.  
- Implemented contract testing for GraphQL APIs to catch breaking schema changes early in the pipeline.  

**Lilly Trial Guide**  
- Used Jest to ensure robust test coverage for the Next.js application, particularly for multilingual support.  

### GraphQL
**Maestro - Study Orchestration**  
- Designed GraphQL resolvers for querying DynamoDB audit logs, enhancing developer productivity with simplified data access.  
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls by 40%.  

**Lilly Trial Guide**  
- Used GraphQL for efficient data retrieval and integrated it with a responsive frontend.  

---

## Advanced Understanding

### Serverless Technologies
**SRE Responsibilities & IMS**  
- Developed event-driven workflows using Lambda, SNS, and SQS to process and notify changes in SASS inventory states. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work accross the system.
- Leveraged AWS Eventbridge and to trigger Lambdas for near processing of IMS updates.

**Maestro - Study Orchestration**  
- Built AWS Lambda-based processing for integrating Temporal workflows with external data sources.  
- Enhanced audit logging with DynamoDB streams for real-time monitoring.  

### Design Patterns
**Maestro - Study Orchestration**  
- Applied **Saga Pattern** for orchestrating distributed transactions across DynamoDB tables, ensuring data consistency during workflow execution.  
- Built a plugin-based architecture to allow the addition of new integrations without disrupting existing workflows. Plugins are loaded into an EIC(External Interface Controller) that manage metadata on when Temporal schedules should run, where they should get their data, where to send their data. This ETL system is the backbone of the entire application, allowing the system to scale to any amount of Clinical trial sites that want to be onboarded to the system.

**SRE Responsibilities & IMS**  
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work accross the system.
- Used **State Machine Pattern** for managing the compliance of resources that were created on Heroku. This was done by managing timestamped updates when certain notifactions were sent out to potential owners of Heroku resources. Warnings and notifications were triggered by cron jobs and then monitored to track which notifications were sent to certain application teams. This allowed up to confidently spin down unused resources.

### DevOps Tooling
**Maestro - Study Orchestration**  
- Used GitHub Actions to implement CI/CD pipelines application deployments.  
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD, maintaing parody between environments with environement variables.

**SRE Responsibilities & IMS**  
- Migrated approx 10 applications from Code Pipeline to Github Actions. All applications had various deployment methods to multiple AWS services. After this update, all applications had a uniform deployment process that streamlined development.

**All Applications**  
- Built CI/CD pipelines with CodePipeline and Github Actions for frontend and backend deployments, ensuring quick turnaround for updates.
- Used automated testing, linting and format checking in CI pipelines to maintain greater control over codebase updates.
- Managed schema updates with migration strategies. Used timestamped migration files for easy rollback of postgres dbs, triggered by a Lambda on system deployment.
 

---

## Expert Understanding

### Core Cloud Concepts
**Maestro - Study Orchestration**    
- Managed ingress and egress for systems running on Kuberneties, creating service accounts and rules that allowed or dissallowed services to talk with eachother.
- Manage DNS, certificate creation, and load balancing for UI application.
- Documented and analyzed clinical trial workflows to ensure alignment with business and compliance needs.
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.

**SRE Responsibilities & IMS**  
- Built serverless architectures using AWS Lambda, SNS, and SQS to streamline data flow and reduce latency. Utilozed SQS retries for system error handling.
- Utilized roles and security groups for granular access to resources created for applications.
- Designed DynamoDB table schemas to optimize for high-volume reads and writes with cost efficiency.  
- Manage DNS, certificate creation, and load balancing for multiple UI applications.
- Used Azure Enterprise Apps to create client credentials and manage user access to applications.
  
### Systems Analysis & Design
**Maestro - Study Orchestration**  
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Reaserched and designed POC for workflow management system that can be configured via React Flow diagrams. This allows users to granularly control their clinical trial site by adding workflow steps that result in system changes and activities/tasks being created automatically. 
- Designed and implemented a scalable audit log system using AWS Kinesis Streams and DynamoDB to handle high-throughput updates.

** SRE Responsibilities & IMS**  
- Pushed refactor of one IMS application that was similar to another. Refatored application over very short timeframe and allowed for seemless updates to be integrated that were once very time consuming due to bad architecture.

**eCTS**  
- Redesigned legacy systems into microservices for improved modularity and maintainability.  
- Built serverless architecure API that was agnostic to the original system and schema so that data could be constumed accross enterprise. Used transformer classes to translate inconsistant data in legacy database that was still required

---
