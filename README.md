# Horizontally Scalable Live Chat Application

This is a horizontally scalable live chat application built using Node.js, WebSockets, Nginx, Redis, and Kubernetes. This application allows for real-time communication between users in a scalable and reliable manner.

## Features

- Real-time messaging: Users can send and receive messages in real-time.
- Horizontally scalable: The application can handle increasing loads by adding more instances.
- High availability: Kubernetes ensures that the application remains available even in the face of failures.
- Load balancing: Nginx acts as a load balancer to distribute incoming traffic across multiple instances.
- Persistent storage: Redis is used for storing chat messages to ensure reliability and persistence.

## Architecture

The architecture of the application consists of several components:

1. **Node.js**: The backend server is built using Node.js. It handles WebSocket connections, message routing, and interaction with Redis.

2. **WebSockets**: WebSocket protocol is used for real-time bidirectional communication between clients and the server.

3. **Nginx**: Nginx acts as a reverse proxy and load balancer. It distributes incoming WebSocket connections across multiple instances of the Node.js server.

4. **Redis**: Redis is used as a message broker and for storing chat messages. It ensures that messages are reliably delivered and persisted even if the backend server goes down. Redis pub/sub is used so that clients that are in the same chat room but connected to different servers can still send and receive each others' messages.

5. **Kubernetes**: Kubernetes is used for container orchestration. It manages the deployment, scaling, and monitoring of the application.


## System Diagram

![System Diagram](https://user-images.githubusercontent.com/96862218/209307263-e739e9eb-5034-4c13-a5f5-8802824eeef5.svg)

## Setup Instructions

1. **Clone the repository**: Clone the repository to your local machine.

    ```bash
    git clone https://github.com/tripathiraj9801/Chat-Backend.git
    ```

2. **Install dependencies**: Navigate to the project directory and install dependencies using npm.

    ```bash
    cd horizontally-scalable-chat
    npm install
    ```

3. **Configuration**: Update the configuration files as needed. This may include configuring Nginx for load balancing and updating Kubernetes deployment files.

4. **Build Docker images**: Build Docker images for the Node.js server and Nginx.

    ```bash
    docker build -t your-username/node-server ./node-server
    docker build -t your-username/nginx ./nginx
    ```

5. **Deploy to Kubernetes**: Deploy the application to Kubernetes using the provided deployment files.

    ```bash
    kubectl apply -f kubernetes/
    ```

6. **Access the application**: Once deployed, access the application through the assigned Kubernetes service endpoint.

## Usage

1. **Sign up or log in**: Users can sign up for a new account or log in with their existing credentials.

2. **Start chatting**: Once logged in, users can start sending and receiving messages in real-time.

3. **Scalability**: As the load increases, Kubernetes will automatically scale the application by adding more instances of the backend server.

## Authors

- [Rajeev Tripathi]

## Try it out

Sadly Live Link is no longer available because AWS EKS is too expensive for me to afford currently. I am working on a Youtube video for the same.:(
# Real-Time-Chat
# Real-Time-Chat
