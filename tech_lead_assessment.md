# Jacob Victor Berg - Senior Software Engineer/ Site Reliability Engineer

## Certifications
- AWS Certified Developer, AWS Solutions Architect Associate  

## Modus Operandi:
- Acted as a senior engineer, guiding technical business guidance and assisting developers across multiple projects. Assisted in technical interviews.

---

### 12-Factor Application
**Maestro - Study Orchestration**  
- Assisted in design of Temporal Workflows to orchestrate clinical trial data, ensuring easy scalability and reliability via a **distributed and microservice** architecture. Temporal Workflows were utilized for automatic updates to system data via triggers and schedules, managed by a **plugin architecture** system.
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD and GitHub Actions, maintaining parity between environments with environment variables. System settings were stored in a repository, which is monitored by Argo CD for dynamic updates to environments.
- Utilized backing services such as S3 to manage plugins for Plugin Architecture in system. Also used S3 to store all actions between Temporal Workflows for transferring large amounts of data between Temporal activities—this also had the benefit of storing all activity data for auditing purposes.
- Maintained **disposability and robustness** of Temporal worker by designing a remediation mechanism into system startup. On startup, application would pull all existing plugins from S3 to create/delete any workflow schedule that may have been out of sync if system was offline.
- Created dynamic workflows for trial coordinators to adapt patient activities based on clinical protocol requirements using React Flow, Next.js, JDM models with Zen Engine.
- Used Docker with docker-compose for local development of multiple microservices running simultaneously with a Makefile. Implemented localstack to spin up AWS services locally (DynamoDB, S3) through docker-compose.

**SRE Responsibilities & IMS**  
- Adhered to **externalized configurations** and environment variable management using AWS for event-driven microservices.  
- Utilized **stateless services** for Lambda functions interacting with SNS and SQS queues.
- Maintained **disposability and robustness** with a remediation Lambda that would scan for ownership status if Ownership System was offline during resource collection.
- Created **admin-specific** page within app to update critical data. Admin page would check JWT for correct Azure group before allowing access. Admins could update important system data for Heroku Stack lifecycle updates and stage outdated or unclaimed Heroku applications for spin-down.
- Used Docker with docker-compose for local development of backend event-driven services. Implemented localstack to spin up AWS services locally (SNS, SQS) through docker-compose.
- Used NPM workspaces to structure a monorepo of multiple services and modules. This included Lambda Layers that were dynamically structured for deployment.

**Trial Guide**
- Deployed a Heroku application with environments, including a pre-production environment for blue-green deployment.
- Used Contentful resources to dynamically build React components based on resource type.
- Maintained a CMS model management system to synchronize Contentful environments.
- Created a script to run and update TypeScript types pulled from Contentful.

---

### Deployment, Scaling, and Management of Containerized Applications
**Maestro - Study Orchestration**  
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling.  
- Utilized KCL (Kinesis Client Library) with Kinesis Streams to process streaming data reliably at scale and manage database sharding.

**SRE Responsibilities & IMS**  
- Migrated enterprise Vue and React applications to ECS with automated pipelines for CI/CD using GitHub Actions.
- Gained expert understanding of CI/CD practices, GitHub Actions, CloudFormation, AWS CLI, Docker, and Artifactory.
- Used SNS, SQS, and Lambdas for resource collection, allowing for scaling of compute processes during resource scanning and DB updates. 
- Used Lambda API and Dataloader for cached querying to SQL databases.
- Deployed and managed containerized applications for multiple SaaS products used by client.
- Utilized health checks and rolling updates to ensure system stability.

---

### Performance Tuning
**SRE Responsibilities & IMS**  
- Reduced Heroku utilization by lowering enterprise footprint by 20% in Heroku apps and resources. This was done by managing timestamped updates when certain notifications were sent to potential owners of Heroku resources. Warnings and notifications were triggered by AWS EventBridge and monitored to track notifications sent to application teams (**state machine**). This allowed the product owner to confidently delegate the spin-down of unused resources.
- Reduced Contentful space utilization by lowering the enterprise footprint by 25%. Achieved this by tracking when spaces were last used. A script would run nightly, tagging spaces that had not been utilized in the last 180 days. Members of these Contentful sites were sent notifications to delete their unused spaces. This provided the product owner with confidence and necessary data to delegate the removal of unused spaces.
- Recognized need for increased memory in API worker, speeding up database queries considerably.
- Drove refactor of original Contentful IMS by replicating the architecture of the Heroku IMS. By utilizing event-driven architecture, the refactor allowed for resources to scale during resource collection and loading. This cut resource collection time in half upon completion. It also drastically improved code update speed and delivery.

**Maestro - Study Orchestration**  
- Improved workflow execution speed by optimizing Temporal plugin queries and utilizing batched data fetches.

### Business Analysis
**Maestro - Study Orchestration**  
- Conducted application design sessions with product owners to refine business rules for non-technical user configurability. This resulted in work on a new business rule management system using React Flow. This solution aims to empower non-technical users to configure site-specific rules within the application, making the system adaptable, user-centric, and scalable. This expansion has the potential to scale the project significantly, as it could lead to a larger team in future project phases. Through these efforts, I’ve actively contributed to enhancing both the application’s functionality and its potential for broader business impact.
- Documented and analyzed clinical trial workflows to ensure alignment with business and compliance needs.

**Data Marketplace**  
- Collaborated with UX teams to align evolving user interface designs with business objectives, ensuring rapid prototyping.  
- Delivered iterative updates to meet changing marketplace requirements.

**SRE Responsibilities & IMS**  
- Worked closely with product owners of multiple SaaS products to develop and architect multiple programs and applications ensuring user management, resource management, and authentication to products.

### Infrastructure as Code
**SRE Responsibilities & IMS**  
- Developed CloudFormation templates to automate ECS service deployments and resource provisioning.  
- Automated secret rotation and access management using AWS Secrets Manager within IaC templates.  

**Maestro - Study Orchestration**  
- Managed Kubernetes deployments through Helm charts, enabling version control and consistent application setup.  
- Designed infrastructure using OpenShift templates to simplify container management.  

**Add all deployment methods for all other apps**

### Test-Driven Development
**Maestro - Study Orchestration**  
- Developed unit tests for Temporal workflows using pytest to validate plugin behavior and ensure data integrity.  
- Implemented contract testing for GraphQL APIs to catch breaking schema changes early in the pipeline.

**Lilly Trial Guide**  
- Used Jest to ensure robust test coverage for the Next.js application, particularly for multilingual support.  

**Add all other apps describing JavaScript testing and python**

### GraphQL
**Maestro - Study Orchestration**  
- Designed GraphQL resolvers for querying DynamoDB audit logs, enhancing developer productivity with simplified data access.  
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Used PynamoDB Models and Strawberry GraphQL types to maintain a strict adherence to schema.

**SRE Responsibilities & IMS**  
- Designed robust database designs and GraphQL APIs that used Dataloader for cached querying to SQL databases.
- Created pagination mechanisms via GraphQL for paging through large DB queries.
- Simplified user access setup in the GraphQL API by creating a user context class that checks the user's token as well as indicators for whether the call came from an internal app.

**Lilly Trial Guide**  
- Used GraphQL for efficient data retrieval and integrated it with a responsive frontend.
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Implemented a mechanism that would pull the Contentful Schema and compare the updated schema to app typings, maintaining a 1-to-1 relationship with SaaS product updates and codebase.

---

### Serverless Technologies
**SRE Responsibilities & IMS**  
- Developed event-driven workflows using Lambda, SNS, and SQS to process and notify changes in SaaS inventory states. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work across the system.
- Leveraged AWS EventBridge to trigger Lambdas for near real-time processing of IMS updates.

**Maestro - Study Orchestration**  
- Built AWS Lambda-based processing for integrating Temporal workflows with external data sources.  
- Enhanced audit logging with DynamoDB streams for real-time monitoring.  

### Design Patterns
**Maestro - Study Orchestration**  
- Applied **Saga Pattern** for orchestrating distributed transactions across DynamoDB tables, ensuring data consistency during workflow execution and executed rollbacks when needed.  
- Built a **plugin-based architecture** to allow the addition of new integrations without disrupting existing workflows. Plugins are loaded into an EIC (External Interface Controller) that manages metadata on when Temporal schedules should run, where they should get their data, and where to send their data. This ETL system is the backbone of the entire application, allowing the system to scale to any number of clinical trial sites that want to be onboarded to the system.

**SRE Responsibilities & IMS**  
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work across the system.
- Used **State Machine Pattern** for managing the compliance of resources created on Heroku. This was done by managing timestamped updates when certain notifications were sent to potential owners of Heroku resources. Warnings and notifications were triggered by cron jobs and then monitored to track notifications sent to application teams. This allowed the product owner to confidently delegate the spin-down of unused resources.

### DevOps Tooling
**Maestro - Study Orchestration**  
- Used GitHub Actions to implement CI/CD pipelines for application deployments.  
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD, maintaining parity between environments with environment variables.

**SRE Responsibilities & IMS**  
- Migrated approx. 10 applications from CodePipeline to GitHub Actions. All applications had various deployment methods to multiple AWS services. After this update, all applications had a uniform deployment process that streamlined development.

**All Applications**  
- Built CI/CD pipelines with CodePipeline and GitHub Actions for frontend and backend deployments, ensuring quick turnaround for updates.
- Used automated testing, linting, and format checking in CI pipelines to maintain greater control over codebase updates.
- Managed schema updates with migration strategies. Used timestamped migration files for easy rollback of Postgres databases, triggered by a Lambda on system deployment.

---

### Core Cloud Concepts
**Maestro - Study Orchestration**    
- Managed ingress and egress for systems running on Kubernetes, creating service accounts and rules that allowed or disallowed services to talk with each other.
- Managed DNS, certificate creation, and load balancing for UI applications.
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.

**SRE Responsibilities & IMS**  
- Built serverless architectures using AWS Lambda, SNS, and SQS to streamline data flow and reduce latency. Utilized SQS retries for system error handling.
- Managed ingress and egress for Lambdas, EC2, Postgres, and DynamoDB in AWS.
- Utilized roles and security groups for granular access to resources created for applications.
- Designed DynamoDB table schemas to optimize for high-volume reads and writes with cost efficiency.  
- Managed DNS, certificate creation, and load balancing for multiple UI applications.
- Used Azure Enterprise Apps to create client credentials and manage user access to applications.
### Systems Analysis & Design
**Maestro - Study Orchestration**  
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Researched and designed a POC for a workflow management system that can be configured via React Flow diagrams. This allows users to granularly control their clinical trial site by adding workflow steps that result in system changes and activities/tasks being created automatically.
- Designed and implemented a scalable audit log system using AWS Kinesis Streams and DynamoDB to handle high-throughput updates.

**SRE Responsibilities & IMS**  
- Pushed refactor of one IMS application that was similar to another. Refactored the application over a very short timeframe and allowed for seamless updates to be integrated that were previously time-consuming due to poor architecture.

**eCTS**  
- Redesigned legacy systems into microservices for improved modularity and maintainability. Utilized Lambdas and shared code to share data between microservices.
- Built a serverless architecture API that was agnostic to the original system and schema so that data could be consumed across the enterprise. Used transformer classes to translate inconsistent data in a legacy database that was still required.

**Data Marketplace**  
- The project required agile, flexible UI development. I worked directly with product owners and UX to rapidly iterate on prototypes that aligned with evolving business goals.

---

## **Experience**
- **Work Experience**:
   - Over 6 years of multi-project client experience, notably with Eli Lilly.

### Maestro - Study Orchestration (2024-Present):
For the Maestro Study Orchestration project, I took on a lead role to ensure critical business requirements were met for an application that helps Clinical Trial Coordinators track and update patient activities within trials. I designed and implemented Temporal Workflows to fetch data from external databases, using a plug-in architecture for better scalability and flexibility. My work on DynamoDB involved complex data structures, managed through GraphQL and coordinated with the Saga Pattern for robust, multi-table updates. Additionally, I set up an audit log system with Kinesis Streams to track all entity updates, which strengthened our system’s traceability and monitoring capabilities.

Recently, I initiated work on a new business rule management system using React Flow. This solution, currently in the research phase with the product owner, aims to empower non-technical users to configure site-specific rules within the application, making the system adaptable, user-centric, and scalable. This expansion has the potential to scale the project significantly, as it could lead to a larger team in future project phases. Through these efforts, I’ve actively contributed to enhancing both the application’s functionality and its potential for broader business impact.

### LillyDev SRE Responsibilities & IMS (Inventory Management System) (2021-2024):
As a Senior Site Reliability Engineer, I oversaw various shared services within Lilly’s DevOps community, such as the LillyDev React site and migration tools on ECS. My role involved setting up infrastructure as code with CloudFormation, monitoring performance, and implementing scalable solutions.

One of the major projects I took part in as an SRE was the IMS project. In this project, I led the development of microservices and SPAs that provided visibility into SaaS products being used across the enterprise. This event-driven architecture used SNS, SQS, and Lambda functions to automate notifications and update statuses, improving data integrity. The project required rigorous database design and optimization skills, which I applied to manage lifecycle states and automate ownership processes. I collaborated closely with product owners and UX, deploying with GitHub Actions and using CloudFormation to maintain clean, scalable code.  In leading this effort, I was responsible for reducing the overall enterprise footprint by over 20% on Heroku and 25% on Contentful. By employing best practices and collaboration with the client, I built a framework that simplified operations and reduced resource usage.

### eCTS (Enterprise Clinical Trial System) (2020-2021):
As a senior engineer on the eCTS project, I contributed to modernizing a legacy clinical trial management system with TypeScript, AWS Lambdas, and API Gateway. This involved designing microservices and serverless architectures that minimized dependencies on older systems. My work extended to maintaining an agile development flow, ensuring we met strict business and compliance requirements. This experience deepened my understanding of event-driven architectures and cloud-native development while allowing me to directly support the scalability and performance goals of the organization.

### Data Marketplace (2020):
The Data Marketplace project required agile, flexible UI development. I worked directly with product owners and UX to rapidly iterate on prototypes that aligned with evolving business goals. I used AWS CloudFront, CodePipeline, and CloudFormation to deploy a responsive React frontend, establishing a CI/CD pipeline for smooth releases. This project helped me hone my skills in requirements analysis and design patterns, focusing on delivering a product that was adaptable and efficient.

### Lilly Trial Guide (2019-2020):
I helped in the development of a major overhaul of a public-facing application, moving it from React/Sails to a Next.js/Express stack. We worked closely with product owners and UX for agile iterations with strict adherence to company guidelines. I helped implement scalable solutions, including deploying to Heroku and integrating with Contentful and Elastic Search with Kabana, making the app easily configurable and efficient. I assisted in streamlining deployment with CI/CD, ensuring a reliable, maintainable product that met Lilly’s high standards for accessibility and multilingual support.



Mention:
Styled Components
No SQL
data processing systems
express 
end to end testing
documentation