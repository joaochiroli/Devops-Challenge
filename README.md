# Full-Stack-Challenge

SRE Kubernetes Coding Challenge

Technologies 
- Kubernetes
- DigitalOcean/AWS/GCP/Azure
- Gitlab/Github/CircleCI/CodeCommit 
- JMeter
- Docker
- Prometheus
- Linux
- NGINX

Setup
You can clone the challenge repository to your local machine with the following command:
{GITHUB-TOKEN}: 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 
git clone https://{GITHUB-TOKEN}@github.com/fullstacklabs/assessment-cc-sre-kubernetes-sr-01 --branch v1.0.0
​
## SRE Challenge: Part 1
Continuous integration

Set up a new repository and CI pipeline using any code version provider
The CI steps should be created and triggered for any pull request. The pipeline should run the following steps:
- Install dependencies npm install
- Linter (ESLint) npm run lint
- Formatter (Prettier) npm run prettier
- Test (Jest) CI=true npm run test
- Build npm run build

The pipeline should be successful. 
Please provide some pull requests to show pass or fail status in the CI pipeline.


## SRE Challenge: Part 2
Continuous Deployment and Load Testing 
Deploy the provided application to your chosen cloud provider using any service that runs the application as a Docker container. Then, create a test plan for the application's home page and generate a testing report using JMeter.
The application needs to:
Available for anyone with Internet access only during the challenge recording

## SRE Challenge: Part 3
Monitoring system  
Deploy a Prometheus monitoring system on an Ubuntu cloud instance. The system should be secured and accessible through a reverse proxy, with proper authentication in place, and connected to an external Node Exporter. You can follow these steps: 
Access the Server: Access your cloud instance via SSH using either the provided server password or an SSH key (if configured).
Install Prometheus and Node Exporter:
Update your package list and install Prometheus with the following commands:
sudo apt update sudo apt install prometheus
​
Verify the installation by checking the status of Prometheus services:
sudo service prometheus status sudo service prometheus-node-exporter status
​
Completion Criteria 
Use NGINX as a reverse proxy to forward requests from your server's IP address to Prometheus' default ports as follows: 
http://{YOUR-SERVER-IP}/ to Prometheus (<http://localhost:9090/>) http://{YOUR-SERVER-IP}/metrics/ to the Node Exporter (<http://localhost:9100/>)
​
Basic authentication is set up, requiring credentials to access both endpoints.
Direct access to ports 9090 (Prometheus) and 9100 (Node Exporter) is blocked, and access is only allowed via NGINX.
Prometheus is scraping metrics from an external Node Exporter running on a second server.
