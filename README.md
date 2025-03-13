# **GameSolverBackend**

GameSolverBackend is a backend service deployed on **AWS Elastic Beanstalk** that provides APIs to calculate game outcomes based on a given reward matrix and other parameters.

## **Deployment and Configuration**
- The backend code is packaged as a **zip file** and deployed to **Elastic Beanstalk**.
- The configuration files in `.ebextensions` and `.platform/nginx/conf.d` are used to:
  - Adjust request timeouts.
  - Enable and enforce **HTTPS**.
  - Disable response buffering to ensure real-time messages are sent to the frontend.

## **Features**
- Provides APIs for game outcome calculation.
- Supports real-time event streaming to the frontend.
- Optimized for performance with custom Nginx configurations.