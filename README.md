# docker-web

- sudo apt install npm
- sudo npm install -g n
- sudo n lts


- docker exec -it ae4e933d5dc0 /bin/bash
- env
- this shows the env variables of the container
- docker run -d -p 3000:3000 leaderboard
- docker build -t name . 


Create a Docker Image using dockerfile 

- cd ~/smg-web/dist/apps/exhibition-leaderboard/standalone
- npx nx build exhibition-leaderboard
- sudo pnpm run build-leaderboard
- docker build -t leaderboard .
- Only the standalone folder is needed in the docker image.
- cd into that "standalone" folder and run "node apps/exhibition-leaderboard/server.js"

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


