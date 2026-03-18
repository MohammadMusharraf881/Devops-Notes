📌 1. Check Docker Installation
docker --version

👉 Purpose: Verify Docker is installed and working

📌 2. Pull an Image from Docker Hub
docker pull nginx

👉 Purpose: Download an image from Docker Hub to your local system

📌 3. View Downloaded Images
docker images

👉 Purpose: List all images available locally

📌 4. Run a Container
docker run -d -p 80:80 nginx

👉 Purpose: Create and start a container

-d → Run in background

-p → Map ports (host:container)

📌 5. Run Container with Name
docker run -d -p 80:80 --name my-nginx nginx

👉 Purpose: Assign a custom name to container

📌 6. List Running Containers
docker ps

👉 Purpose: Show currently running containers

📌 7. List All Containers (Including Stopped)
docker ps -a

👉 Purpose: Show all containers (running + stopped)

📌 8. Stop a Container
docker stop my-nginx

👉 Purpose: Stop a running container

📌 9. Start a Container
docker start my-nginx

👉 Purpose: Restart a stopped container

📌 10. Remove a Container
docker rm my-nginx

👉 Purpose: Delete a container

📌 11. Remove an Image
docker rmi nginx

👉 Purpose: Delete an image from local system

📌 12. Execute Command Inside Container
docker exec -it my-nginx bash

👉 Purpose: Access container terminal (interactive mode)

📌 13. View Container Logs
docker logs my-nginx

👉 Purpose: Check logs/output of a container

📌 14. Build Docker Image
docker build -t my-app .

👉 Purpose: Create an image from Dockerfile

📌 15. List Docker Networks
docker network ls

👉 Purpose: Show all Docker networks

📌 16. Create a Network
docker network create my-network

👉 Purpose: Create a custom network for containers

📌 17. Run Container in Network
docker run -d --network my-network nginx

👉 Purpose: Connect container to a specific network

📌 18. Inspect Container
docker inspect my-nginx

👉 Purpose: Get detailed information (IP, config, etc.)

📌 19. Copy Files Between Host & Container
docker cp file.txt my-nginx:/usr/share/nginx/html/

👉 Purpose: Transfer files into container

📌 20. Check Resource Usage
docker stats

👉 Purpose: Monitor CPU, memory usage of containers

🎯 Summary (Interview Ready)

Images → Blueprint

Containers → Running instance

Docker Run → Create + Start

Docker Exec → Access container

Docker Build → Create custom image

Port Mapping → Connect container to real world




📌 1. Access Container Terminal
docker exec -it my-container bash

👉 Purpose: Open an interactive terminal inside a running container

-i → interactive

-t → terminal

💡 Use sh if bash is not available:

docker exec -it my-container sh
📌 2. Run Command Inside Container
docker exec my-container ls

👉 Purpose: Execute a single command inside container without opening terminal

📌 3. Attach to Running Container
docker attach my-container

👉 Purpose: Attach your terminal to container’s main process

⚠️ Important:

Ctrl + C may stop the container

Safer alternative → use docker exec

📌 4. View Container Logs
docker logs my-container

👉 Purpose: See output logs of container

📌 5. Follow Logs (Real-time)
docker logs -f my-container

👉 Purpose: Stream logs live (like tail -f)

📌 6. Copy File → Container
docker cp file.txt my-container:/app/

👉 Purpose: Copy file from host → container

📌 7. Copy File ← Container
docker cp my-container:/app/file.txt .

👉 Purpose: Copy file from container → host

📌 8. Inspect Container Details
docker inspect my-container

👉 Purpose: Get full JSON info (IP, volumes, config)

📌 9. View Running Processes in Container
docker top my-container

👉 Purpose: Show active processes inside container

📌 10. Check Resource Usage
docker stats

👉 Purpose: Monitor CPU, memory, network usage

📌 11. Pause Container
docker pause my-container

👉 Purpose: Freeze container processes

📌 12. Unpause Container
docker unpause my-container

👉 Purpose: Resume paused container

📌 13. Rename Container
docker rename old-name new-name

👉 Purpose: Change container name

📌 14. Update Container Resources
docker update --memory 500m my-container

👉 Purpose: Limit container memory usage

🎯 Key Concept (Very Important)

👉 Difference between exec vs attach

Command	Use Case	Safe?
docker exec	Run commands / open new terminal	✅ Safe
docker attach	Attach to main process	⚠️ Risky
💡 Pro Tip (Real DevOps Insight)

👉 Always prefer:

docker exec -it container-name bash

Instead of attach — because it doesn’t crash your container.




📦 Day 05 – Docker Volume Commands (With Purpose)

👉 Volumes are used to store data permanently (even if container is deleted)

📌 1. Create a Volume
docker volume create my-volume

👉 Purpose: Create a named volume for persistent storage

📌 2. List All Volumes
docker volume ls

👉 Purpose: Show all available volumes

📌 3. Inspect Volume
docker volume inspect my-volume

👉 Purpose: Get details (location, mount point, etc.)

📌 4. Remove a Volume
docker volume rm my-volume

👉 Purpose: Delete a volume

⚠️ Volume must not be in use by any container

📌 5. Remove All Unused Volumes
docker volume prune

👉 Purpose: Clean up unused volumes (free space)

📌 6. Mount Volume to Container
docker run -d -v my-volume:/app nginx

👉 Purpose: Attach volume to container

my-volume → volume name

/app → container path

📌 7. Bind Mount (Host Folder → Container)
docker run -d -v /host/path:/app nginx

👉 Purpose: Use local system folder inside container

💡 Example (Windows):

docker run -d -v D:\projects:/app nginx
📌 8. Read-Only Volume Mount
docker run -d -v my-volume:/app:ro nginx

👉 Purpose: Mount volume as read-only (secure data)

📌 9. Copy Data Using Volume (Advanced)
docker run -d -v my-volume:/data busybox

👉 Purpose: Share data between multiple containers

📌 10. Backup Volume Data
docker run --rm -v my-volume:/data -v $(pwd):/backup busybox tar czf /backup/backup.tar /data

👉 Purpose: Backup volume data to local system

📌 11. Restore Volume Data
docker run --rm -v my-volume:/data -v $(pwd):/backup busybox tar xzf /backup/backup.tar -C /

👉 Purpose: Restore volume from backup

🎯 Key Concepts (Interview Ready)
🔹 Types of Storage in Docker

Volume (Best Practice)
→ Managed by Docker
→ Persistent & secure

Bind Mount
→ Uses host system folder
→ More control, less isolation

Tmpfs (Memory only)
→ Temporary (RAM storage)

💡 Real-Life Example

👉 Imagine:

Container = App (like Instagram)

Volume = Database (your photos)

If container deletes →
❌ App gone
✅ Data still safe in volume

⚠️ Important Points

Data inside container is temporary

Always use volumes for database/storage

Volumes are independent of container lifecycle