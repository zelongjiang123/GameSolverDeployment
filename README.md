# **GameSolverBackend**

GameSolverBackend is a backend service deployed on **AWS Elastic Beanstalk** that provides APIs to calculate game outcomes based on a given reward matrix and other parameters.

## **Deployment and Configuration**
- The backend code is packaged as a **zip file** and deployed to **Elastic Beanstalk**.
- `.ebextensions/https-instance-single.config`: allow inbound https traffics
- `.ebextensions/https-instance-example.config`: create ssl certificate file (`server.crt`) and key file (`server.key`) on **nginx**. Replace the placeholders with your ssl certificate and keys. You can find free ssl on [ZeroSSL](http://www.zerossl.com/)
- `.platform/nginx/conf.d/https.conf`: create https server
- `.platform/nginx/conf.d/elasticbeanstalk/00_application.conf`: redirect https request to the backend running on http
- `.platform/nginx/conf.d/myconf.conf`:
    - Adjust request timeouts.
    - Disable response buffering to ensure real-time messages are sent to the frontend.

## **Features**
- Provides APIs for game outcome calculation.
- Supports real-time event streaming to the frontend.
- Optimized for performance with custom Nginx configurations.