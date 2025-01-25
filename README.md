# Full-Stack-Challenge

SRE Kubernetes Coding Challenge

FSL Version: V1.0.0
Introduction
Welcome to our coding challenge! This challenge has been designed to test your coding skills and problem-solving abilities. This challenge is a great way to push yourself and learn new things. The challenge will test your technology stack skills and your ability to solve problems. Good luck, and have fun!
Guidelines
You will create a screen recording video of yourself completing the challenge, then send us a link to the file via Google Drive. A few things to consider:
The recording must capture the entire coding challenge and should not exceed 60 minutes. While there is some flexibility to go beyond this limit, any additional time over 60 minutes will result in penalties and may affect your application.
You can use screen recording software like Loom, QuickTime, or something similar, to create the video.
As you complete the challenge, please explain what you are doing. Walk us through your thinking, explain your decisions, etc.
You cannot use tools such as Copilot, Tabnine, Captain Stack, GPT-Code-Clippy, chatGPT, or similar to simplify or generate code to support the challenge. Doing this will be grounds for automatic disqualification.
You cannot search for information from websites like Stackoverflow, blogs, forums, or similar; however, you can use the official documentation website of the technology.
You MUST NOT edit your video, stop it and continue later, copy contents from hidden screens, or do anything that could be considered cheating.
The recording must be done in one take without pauses or editing. You MUST NOT stop or interrupt the recording at any point; if you do, you will be disqualified.
You should start the recording after completing the project's environment setup.
You should record your entire screen so we can validate your implementation correctly. Also, your computer clock should be visible in the entire video.
Here is a short clip from a recent coding challenge as an example of what your recording should look like Example video. It is from a React challenge, but it is the same for any challenge.
Please upload the video file to Google Drive and share an open link with us (we support .mp4, files smaller/with less than 4 GB).
Technologies 
Kubernetes
DigitalOcean/AWS/GCP/Azure
Gitlab/Github/CircleCI/CodeCommit 
JMeter
Docker
Prometheus
Linux
NGINX
Setup
You can clone the challenge repository to your local machine with the following command:
{GITHUB-TOKEN}: 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 
git clone https://{GITHUB-TOKEN}@github.com/fullstacklabs/assessment-cc-sre-kubernetes-sr-01 --branch v1.0.0
​
## SRE Challenge: Part 1
Continuous integration
Set up a new repository and CI pipeline using any code version provider
The CI steps should be created and triggered for any pull request. The pipeline should run the following steps:
Install dependencies npm install
Linter (ESLint) npm run lint
Formatter (Prettier) npm run prettier
Test (Jest) CI=true npm run test
Build npm run build
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
