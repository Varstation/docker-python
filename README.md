# Python Slim with aws-cli

Created By Beta. beta@varsomics.com

## TODO:
Create doc for tagging


# How to build and push
Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:
```bash
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/s4y1t8n6
```

Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.
Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built:
```bash
docker build -t python:3.9.1-slim .
````
After the build completes, tag your image so you can push the image to this repository:
```bash
docker tag python:latest public.ecr.aws/s4y1t8n6/python:3.9.1-slim
```

Run the following command to push this image to your newly created AWS repository:
```bash
docker push public.ecr.aws/s4y1t8n6/python:3.9.1-slim
````

