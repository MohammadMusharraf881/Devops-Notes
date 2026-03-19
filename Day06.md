Container intraction commands:

docker exec -it<container_id> bash -pens terminal inside a container

docker logs <container_id> -shows container output logs.

docker inspect <container_id> display detailed configuration in json format

docker stats shows live cpu


📦 Docker Volume Commands
📌 Create Volume
docker volume create my-volume

👉 Create a new volume

📌 List Volumes
docker volume ls

👉 Show all volumes

📌 Inspect Volume
docker volume inspect my-volume

👉 View details (mount path, config)

📌 Remove Volume
docker volume rm my-volume

👉 Delete a specific volume

📌 Remove Unused Volumes
docker volume prune

👉 Delete all unused volumes

📌 Use Volume in Container
docker run -d -v my-volume:/app nginx

👉 Mount volume to container

📌 Bind Mount (Host → Container)
docker run -d -v /host/path:/app nginx

👉 Use local folder inside container

📌 Read-Only Volume
docker run -d -v my-volume:/app:ro nginx

👉 Mount volume as read-only

📌 Share Volume Between Containers
docker run -d -v my-volume:/data busybox

👉 Same volume can be used by multiple containers

📌 Backup Volume
docker run --rm -v my-volume:/data -v $(pwd):/backup busybox tar czf /backup/backup.tar /data

👉 Backup volume data

📌 Restore Volume
docker run --rm -v my-volume:/data -v $(pwd):/backup busybox tar xzf /backup/backup.tar -C /

👉 Restore data into volume

🎯 One-Line Revision

👉 Volume = Permanent storage for containers