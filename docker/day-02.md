🐳 Day 02 - Docker (Images & Containers)
✅ What I Did
Worked with Docker images and containers
Learned how container lifecycle works
Practiced starting, stopping, and removing containers
Understood how Docker manages system resources
⚙️ Commands Used
docker images
docker ps
docker ps -a

docker run -d nginx
docker run -d mysql

docker stop <container_id>
docker start <container_id>

docker rm <container_id>
docker rmi <image_id>

docker system prune
🧠 What I Learned
Images are templates used to create containers
Containers are runtime instances of images
docker ps shows only running containers
docker ps -a shows all containers (running + stopped)
Containers can be started, stopped, and removed anytime
Cleaning unused containers/images helps manage system resources
🚧 Problems Faced
Confused between stopping and removing containers
Some containers stayed in exited state and caused confusion
Unable to remove image because container was still using it
✅ Solution
Used docker ps -a to identify all containers
Stopped running containers using docker stop <container_id>
Removed containers using docker rm <container_id>
Then successfully removed images using docker rmi <image_id>
📌 Next
Learn about ports and container networking 🌐
