# 🐋 Index

- [🐋 Index](#-index)
- [🐋 Concepts](#-concepts)
- [🐋 Basic setup: React test demo](#-basic-setup-react-test-demo)
- [🐋 Docker compose (with react demo)](#-docker-compose-with-react-demo)
- [🐋 Docker compose watch (with MERN demo)](#-docker-compose-watch-with-mern-demo)
- [🐋 With Nextjs](#-with-nextjs)

# 🐋 Concepts

Docker is like a 🍱 lunch box for food. You can have the same meal everywhere.

1. Image
2. Container

Image is like a recipe🧾, we can create a lot of cakes 🍰🍰🍰🍰 (container) from the recipe.

3. Volumes
   🍰 (container) -> 🗂 (volume) -> 🌐 (server)
4. Network

🔗[Docker Hub](https://hub.docker.com/)

# 🐋 Basic setup: React test demo

1. create `/Dockerfile` file

2. create `/.dockerignore` file
   - add `node_modules/` into the file
3. build image: `docker build -t react-test .`
4. run image: `docker run react-test`
5. port mapping: `docker run -p 5173:5173 react-test`
6. Ensure the container can access and update code from local directory: `docker run -p 5173:5173 -v "$(pwd):/app" -v /app/node_modules react-test`
7. `docker login`
8. publish on docker hub: `docker tag react-test mydockerusername/react-test`
9. `docker push mydockerusername/react-test`

# 🐋 Docker compose (with react demo)

1. `docker init`
2. change the script in package.json: `"dev": "vite --host"`
3. `docker compose up` or `sudo docker compose up`

# 🐋 Docker compose watch (with MERN demo)

- sync in real time
- rebuild
- sync-restart

`docker compose up`
`docker compose watch`

# 🐋 With Nextjs
