# Slick Requirements

## Certifications
- AWS Certified Developer, AWS Solutions Architect Associate  
  - No additional details needed here; certifications speak for themselves.

---

## Basic Understanding

### 12-Factor Application
**Maestro - Study Orchestration**  
- Designed **stateless Temporal Workflows** to orchestrate clinical trial data activities, ensuring easy scalability and reliability.  
- Managed **environment variable configurations** for deployment consistency across Kubernetes clusters.  
- Automated release processes using **GitHub Actions** and Kubernetes rollout strategies.

**LillyDev SRE Responsibilities & IMS**  
- Adhered to **externalized configurations** and environment variable management using Heroku for event-driven microservices.  
- Utilized **stateless services** for Lambda functions interacting with SNS and SQS queues.  

**Data Marketplace**  
- Deployed a responsive React frontend with configurations managed through environment variables for seamless development and production transitions.  
- Automated deployments and releases with AWS CodePipeline, adhering to 12-factor principles.  

---

### Deployment, Scaling, and Management of Containerized Applications
**Maestro - Study Orchestration**  
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling for changing trial requirements.  
- Monitored and auto-scaled Kubernetes pods based on workflow execution metrics, improving resource utilization.  

**LillyDev SRE Responsibilities & IMS**  
- Migrated enterprise React applications to ECS with automated pipelines for CI/CD using GitHub Actions.  
- Scaled ECS services for high availability during SASS inventory updates, reducing downtime by 30%.  

**Lilly Trial Guide**  
- Migrated the application stack to Next.js and containerized it for deployment to Heroku, streamlining performance and scaling processes.  

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
- Conducted joint application design (JAD) sessions with product owners to refine business rules for non-technical user configurability.  
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
**LillyDev SRE Responsibilities & IMS**  
- Developed event-driven workflows using Lambda, SNS, and SQS to process and notify changes in SASS inventory states.  
- Leveraged DynamoDB streams and Lambda triggers for near real-time processing of IMS updates.  

**Maestro - Study Orchestration**  
- Built AWS Lambda-based processing for integrating Temporal workflows with external data sources.  
- Enhanced audit logging with DynamoDB streams for real-time monitoring.  

### Design Patterns
**Maestro - Study Orchestration**  
- Applied **Saga Pattern** for orchestrating distributed transactions across DynamoDB tables, ensuring data consistency during workflow execution.  
- Built a plugin-based architecture to allow the addition of new integrations without disrupting existing workflows.

**LillyDev SRE Responsibilities & IMS**  
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness.

**eCTS**  
- Used **State Machine Pattern** for designing microservices that adhered to clinical trial workflows.  

### DevOps Tooling
**Maestro - Study Orchestration**  
- Used GitHub Actions to implement CI/CD pipelines for both containerized workflows and application deployments.  
- Implemented monitoring and alerting with Prometheus and Grafana for Temporal workflow services.  

**Data Marketplace**  
- Built CI/CD pipelines with CodePipeline for frontend and backend deployments, ensuring quick turnaround for updates.  

---

## Expert Understanding

### Core Cloud Concepts
**Maestro - Study Orchestration**  
- Designed and implemented a scalable audit log system using **AWS Kinesis Streams** and DynamoDB to handle high-throughput updates.  
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.

**LillyDev SRE Responsibilities & IMS**  
- Built serverless architectures using AWS Lambda, Kinesis, and SQS to streamline data flow and reduce latency.  
- Designed DynamoDB table schemas to optimize for high-volume reads and writes with cost efficiency.  

### Systems Analysis & Design
**Maestro - Study Orchestration**  
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Defined architectural blueprints for plugin-based Temporal workflows, enabling scalable and reusable components.

**eCTS**  
- Redesigned legacy systems into microservices for improved modularity and maintainability.  
- Documented and analyzed clinical trial workflows to ensure alignment with business and compliance needs.  

---
