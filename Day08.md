Run Ubuntu container
Pass -e COLLEGE=CSE
Show echo $ COLLEGE
Stop container then check what happened


The command:

docker ps -a
🔍 What it does

It shows all containers on your system:

✅ Running containers
❌ Stopped containers
🆕 Created but never started containers
📋 Example Output
CONTAINER ID   IMAGE     COMMAND       STATUS                     NAMES
a1b2c3d4e5f6   ubuntu    "/bin/bash"   Exited (0) 2 minutes ago   dreamy_morse
f7g8h9i0j1k2   ubuntu    "/bin/bash"   Up 5 minutes               cool_container
🧠 How to Understand It
CONTAINER ID → Unique ID of container
IMAGE → Which image (e.g., ubuntu)
COMMAND → What was run (/bin/bash)
STATUS
Up → Running
Exited → Stopped
NAMES → Auto-generated name
⚡ Common Use Cases
▶️ Start a stopped container
docker start container_id
🔁 Start + attach
docker start -ai container_id
🗑️ Remove container
docker rm container_id
🔥 Pro Tip (Important for Exams)
docker ps → only running containers
docker ps -a → all containers (important difference)



🧠 What is docker exec -it?

It is used to enter a running container and run commands inside it.

👉 Think:

docker run → start a new container
docker exec → go inside an already running container
✅ Correct Syntax
docker exec -it <container_id_or_name> <command>
💻 Most Common Usage (VERY IMPORTANT)
docker exec -it container_id bash

👉 This gives you a terminal inside the container

📋 Example
Step 1: Run container
docker run -dit ubuntu
Step 2: Check container
docker ps
Step 3: Enter container
docker exec -it abc123 bash

Now you are inside:

root@abc123:/#
🔍 What do -i and -t mean?
-i → interactive mode (keep input open)
-t → terminal (TTY)

👉 Together → you can type commands like a normal terminal

⚡ Important Difference (Exam Question)
Command	Use
docker run -it ubuntu	Start new container + enter
docker exec -it	Enter existing running container
❗ Common Errors
❌ Error:
docker exec -it abc123

👉 Missing command → ❌

✅ Correct:
docker exec -it abc123 bash
🔥 Pro Tips
Use bash if available
If not:
docker exec -it container_id sh
Works only if container is running
👉 Check:
docker ps
🧪 Viva One-Liner Answer

👉 "docker exec -it is used to run commands inside a running container interactively."

