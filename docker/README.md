Commands:

1. `docker init`
2. `docker build -t <imagename>:<tag> <directory of Dockerfile>`
3. Ports: `docker run -p <e.g. 127.0.0.1:8080:8080> <imagename>:<tag>`
4. Volumes: `docker run -v <host location>:<docker location> <imagename>:<tag>`
5. Named Volumes:
    - `docker volume create <name of your volume>`
    - `docker run -v <volume name>:<docker location>`
6. Docker Compose:
    - Create compose.yaml.
    - `docker compose up --build`
7. Deploy to AWS:
    - Popular: ECS or EKS
    - Upload image to ECR: `aws ecr get-login-password --region <region e.g. us-east-1> | docker login --username AWS --password-stdin <account ID e.g. 755314965794>.dkr.ecr.<region>.amazonaws.com`
    - Prepare image for upload into ECR: `docker tag <image>:<tag> <account id>.dkr.ecr.<region>.amazonaws.com/<image>:<tag>`
    - Push: `docker push <accountid>.dkr.ecr.<region>.amazonaws.com/<image>:<tag>`<== Remember to create repository first in ECR UI.
    - Create ECS Cluster via UI - instantiate with EC2 or Fargate (serverless).
    - Create task definition - link to ECR image URI, port mappings etc.
    - Deploy to Fargate service.
    - May need to add security group settings to be able to view.
