# Slick Requirements (DRAFT)

```
Notes:
- Where should I put information about package/module management with NPM workspaces and shared code? (added this to IMS stuff in 12 factor)
```

## Certifications
- AWS Certified Developer, AWS Solutions Architect Associate  

---

## Basic Understanding

### 12-Factor Application
**Maestro - Study Orchestration**  
- Assisted in design of Temporal Workflows to orchestrate clinical trial data, ensuring easy scalability and reliability via a **distributed and microservice** architecture. Temporal Workflows were utilized for automatic updates to system data via triggers and schedules, managed by a **plugin architecture** system.
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD and Gitub Actions, maintaining parody between environments with environement variables. System settings were stored in a repository, which is monitored by Argo CD for dynamic updates to environments.
- Utilized backing services such as S3 to manage plugins for Plugin Architecture in system. Also used S3 to store all actions between Temporal Workflows for transfering large amounts of data between Temporal activities -- this also had the benifit of storing all activity data for auditing purposes.
- Maintained **disposability and robusteness**  of temporal worker by designing a remediation mechanism into system startup. On startup, application would pull all existing plugins from S3 to create/delete any workflow schedule that may have been out of sync if system was offline.
- Created dynamic workflows for trial coordinators to adapt patient activities based on clinical protocol requirements using React Flow, Next.js, JDM models with Zen Engine.
- Used Docker with docker-compose for local development of multiple micro services running simultaneously with a Makefile. Implemented localstack to spin up AWS services locally(DynamoDB, S3) through docker-compose.

**SRE Responsibilities & IMS**  
- Adhered to **externalized configurations** and environment variable management using AWS for event-driven microservices.  
- Utilized **stateless services** for Lambda functions interacting with SNS and SQS queues.
- Maintained **disposability and robusteness** with a remediation Lambda that would scan for ownership status if Ownership System was offline during resource collection.
- Created **admin specific** page within app to update critical data. Admin page would check JWT for correct Azure group before allowing access to page. Admin could update important system data for Heroku Stack lifecycle updates. Admin could also stage outdated and unclaimed Heroku applications for spindown.
- Used Docker with docker-compose for local development of backend event-driven services. Implemented localstack to spin up AWS services locally(SNS, SQS) through docker-compose.
- Used NPM workspaces to structure monorepo of multiple services and modules. This included Lambda Layers that were dynamically structured for deployment.
---

### Deployment, Scaling, and Management of Containerized Applications
**Maestro - Study Orchestration**  
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling.  
- Utilized KCL(Kinesis Client Library) with Kinesis Streams to process streaming data reliably at scale and manage sharding of database.

**SRE Responsibilities & IMS**   
- Migrated enterprise Vue and React applications to ECS with automated pipelines for CI/CD using GitHub Actions.
- Gained expert understanding  of CI/CD practices GitHub Actions, Cloudformation, AWS CLI, Docker, Artifactory.
- Used SNS, SQS and Lambdas for resource collection, which allowed for scaling of compute processes during resource scanning and DB updates. 
- Used Lambda API and Dataloader for cached querying to SQL database.
- Deployed and managed containerized applications that managed multiple SASS products that client was using.
- Utilized health checks and rolling updates to ensure system stability.

---

## Strong Understanding

### Performance Tuning
**SRE Responsibilities & IMS**    
- Reduced Heroku utilization by lowering enterprise footprint by 20% in Heroku apps and resources. This was done by managing timestamped updates when certain notifactions were sent out to potential owners of Heroku resources. Warnings and notifications were triggered by AWS Eventbridge and then monitored to track which notifications were sent to certain application teams(**state machine**). This allowed the pruduct owner to confidently delegate the spin down unused resources.
- Reduced Contentful space utilization by lowering enterprise footprint 25%. This was achieved by tracking when spaces were last used. A script would run nightly and tag the spaces that had not been utilized in the last 180 days. Memebers of these Contentful sites were sent notifications automatically to delete their spaces if they were not being used. This data also gave the product owner confidence and neccessary data to delegate the removal of spaces that were not being used.
- Recognized need for increased memory in API worker, speeding up queries to DB considerably.
- Drove refactor of original Contentful IMS by parodying the exiting architecture for the Heroku IMS. By utilizing event-driven architecture, the refactor allowed for resources to scale during resoure collection and loading. This cut resource collection in half after it was complete. It also drastically improved code update speed and delivery.

**Maestro - Study Orchestration**  
- Improved workflow execution speed by optimizing Temporal plugin queries and utilizing batched data fetches.
*MORE HERE*  

### Business Analysis
**Maestro - Study Orchestration**  
- Conducted application design sessions with product owners to refine business rules for non-technical user configurability. This resulted in work on a new business rule management system using React Flow. This solution aims to empower non-technical users to configure site-specific rules within the application, making the system adaptable, user-centric and scalable. This expansion has the potential to scale the project significantly, as it could lead to a larger team in future project phases. Through these efforts, I’ve actively contributed to enhancing both the application’s functionality and its potential for broader business impact. 
- Documented and analyzed clinical trial workflows to ensure alignment with business and compliance needs.
  
**Data Marketplace**  
- Collaborated with UX teams to align evolving user interface designs with business objectives, ensuring rapid prototyping.  
- Delivered iterative updates to meet changing marketplace requirements.
  
**SRE Responsibilities & IMS**
- Worked closely with product owner of multiple SASS products to develop and architect multiple programs and applications ensuring user management, resource management, authentication to products. 

### Infrastructure as Code
**SRE Responsibilities & IMS**  
- Developed CloudFormation templates to automate ECS service deployments and resource provisioning.  
- Automated secret rotation and access management using AWS Secrets Manager within IaC templates.  

**Maestro - Study Orchestration**  
- Managed Kubernetes deployments through Helm charts, enabling version control and consistent application setup.  
- Designed infrastructure using OpenShift templates to simplify container management.  

### Test-Driven Development
**Maestro - Study Orchestration**  
- Developed unit tests for Temporal workflows using pytest to validate plugin behavior and ensure data integrity.  
- Implemented contract testing for GraphQL APIs to catch breaking schema changes early in the pipeline.

**Lilly Trial Guide**  
- Used Jest to ensure robust test coverage for the Next.js application, particularly for multilingual support.  

### GraphQL
**Maestro - Study Orchestration**  
- Designed GraphQL resolvers for querying DynamoDB audit logs, enhancing developer productivity with simplified data access.  
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Used PynamoDB Models and Strawberry GraphQL types to maintain a strict adherance to schama.

**SRE Responsibilities & IMS**  
- Designed robust database design and GraphQL API that used Dataloader for cached querying to SQL database.
- Created pagination mechanism via GraphQL for paging through large DB queries.
- Simplified user access setup in Graphql API by creating user context class that checks the users token as well as the indicators as to whether the call came from an internal app.

**Lilly Trial Guide**  
- Used GraphQL for efficient data retrieval and integrated it with a responsive frontend.
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Implemented mechanism that would pull Contentful Schema and compare updated schema to our app typings, maintaining a 1 to 1 relationship with Sass product updates and codebase.

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
- Applied **Saga Pattern** for orchestrating distributed transactions across DynamoDB tables, ensuring data consistency during workflow execution and exexuted rollbacks when needed.  
- Built a **plugin-based architecture** to allow the addition of new integrations without disrupting existing workflows. Plugins are loaded into an EIC(External Interface Controller) that manage metadata on when Temporal schedules should run, where they should get their data, where to send their data. This ETL system is the backbone of the entire application, allowing the system to scale to any amount of Clinical trial sites that want to be onboarded to the system.

**SRE Responsibilities & IMS**  
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work accross the system.
- Used **State Machine Pattern** for managing the compliance of resources that were created on Heroku. This was done by managing timestamped updates when certain notifactions were sent out to potential owners of Heroku resources. Warnings and notifications were triggered by cron jobs and then monitored to track which notifications were sent to certain application teams. This allowed the pruduct owner to confidently delegate the spin down unused resources.

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
- Managed ingress and egress for systems running on Kuberneties, creating service accounts and rules that allowed or dissallowed services to talk with each other.
- Manage DNS, certificate creation, and load balancing for UI application.
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.

**SRE Responsibilities & IMS**  
- Built serverless architectures using AWS Lambda, SNS, and SQS to streamline data flow and reduce latency. Utilized SQS retries for system error handling.
- Utilized roles and security groups for granular access to resources created for applications.
- Designed DynamoDB table schemas to optimize for high-volume reads and writes with cost efficiency.  
- Manage DNS, certificate creation, and load balancing for multiple UI applications.
- Used Azure Enterprise Apps to create client credentials and manage user access to applications.
  
### Systems Analysis & Design
**Maestro - Study Orchestration**  
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Reaserched and designed POC for workflow management system that can be configured via React Flow diagrams. This allows users to granularly control their clinical trial site by adding workflow steps that result in system changes and activities/tasks being created automatically. 
- Designed and implemented a scalable audit log system using AWS Kinesis Streams and DynamoDB to handle high-throughput updates.

**SRE Responsibilities & IMS**  
- Pushed refactor of one IMS application that was similar to another. Refactored application over very short timeframe and allowed for seemless updates to be integrated that were once very time consuming due to bad architecture.

**eCTS**  
- Redesigned legacy systems into microservices for improved modularity and maintainability. Utilized Lambdas and shared code to share data between microservices.
- Built serverless architecure API that was agnostic to the original system and schema so that data could be constumed accross enterprise. Used transformer classes to translate inconsistant data in legacy database that was still required.
  
**Data Marketplace**  
- Project required agile, flexible UI development, and I worked directly with product owners and UX to rapidly iterate on prototypes that aligned with evolving business goals.
---


## **Experience**
- **Work Experience**:
   - Over 6 years of multi-project client experience, notably with Eli Lilly.

### Maestro - Study Orchestration(2024-Present):

For the Maestro Study Orchestration project, I took on a lead role to ensure critical business requirements were met for an application that helps Clinical Trial Coordinators track and update patient activities within trials. I designed and implemented Temporal Workflows to fetch data from external databases, using a plug-in architecture for better scalability and flexibility. My work on DynamoDB involved complex data structures, managed through GraphQL and coordinated with the Saga Pattern for robust, multi-table updates. Additionally, I set up an audit log system with Kinesis Streams to track all entity updates, which strengthened our system’s traceability and monitoring capabilities.

Recently, I initiated work on a new business rule management system using React Flow. This solution, currently in the research phase with the product owner, aims to empower non-technical users to configure site-specific rules within the application, making the system adaptable, user-centric and scalable. This expansion has the potential to scale the project significantly, as it could lead to a larger team in future project phases. Through these efforts, I’ve actively contributed to enhancing both the application’s functionality and its potential for broader business impact.


### LillyDev SRE Responsibilities & IMS (Inventory Management System)(2021-2024):

As a Senior Site Reliability Engineer, I oversaw various shared services within Lilly’s DevOps community, such as the LillyDev React site and migration tools on ECS. My role involved setting up infrastructure as code with CloudFormation, monitoring performance, and implementing scalable solutions.

One of the major projects I took part in as an SRE was the IMS project. In this project, I led the development of microservices and SPAs that provided visibility into SASS products being used across the enterprise. This event-driven architecture used SNS, SQS, and Lambda functions to automate notifications and update statuses, improving data integrity. The project required rigorous database design and optimization skills, which I applied to manage lifecycle states and automate ownership processes. I collaborated closely with product owners and UX, deploying with GitHub Actions and using CloudFormation to maintain clean, scalable code.  In leading this effort, I was responsible for reducing the overall enterprise footprint by over 20% on Heroku and 25% on Contentful. By employing best practices and collaboration with the client, I built a framework that simplified operations and reduced resource usage.


### eCTS (Enterprise Clinical Trial System)(2020 - 2021):

As a senior engineer on the eCTS project, I contributed to modernizing a legacy clinical trial management system with TypeScript, AWS Lambdas, and API Gateway. This involved designing microservices and serverless architectures that minimized dependencies on older systems. My work extended to maintaining an agile development flow, ensuring we met strict business and compliance requirements. This experience deepened my understanding of event-driven architectures and cloud-native development while allowing me to directly support the scalability and performance goals of the organization.


### Data Marketplace(2019 - 2020):

The Data Marketplace project required agile, flexible UI development, and I worked directly with product owners and UX to rapidly iterate on prototypes that aligned with evolving business goals. I used AWS CloudFront, CodePipeline, and CloudFormation to deploy a responsive React frontend, establishing a CI/CD pipeline for smooth releases. This project helped me hone my skills in requirements analysis and design patterns, focusing on delivering a product that was adaptable, efficient.


### Lilly Trial Guide(2018 - 2019):

I helped in the developent of a major overhaul of a public-facing application, moving it from React/Sails to a Next.js/Express stack. We worked closely with product owners and UX for agile iterations with strict adherence to company guidelines. I helped implement scalable solutions, including deploying to Heroku and integrating with Contentful and Elastic Search, making the app easily configurable and efficient. I assisted in streamlining deployment with CI/CD, ensuring a reliable, maintainable product that met Lilly’s high standards for accessibility and multilingual support.


