# Blue Sun Financial - CI/CD Pipeline Project

## Overview

The purpose is to demo a minimal implementation of a CI/CD pipeline for Blue Sun Financial (a fake retail bank) including deploying it to the cloud. The project shows the integration of tools and services such as: Jenkins, EC2, and Elastic Beanstalk.

## Steps Taken

1. **Launched EC2 Instance**:

   - Launched an EC2 instance to host Jenkins.
   - Created a directory to clone repo in.

2. **Jenkins**:

   - Connected to the EC2 terminal.
   - Installed and started Jenkins on system:

   ```sudo apt update && sudo apt install fontconfig openjdk-17-jre software-properties-common && sudo add-apt-repository ppa:deadsnakes/ppa && sudo apt install python3.7 python3.7-venv
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
   echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" https://pkg.jenkins.io/debian-stable binary/ | sudo tee /etc/apt/sources.list.d/jenkins.list > /dev/null
   sudo apt-get update
   sudo apt-get install jenkins
   sudo systemctl start jenkins
   sudo systemctl status jenkins
   ```

   - Accessed Jenkins through the EC2's public IP address on port 8080.
   - Completed initial setup steps including plugin installation and admin user creation.

3. **Multi-Branch Pipeline Creation**:

   - Set up a new Multi-Branch pipeline in Jenkins.
   - Connected the pipeline to the GitHub repository giving the repo URL and using personal access token for authentication.

4. **Build Process**:
   - Triggered the first build, which completed successfully.
   - Analyzed the build stages:
     - Stage 1: Starts the process.
     - Stage 2: This tells Jenkins to get the code from the GitHub repo I defined (my forked repo)
     - Stage 3: Sets up a Python virtual environment (venv) and installs all the necessary packages and dependencies of the project’s repo.
     - Stage 4: Activates the virtual environment the Build stage set up for us. Runs any test files specified, and documents the results in an file called `results.xml`
