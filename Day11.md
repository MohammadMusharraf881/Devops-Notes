Docker Networking:

Docker provides different network drivers to control how containers communicate.
 A. Bridge Network (Default)
Default network when you run a container.
Containers on same bridge can communicate via IP.
Best for standalone containers on single host.


# List networks
docker network ls

# Inspect bridge network
docker network inspect bridge

# Create custom bridge network
docker network create my_bridge_net

# Run container in custom bridge
docker run -d --name container1 --network my_bridge_net nginx
docker run -d --name container2 --network my_bridge_net alpine sleep 300

# Test communication
docker exec -it container2 ping container1

Container shares host’s networking stack.
No separate IP.
Faster performance.
Linux only.
 
docker run -d --network host nginx
curl http://localhost


Used in Docker Swarm.
Connects containers across multiple hosts.


# Initialize swarm
docker swarm init

# Create overlay network
docker network create -d overlay my_overlay

# Deploy service using overlay
docker service create --name web --network my_overlay -p 8080:80 nginx



Docker has built-in DNS.
Containers resolve each other by container name (if same custom network).
Works only in user-defined bridge networks.


docker network create app_net

docker run -d --name backend --network app_net nginx
docker run -it --name client --network app_net alpine sh

ping backend

