
**This `README.md` provides a complete guide for your `docker-project` directory, including explanations of all files, usage instructions, and troubleshooting steps.**


# Flask Redis Counter

This is a simple Flask application that connects to a Redis instance to implement a visit counter.
Every time you access the application, the counter increments, and the current count is displayed.

---

## Features
- Python Flask web application.
- Uses Redis as a backend to store the visit counter.
- Demonstrates Docker integration with Flask and Redis using `docker-compose`.

---

## Project Structure
/project
├── app/
│   ├── app.py
│   ├── requirements.txt
|___Dockerfile
└── Docker-compose.yml


## Prerequisites
1. **Docker** and **Docker Compose** installed on your system.


## Installation and Usage

### Running with Docker Compose
1. Clone the repository:
   
   git clone https://github.com/Ernieblack/Docker-Project.git
   cd project
   
2. Build and start the containers:
docker-compose up --build

3. Open your browser and go to: http://localhost:5000

Configuration
The application relies on the following environment variables for Redis configuration:

REDIS_HOST: The Redis host (default: redis).
You can customize these in the docker-compose.yml file under the web service.

Example Output
Visiting the root URL (/) will return:
Hello, World! You have visited 1 times.
The visit count will increase with each reload.

Files Overview
app.py
Connects to Redis using the host specified in the REDIS_HOST environment variable.
Provides a simple / route to display the visit count.

requirements.txt
Contains the Python dependencies:
flask
redis

Dockerfile
Defines how to build the Docker image for the Flask application.

docker-compose.yml
Defines a multi-container setup with Flask and Redis.
Troubleshooting
Redis Connection Issues:

Ensure Redis is running and accessible at the host specified in REDIS_HOST.

Port Conflicts:
If the default ports (5000 for Flask and 6379 for Redis) are in use, update the docker-compose.yml file to map different ports.
