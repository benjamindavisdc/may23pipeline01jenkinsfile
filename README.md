# Jenkins Pipeline for Cloud Engineer Web Deployment Portfolio
This is the Pipeline control file to upload my Web App to my Apache server to host my Cloud Portfolio!

This Jenkinsfile contains the pipeline configuration used to deploy a web portfolio to an AWS Apache server. It clones a Git repository, cleans the web directory, copies the files to the server, and performs clean-up tasks.

# Prerequisites
Jenkins installed and configured
Docker installed
Access to an AWS Apache server

# Pipeline Steps
The pipeline consists of the following stages:

Clone Git Repository: This stage clones the Git repository containing the web portfolio files.

Clean Web Directory: This stage cleans the Apache web directory by removing all files from it. It utilizes a Docker container named my-apache-container to execute the command.

Copy Files: This stage copies the new files from the cloned repository to the Apache web directory. It utilizes a Docker container to copy the files.

Clean Up: This final stage performs clean-up tasks by removing the temporary repository directory.
