# Jacob Victor Berg
`Senior Software Engineer / Site Reliability Engineer`

## Certifications
- AWS Certified Developer, AWS Solutions Architect Associate  

## **Experience**

### Maestro - Study Orchestration (2024-Present):
Assisted in lead development data processing system by utilizing Temporal Workflows, plug-in architecture, GraphQL, DynamoDB/NoSQL, and the Saga Pattern. Built out a React Flow-based rule management system to enable site-specific configurations for non-technical users, enhancing scalability and adaptability.

- Assisted in design of Temporal Workflows to orchestrate clinical trial data, ensuring easy scalability and reliability via a **distributed and microservice** architecture. Temporal Workflows were utilized for automatic updates to system data via triggers and schedules, managed by a **plugin architecture** system.
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD and Gitub Actions, maintaining parody between environments with environement variables. System settings were stored in a repository, which is monitored by Argo CD for dynamic updates to environments.
- Utilized backing services such as S3 to manage plugins for Plugin Architecture in system. Also used S3 to store all actions between Temporal Workflows for transfering large amounts of data between Temporal activities -- this also had the benifit of storing all activity data for auditing purposes.
- Maintained **disposability and robusteness**  of temporal worker by designing a remediation mechanism into system startup. On startup, application would pull all existing plugins from S3 to create/delete any workflow schedule that may have been out of sync if system was offline.
- Created dynamic workflows for trial coordinators to adapt patient activities based on clinical protocol requirements using React Flow, Next.js, JDM models with Zen Engine.
- Used Docker with docker-compose for local development of multiple micro services running simultaneously with a Makefile. Implemented localstack to spin up AWS services locally(DynamoDB, S3) through docker-compose.
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling.  
- Utilized KCL(Kinesis Client Library) with Kinesis Streams to process streaming data reliably at scale and manage sharding of database.
- Improved workflow execution speed by optimizing Temporal plugin queries and utilizing batched data fetches.
- Conducted application design sessions with product owners to refine business rules for non-technical user configurability. This resulted in work on a new business rule management system using React Flow. This solution aims to empower non-technical users to configure site-specific rules within the application, making the system adaptable, user-centric and scalable. This expansion has the potential to scale the project significantly, as it could lead to a larger team in future project phases. Through these efforts, I’ve actively contributed to enhancing both the application’s functionality and its potential for broader business impact. 
- Documented and analyzed clinical trial workflows to ensure alignment with business and compliance needs.
- Managed Kubernetes deployments through Helm charts, enabling version control and consistent application setup.  
- Designed infrastructure using OpenShift templates to simplify container management. 
- Designed GraphQL resolvers for querying DynamoDB audit logs, enhancing developer productivity with simplified data access.  
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Used PynamoDB Models and Strawberry GraphQL types to maintain a strict adherance to schama.
- Built AWS Lambda-based processing for integrating Temporal workflows with external data sources.  
- Enhanced audit logging with DynamoDB streams for real-time monitoring.  
- Used GitHub Actions to implement CI/CD pipelines application deployments.  
- Automated release processes using GitHub Actions and Kubernetes rollout strategies via Argo CD, maintaing parody between environments with environement variables.
- Managed ingress and egress for systems running on Kuberneties, creating service accounts and rules that allowed or dissallowed services to talk with each other.
- Manage DNS, certificate creation, and load balancing for UI application.
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Reaserched and designed POC for workflow management system that can be configured via React Flow diagrams. This allows users to granularly control their clinical trial site by adding workflow steps that result in system changes and activities/tasks being created automatically. 
- Designed and implemented a scalable audit log system using AWS Kinesis Streams and DynamoDB to handle high-throughput updates.


### LillyDev SRE Responsibilities & IMS (2021-2024):
Managed shared DevOps services and infrastructure-as-code using CloudFormation, scaling enterprise tools on ECS. Led the IMS project to optimize SaaS resource usage by 20%+ via event-driven microservices with SNS, SQS, and Lambda, improving automation and reducing enterprise footprint.


- Adhered to **externalized configurations** and environment variable management using AWS for event-driven microservices.  
- Utilized **stateless services** for Lambda functions interacting with SNS and SQS queues.
- Maintained **disposability and robusteness** with a remediation Lambda that would scan for ownership status if Ownership System was offline during resource collection.
- Created **admin specific** page within app to update critical data. Admin page would check JWT for correct Azure group before allowing access to page. Admin could update important system data for Heroku Stack lifecycle updates. Admin could also stage outdated and unclaimed Heroku applications for spindown.
- Used Docker with docker-compose for local development of backend event-driven services. Implemented localstack to spin up AWS services locally(SNS, SQS) through docker-compose.
- Used NPM workspaces to structure monorepo of multiple services and modules. This included Lambda Layers that were dynamically structured for deployment.
- Migrated enterprise Vue and React applications to ECS with automated pipelines for CI/CD using GitHub Actions.
- Gained expert understanding  of CI/CD practices GitHub Actions, Cloudformation, AWS CLI, Docker, Artifactory.
- Used SNS, SQS and Lambdas for resource collection, which allowed for scaling of compute processes during resource scanning and DB updates. 
- Used Lambda API and Dataloader for cached querying to SQL database.
- Deployed and managed containerized applications that managed multiple SASS products that client was using.
- Utilized health checks and rolling updates to ensure system stability.
- Reduced Heroku utilization by lowering enterprise footprint by 20% in Heroku apps and resources. This was done by managing timestamped updates when certain notifactions were sent out to potential owners of Heroku resources. Warnings and notifications were triggered by AWS Eventbridge and then monitored to track which notifications were sent to certain application teams(**state machine**). This allowed the pruduct owner to confidently delegate the spin down unused resources.
- Reduced Contentful space utilization by lowering enterprise footprint 25%. This was achieved by tracking when spaces were last used. A script would run nightly and tag the spaces that had not been utilized in the last 180 days. Memebers of these Contentful sites were sent notifications automatically to delete their spaces if they were not being used. This data also gave the product owner confidence and neccessary data to delegate the removal of spaces that were not being used.
- Recognized need for increased memory in API worker, speeding up queries to DB considerably.
- Drove refactor of original Contentful IMS by parodying the exiting architecture for the Heroku IMS. By utilizing event-driven architecture, the refactor allowed for resources to scale during resoure collection and loading. This cut resource collection in half after it was complete. It also drastically improved code update speed and delivery.
- Worked closely with product owner of multiple SASS products to develop and architect multiple programs and applications ensuring user management, resource management, authentication to products.
- Developed CloudFormation templates to automate ECS service deployments and resource provisioning.  
- Automated secret rotation and access management using AWS Secrets Manager within IaC templates.  
- Used Jest to ensure end to end test coverage for the Next.js application, particularly for multilingual support.  
- Designed robust database design and GraphQL API that used Dataloader for cached querying to SQL database.
- Created pagination mechanism via GraphQL for paging through large DB queries.
- Simplified user access setup in Graphql API by creating user context class that checks the users token as well as the indicators as to whether the call came from an internal app.
- Developed event-driven workflows using Lambda, SNS, and SQS to process and notify changes in SASS inventory states. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work accross the system.
- Leveraged AWS Eventbridge and to trigger Lambdas for near processing of IMS updates.
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness. Used SQS and SNS to trigger different Lambdas to update system data. Created "resource scanners" and "resource loaders" to distribute work accross the system.
- Used **State Machine Pattern** for managing the compliance of resources that were created on Heroku. This was done by managing timestamped updates when certain notifactions were sent out to potential owners of Heroku resources. Warnings and notifications were triggered by cron jobs and then monitored to track which notifications were sent to certain application teams. This allowed the pruduct owner to confidently delegate the spin down unused resources.
- Migrated approx 10 applications from Code Pipeline to Github Actions. All applications had various deployment methods to multiple AWS services. After this update, all applications had a uniform deployment process that streamlined development.
- Built serverless architectures using AWS Lambda, SNS, and SQS to streamline data flow and reduce latency. Utilized SQS retries for system error handling.
- Managed ingress and egress for Lambdas, EC2, Postgres, DynamoDB in AWS
- Utilized roles and security groups for granular access to resources created for applications.
- Designed DynamoDB table schemas to optimize for high-volume reads and writes with cost efficiency.  
- Manage DNS, certificate creation, and load balancing for multiple UI applications.
- Used Azure Enterprise Apps to create client credentials and manage user access to applications.
- Created POC app for deploying apps to Azure via Github Actions.
- Pushed refactor of one IMS application that was similar to another. Refactored application over very short timeframe and allowed for seemless updates to be integrated that were once very time consuming due to bad architecture.

### eCTS (Enterprise Clinical Trial System) (2020-2021):
Modernized a legacy clinical trial system with AWS Lambdas, API Gateway, and serverless architectures, aligning with strict business and compliance goals to enhance scalability and performance.

- Redesigned legacy systems into microservices for improved modularity and maintainability. Utilized Lambdas and shared code to share data between microservices.
- Built serverless architecure API that was agnostic to the original system and schema so that data could be constumed accross enterprise. Used transformer classes to translate inconsistant data in legacy database that was still required.

### Data Marketplace (2019-2020):
Developed a responsive React frontend with CI/CD pipelines using AWS CloudFront and CodePipeline, enabling rapid prototype iterations and deployment for evolving business goals.

- Collaborated with UX teams to align evolving user interface designs with business objectives, ensuring rapid prototyping.  
- Delivered iterative updates to meet changing marketplace requirements.
- Project required agile, flexible UI development, and I worked directly with product owners and UX to rapidly iterate on prototypes that aligned with evolving business goals.

### Lilly Trial Guide (2018-2019):
Migrated a public-facing application to a Next.js/Express stack, integrating with Contentful and ElasticSearch to improve scalability and accessibility, while ensuring compliance with company standards.


- Heroku application deployment with environments including a pre production environment for blue green deployment.
- Used Contenful resources to dynamically build React components based off of resource type.
- Maintained CMS model management system to synchronize Contenful environment.
- Created script to run and update Typescript types pulled from Contenful
- Used Jest to ensure robust test coverage for the Next.js application, particularly for multilingual support. 
- Used GraphQL for efficient data retrieval and integrated it with a responsive frontend.
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls.
- Implemented mechanism that would pull Contentful Schema and compare updated schema to our app typings, maintaining a 1 to 1 relationship with Sass product updates and codebase.
- Customized Material UI for component library with Styled Components.
