# CI/CD Pipelines

The folders contain the following:

* [jenkins-pipeline](/jenkins-pipeline): Simple Jenkins pipeline with four stages: 1) test bash script; 2) check HTML file (tidy); 3) Scan docker image for security issues (Aqua microscanner); 4) Upload HTML file to S3 bucket. The S3 bucket used **must exist** before launching the pipeline.
  
* [nginx-ansible](/nginx-ansible): Ansible role for installing the nginx server with a simple configuration for Debian OS. Before deploying update the variables `SERVER_NAME` and `STUDENT_NAME` in `roles/nginx/vars/main.yaml`.