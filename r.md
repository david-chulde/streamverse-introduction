## Microservices APIs

![Microservices Diagram](img.png)

### 1. Authentication and User Microservices (sv-ms-auth) - (JS NestJS) → (PostgreSQL)

1. **Authentication Service (sv-ms-auth-session)** | port: 9000
   - Login, logout, and JWT token generation.
   - Session management and token renewal.
   - Password recovery via OTP or token.
2. **Profile Account Management Service (sv-ms-auth-profile)** | port: 9001
   - Profile updates.
   - Account deletion.

### 2. Content (Videos) Microservices (sv-ms-video) - (JS NestJS) → (PostgreSQL)

3. **Video Upload Service (sv-ms-video-upload)** | port: 9004
   - Video processing and storage.
   - Metadata management (title, description, tags).
4. **Video Feed Service (sv-ms-video-feed)** | port: 9004
   - Recommendation generation based on history and preferences.
   - Video pagination and ranking.

### 3. Social Interaction Microservices (sv-ms-social) - (Java & Spring Boot) → (MariaDB)

5. **Comment Service (sv-ms-social-comment)** | port: 9009
   - Creation, editing, and deletion of comments.
6. **Likes and Dislikes Service (sv-ms-social-like)** | port: 9010
   - Tracking of likes and dislikes.
   - Statistics for popularity metrics.

## Databases

1. **Users and Authentication**: Relational database (PostgreSQL).
2. **Videos and Metadata**: Relational database (PostgreSQL).
3. **Comments**: Relational database (MariaDB).
4. **Likes and Dislikes**: Relational database (MariaDB).

### Install docker in EC2 | Grant Privileges of startup

```bash

# Install docker

sudo dnf install docker -y

# Add group of user

sudo usermod -aG docker ec2-user
newgrp docker

# Run docker in startup

sudo systemctl start docker
sudo systemctl enable docker
```

### Pull Images from Docker HUB in in EC2

```bash

# Push changes from local machine to docker hub

docker buildx build --platform linux/amd64 -t edchulde/ms-auth-session:latest --push .

# Pull changes from EC2
# latest(means tag)
docker run -d --restart=always -p 9000:3000 --name ms-auth-session edchulde/ms-auth-session:latest
```

### Delete containers and images in EC2

```bash
# Stop containers

docker stop $(docker ps -aq)

# Remove containers

docker rm $(docker ps -aq)

# Remove images

docker rmi $(docker images -aq)
```

### Build proyects

#### Java (Springboot)

```bash

# Build proyect

./gradlew clean build

# Run proyect

./gradlew bootRun
```

#### NestJs | Nextjs

```bash

# Build proyect

npm run build

# Run proyect

npm run start:dev
```

```bash

# Build proyect

npm run build

# Run proyect

npm run dev
```
