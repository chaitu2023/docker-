
# Zakool Maintenance Page

This project is a static HTML page designed for the Zakool maintenance message. The page is containerized using Docker and served with **Nginx**.

## Project Structure

```
.
├── assets/               # Folder containing images, icons, and other assets
├── Dockerfile            # Dockerfile to containerize the project
├── index.html            # Main HTML file
└── README.md             # Project documentation
```

## Prerequisites

- Docker installed on your system
- Basic knowledge of command-line operations

## Building and Running the Project

### Step 1: Clone or Download the Repository

Clone this repository to your local machine:

```bash
git clone <repository-url>
cd <project-directory>
```

### Step 2: Build the Docker Image

Run the following command to build the Docker image:

```bash
docker build -t zakool-html .
```

### Step 3: Run the Docker Container

Run the container using the command:

```bash
docker run -d -p 8080:80 .
```

This will start the container and map port `80` from the container to port `8080` on your host machine.

### Step 4: Access the Application

Open your web browser and navigate to:

```
http://localhost:8080
```

You should see the Zakool maintenance page.
