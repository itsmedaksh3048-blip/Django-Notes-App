# 🚀 Features
1. Full-Stack Architecture: Decoupled backend (Django REST API) and frontend (React UI).
2. CRUD Operations: Create, read, update, and delete personal notes in real time.
3. Dockerized Environment: Pre-configured Dockerfile and multi-container orchestration via docker-compose.
4. Production-Ready Proxy: Nginx configuration for routing, reverse proxying, and static asset serving.
5. Persistent Storage: Configured database integration (PostgreSQL / SQLite / MySQL).

# Simple Notes App for TWS Community
This is a simple notes app built with React and Django.

## Requirements
1. Python 3.9
2. Node.js
3. React

## Installation
1. Clone the repository
```
git clone https://github.com/itsmedaksh3048-blip/Django_Notes_App.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`


---

## 🙏 Credits & Acknowledgments

This project is built upon the open-source repository by **Shubham Londhe** and the TWS community.
- **Original Repository:** [django-notes-app](https://github.com/LondheShubham153/django-notes-app)
- Special thanks to the original creator for the foundational architecture.
