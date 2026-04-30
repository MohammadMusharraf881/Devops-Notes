📝 Docker Compose File (version: '3.8')
Services Defined
App (Node.js Application)

Image: node:18 → Uses official Node.js v18 image.

Container Name: node-app

Working Directory: /usr/src/app

Volumes:

.:/usr/src/app → Mounts current project folder into container (live code sync).

Command: npm start → Runs the app.

Ports:

"3000:3000" → Maps host port 3000 to container port 3000.

Environment Variables:

MONGO_URL=mongodb://mongo:27017/mydb → Connects app to MongoDB service.

depends_on:

mongo → Ensures MongoDB starts before the app.

Mongo (Database Service)

Image: mongo:6 → Uses official MongoDB v6 image.

Container Name: mongo-db

Ports:

"27017:27017" → Exposes MongoDB default port.

Volumes:

mongo-data:/data/db → Persists database data in a named volume.

Volumes
mongo-data → Named volume for MongoDB data persistence (data survives container restarts).

⚡ Key Points to Remember
services: defines different containers (app + database).

depends_on: ensures startup order (app waits for DB).

volumes: keep data persistent and allow live code sync.

ports: map container ports to host machine ports.

environment: passes configuration variables (like DB connection string).

📌 Usage
Start everything:

bash
docker compose up
Stop everything:

bash
docker compose down
Data remains safe in mongo-data volume even after containers are stopped.