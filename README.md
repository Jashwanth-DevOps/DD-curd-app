In this DevOps task, you need to build and deploy a full-stack CRUD application using the MEAN stack (MongoDB, Express, Angular 15, and Node.js). The backend will be developed with Node.js and Express to provide REST APIs, connecting to a MongoDB database. The frontend will be an Angular application utilizing HTTPClient for communication.  

The application will manage a collection of tutorials, where each tutorial includes an ID, title, description, and published status. Users will be able to create, retrieve, update, and delete tutorials. Additionally, a search box will allow users to find tutorials by title.

## Project setup

### Node.js Server

cd backend

npm install

You can update the MongoDB credentials by modifying the `db.config.js` file located in `app/config/`.

Run `node server.js`

### Angular Client

cd frontend

npm install

Run `ng serve --port 8081`

You can modify the `src/app/services/tutorial.service.ts` file to adjust how the frontend interacts with the backend.

Navigate to `http://localhost:8081/`




##  Step-by-Step Setup & Deployment

### 1. Prerequisite: Install Docker & Jenkins
On your Ubuntu VM, run these commands to set up your environment:

```
# Update system
sudo apt update -y

# Install Docker
install docker from the offical page 
sudo systemctl start docker
sudo systemctl enable docker

# Install Jenkins
install jenkins from the offical page 

# Give Jenkins permission to run Docker commands
sudo usermod -aG docker jenkins
sudo systemctl restart jenkins
```

### 2. Clone and Run Manually

If you want to test the application manually without the pipeline:
bash
```
### Clone the repository
git clone paste-the-url 

cd DD-curd-app

### Build and start the containers
docker compose up --build -d
```
### 3. Access the Application
Once the containers are running, open your browser and navigate to:
```
URL: http://18.212.97.43 (or your current EC2 Public IP)
```

### 4.CI/CD configuration

#### Pipeline Stages:

- Checkout: Pulls the latest code from GitHub main branch.
- Build & Push: Logs into Docker Hub, builds the Frontend and Backend images, and pushes them to my Docker Hub account (jashwanth112002).
- Deploy: Pulls the new images on the EC2 instance and restarts the containers using docker compose.
- Post-Cleanup: Deletes old/unused images to save disk space.

### Screenshots

#### Jenkins Success:  
 
 -  <img width="1920" height="932" alt="image" src="https://github.com/user-attachments/assets/58d2fc53-72cc-496f-b9ed-351bfa0a4b14" />

#### Docker Hub: 

-   <img width="1915" height="615" alt="image" src="https://github.com/user-attachments/assets/e0377b3b-287a-4806-9cd2-c2b794b951ee" />

#### Working UI:


- <img width="1920" height="971" alt="image" src="https://github.com/user-attachments/assets/61d8708e-b2f3-4589-8887-af313cc8bf1b" />

  

-  <img width="1920" height="919" alt="image" src="https://github.com/user-attachments/assets/68696f36-ccb1-4ab2-b00c-e955494d3ed9" />



-  <img width="1918" height="966" alt="image" src="https://github.com/user-attachments/assets/fc5f366f-f388-4bc2-b29d-13ca8f1d34d7" />




