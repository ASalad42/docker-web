# docker-web

- sudo apt install npm
- sudo npm install -g n
- sudo n lts
  


Create a Docker Image using dockerfile 

- npx nx build exhibition-leaderboard
- docker build -t leaderboard .
- 

Push Docker Image to a Container Registry:
- Build the Docker image: docker build -t your-image-name .
- Authenticate Docker to your ECR: aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com
- Tag the image: docker tag your-image-name:latest your-account-id.dkr.ecr.your-region.amazonaws.com/your-repo-name:latest
- Push the image to ECR: docker push your-account-id.dkr.ecr.your-region.amazonaws.com/your-repo-name:latest

Set Up AWS Lightsail Container Service:
- Create a new Lightsail container service.
- Choose the container image pushed to ECR or provide the public image URL.
- Configure the container service with the desired instance specifications, network settings, and scaling options.
- port 3000

![image](https://github.com/ASalad42/docker-web/assets/104793540/c7258645-1745-4b84-bbfc-0da224886829)
![image](https://github.com/ASalad42/docker-web/assets/104793540/ba9205f9-e438-4a43-9623-2b8c388bbb6f)


