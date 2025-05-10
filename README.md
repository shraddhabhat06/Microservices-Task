# Microservices-Task

## Overview
This document provides details on testing various services after running the `docker-compose` file. These services include User, Product, Order, and Gateway Services. Each service has its own endpoints for testing purposes.

---

## Services and Endpoints

### **User Service**
- **Base URL:** `http://localhost:3000`
- **Endpoints:**
  - **List Users:**  
    ```
    curl http://localhost:3000/users
    ```
    Or open in your browser: [http://localhost:3000/users](http://localhost:3000/users)

---

### **Product Service**
- **Base URL:** `http://localhost:3001`
- **Endpoints:**
  - **List Products:**  
    ```
    curl http://localhost:3001/products
    ```
    Or open in your browser: [http://localhost:3001/products](http://localhost:3001/products)

---

### **Order Service**
- **Base URL:** `http://localhost:3002`
- **Endpoints:**
  - **List Orders:**  
    ```
    curl http://localhost:3002/orders
    ```
    Or open in your browser: [http://localhost:3002/orders](http://localhost:3002/orders)

---

### **Gateway Service**
- **Base URL:** `http://localhost:3003/api`
- **Endpoints:**
  - **Users:**  
    ```
    curl http://localhost:3003/api/users
    ```
  - **Products:**  
    ```
    curl http://localhost:3003/api/products
    ```
  - **Orders:**  
    ```
    curl http://localhost:3003/api/orders
    ```

---

## Instructions
1. Start all services using the `docker-compose` file:
   ```
   docker-compose up
   ```
2. Once the services are running, use the above endpoints to verify the functionality.

Happy testing!


# Microservices Task
This repository contains a microservices-based application built as part of a task submission. The project uses Docker and Docker Compose to manage and run the services.

## Prerequisites
- **Docker**: Version 20.10 or higher
- **Docker Compose**: Version 1.29 or higher

1. **Clone the Repository**
   ```bash
   git clone https://github.com/mohanDevOps-arch/Microservices-Task
   
2.  **Creating multiple folder**
    ```bash
    mkdir -p submission/user-service submission/product-service submission/order-service submission/gateway-service

3. **Creating User Service Dockerfile:**

    ```bash
    cd user-service
    nano Dockerfile

    FROM node:14
    WORKDIR /app
    COPY package.json .
    RUN npm install
    COPY app.js .
    EXPOSE 3000
    CMD ["node", "app.js"]

4. **Creating Product Service Dockerfile:**
    ```bash
    cd user-service
    nano Dockerfile

    FROM node:14
    WORKDIR /app
    COPY package.json .
    RUN npm install
    COPY app.js .
    EXPOSE 3001
    CMD ["node", "app.js"]

5. **Creating Order Service Dockerfile:**
    ```bash
    cd order-service
    nano Dockerfile

    FROM node:14
    WORKDIR /app
    COPY package.json .
    RUN npm install
    COPY app.js .
    EXPOSE 3002
    CMD ["node", "app.js"]


6. **Creating Order Service Dockerfile:**
    ```bash
    cd gateway-service
    nano Dockerfile 

    FROM node:14
    WORKDIR /app
    COPY package.json .
    RUN npm install
    COPY app.js .
    EXPOSE 3003
    CMD ["node", "app.js"]


7. **Creatign docker-compose file**
    ```bash
    nano submission/docker-compose.yml

    version: '3'
    services:
      user-service:
        build: ./user-service
        ports:
          - "3000:3000"
        networks:
          - microservices-network
      product-service:
        build: ./product-service
        ports:
          - "3001:3001"
        networks:
          - microservices-network
      order-service:
        build: ./order-service
        ports:
          - "3002:3002"
        networks:
          - microservices-network
      gateway-service:
        build: ./gateway-service
        ports:
          - "3003:3003"
        networks:
          - microservices-network
    networks:
      microservices-network:
        driver: bridge


8. **Running Docker-compose:**
    ```bash
    cd submission
    docker-compose up --build
  
## Screenshot

1. User Service





