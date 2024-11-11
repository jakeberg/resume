# Jacob Berg - Tech Lead Software Engineer Assessment 
A full-stack software engineer with 6+ years of experience in creating web applications with CICD, unit-testing, Agile methodology and development expertise.


***Certificates:***: AWS Certified Developer Certificate, AWS Solutions Architect Associate Certificate

## **Skills**

**Languages**: JavaScript/Typescript, Python

**Backend**: Temporal Workflows, GraphQL, Postgres, MongoDb, TypeORM, Knex, DynamoDB, Pydantic, Contentful

**Frontend**: React.js, Vue.js, Next.js, Nuxt.js, Redux, Vuex, Material UI, Bootstrap


**CI/CD**: CloudFormation, CodePipline, Github Actions

**Agile**: Jira, Confluence, Documentation, Lucid Chart

### **Eli Lilly - Design Center:** 

***Role**: Software Engineer*  
**About**: The Design Center works with many different business areas across Eli Lilly to provide development support with a focus on user centered design.

> **Lilly Trial Guide:** 

- Assisted with overhauling of a public facing React/Sails application to a Next.js/Express application.
- Written in Typescript, Material UI, Jest, ES-Lint and supported 3 languages for search and UI.
- Utilized Contentful, Elastic Search, GraphQL, Google Maps API, and Heroku.
- Maintained Contentful model migrations with CMS application, and used Contentful Webhooks to populate Elastic Search indices.

> **Data Marketplace:** 

- React.js application for the Lilly Data Marketplace, a frontend for the Enterprise Data Program.
- Used Typescript, Material UI, Jest, ES-Lint.
- Deployed to AWS CloudFront using CodePipeline, CodeBuild, CloudFormation.
- Created a Lambda to refresh user’s tokens from Azure AD.
- PO and UX required fast-paced prototypes while maintaining flexibility to implement when ready.
- Created JSON development server in order to complete tasks when API was still being developed.

> **eCTS:** 

- A legacy application that assists with the construction and management of Eli Lilly's clinical trails and warehouse distribution. 
- Created front-end application with Typescript, Material UI, Redux, Redux-Saga.
- Queried vendor REST services to extract information via AWS Lambda and API Gateway.
- Created AWS Lambda based rest endpoints to replace legacy Oracle system.

### **Eli Lilly - EDAT:** 

***Role**: Senior Site Reliability Engineer*  
***About**: EDAT serves as a Devops team for Eli Lilly. They create technologies that assist the overall development community across the company.*

> **SRE Responsibilities:**

- Maintained various shared packages and applications accross the enterprise.
  - LillyDev(React, Openshift, Contentful, ECS) - Main developer information resource website.
  - Contentful Migration Tool(React, Contentful, ECS) - Tool that assisted with migration of Contentful assets.
  - Heroku Services, Contentful Services, Slack Services(AWS Lambda, Eventbridge) - Various Lambdas that would modify and manage user onboarding and offboarding.
- Created shared packages that are utilized by product monitoring apps that simplified code updates and made services DRY(Microsoft Graph API Client, Service Now Client).

> **IMS(Inventory Management System):**

- A collection of webapps and microservices that collects and collates information about various products that the enterprise owns. (Heroku, Slack, Contentful, AWS Codepipeline)
- Event-based architecture that made use of SNS, SQS, Lambda, SES, to update resource statuses and send notifications to users.
- Used State Machine logic to create various lifecycle states for ownership over enterprise resources. 
- Various Nuxt.js SPAs that display information about userbase, cost, and EOL statuses of resources on each platform.
- Shared Component library that maintains a collections of common Vue.js components that are used for each of the IMS sites.
- Was able to reduce the enterprise footprint of Heroku apps by 20% and by locating abandonded apps and spinning them down automatically.
- Was able to reduce Contentful Space footprint 25% by locating spaces apps and spinning them down.
- Used Github actions to deploy Cloudformation template to AWS.
- Drove leadership buy-in to refactor entire legacy IMS for Contentful to match architecture of other IMS systems. This reduced complexity of system, reduced bugs, and reduced data collection time.

### **Eli Lilly - Study Orchestration (Maestro):** 

***Role**: Senior Software Engineer*  

- A webapp that assists CSCs(Clinical Trial Coordinators) keep track of and update patient activities within a clinical trial.
- Javascript, Next.js, Python, DynamoDb, GraphQL, Temporal Workflows, Kinesis, Openshift, Kubernetes
- Guided development in a senior role in order to meet very stict and complicated business requirements.
- Built Temporal Workflows to pull data from external Daabases using Plugin-In Architecture.
- Updates to DynamoDb via GraphQL made use of Saga Pattern for wholistic rollbacks on failure to update multiple DB tables.
- Drove creation of audit log system using Kinesis Streams to monitor entity update events.
- Used Github actions to deploy Cloudformation template to AWS.
- Developed client relationship with Lilly Tech Lead/Architect and assisted with architecture research.
- Created docker-compose files for all microservices and Makefile to start up entire app in one command, reducing local development complexity.
- Used Pandas data library to assist with ETL transactions in the External Interface Controller microservice.
- Used Factory Pattern in multiple services to simplify and standardize service classes.


