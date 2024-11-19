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

### Deployment, Scaling, and Management of Containerized Applications
**Maestro - Study Orchestration**  
- Deployed containerized applications and Temporal workflows using OpenShift, ensuring rapid scaling for changing trial requirements.  
- Monitored and auto-scaled Kubernetes pods based on workflow execution metrics, improving resource utilization.  

**LillyDev SRE Responsibilities & IMS**  
- Migrated enterprise React applications to ECS with automated pipelines for CI/CD using GitHub Actions.  
- Scaled ECS services for high availability during SASS inventory updates, reducing downtime by 30%.  

---

## Strong Understanding

### Performance Tuning
**LillyDev SRE Responsibilities & IMS**  
- Optimized DynamoDB queries by redesigning table structures and indexing strategies, reducing read costs by 20%.  
- Reduced Heroku app utilization by consolidating redundant services and migrating legacy dependencies.  

### Business Analysis
**Maestro - Study Orchestration**  
- Conducted joint application design (JAD) sessions with product owners to refine business rules for non-technical user configurability.  
- Created dynamic workflows for trial coordinators to adapt patient activities based on clinical protocol requirements.  

### Infrastructure as Code
**LillyDev SRE Responsibilities & IMS**  
- Wrote CloudFormation templates to automate ECS service deployments and resource provisioning.  
- Automated secret rotation and access management using AWS Secrets Manager within IaC templates.  

### Test-Driven Development
**Maestro - Study Orchestration**  
- Developed unit tests for Temporal workflows using **pytest** to validate plugin behavior and ensure data integrity.  
- Implemented contract testing for GraphQL APIs to catch breaking schema changes early in the pipeline.  

### GraphQL
**Maestro - Study Orchestration**  
- Designed GraphQL resolvers for querying DynamoDB audit logs, enhancing developer productivity with simplified data access.  
- Integrated Apollo Client to optimize queries and cache trial data, reducing redundant API calls by 40%.  

---

## Advanced Understanding

### Serverless Technologies
**LillyDev SRE Responsibilities & IMS**  
- Developed event-driven workflows using Lambda, SNS, and SQS to process and notify changes in SASS inventory states.  
- Leveraged DynamoDB streams and Lambda triggers for near real-time processing of IMS updates.  

### Design Patterns
**Maestro - Study Orchestration**  
- Applied **Saga Pattern** for orchestrating distributed transactions across DynamoDB tables, ensuring data consistency during workflow execution.  
- Built a plugin-based architecture to allow the addition of new integrations without disrupting existing workflows.

**LillyDev SRE Responsibilities & IMS**  
- Utilized **event-driven architecture** for state changes in IMS, improving maintainability and system responsiveness.

### DevOps Tooling
**Maestro - Study Orchestration**  
- Used GitHub Actions to implement CI/CD pipelines for both containerized workflows and application deployments.  
- Implemented monitoring and alerting with Prometheus and Grafana for Temporal workflow services.  

---

## Expert Understanding

### Core Cloud Concepts
**Maestro - Study Orchestration**  
- Designed and implemented a scalable audit log system using **AWS Kinesis Streams** and DynamoDB to handle high-throughput updates.  
- Used **DynamoDB Global Secondary Indexes (GSI)** to sort and query entity updates by their last modified timestamps efficiently.

### Systems Analysis & Design
**Maestro - Study Orchestration**  
- Conducted impact analysis for integrating React Flow-based business rules management, ensuring alignment with non-technical user workflows.  
- Defined architectural blueprints for plugin-based Temporal workflows, enabling scalable and reusable components.

---
