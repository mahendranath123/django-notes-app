## **📝 Simple Notes App** 
This is a **Simple Notes App** built with **React** and **Django** to help users jot down and organize their notes effortlessly. The project leverages **Docker**, **Nginx**, and **MySQL** for a robust and scalable setup.  

---

## **🚀 Features** 
- **Django Backend**: Provides APIs for managing notes.  
- **React Frontend**: An intuitive user interface for creating, editing, and viewing notes.  
- **MySQL Database**: Stores all notes securely.  
- **Nginx Integration**: Serves as a reverse proxy for the app.  
- **Dockerized Deployment**: Simplified containerized deployment with Docker.  

---

## 🛠️ Tech Stack  
- **Frontend**: React, JavaScript, CSS  
- **Backend**: Django (Python 3.9)  
- **Database**: MySQL  
- **Web Server**: Nginx  
- **Containerization**: Docker, Docker Compose  

---

## 🧩 Requirements  
- **Python**: >= 3.9  
- **Node.js**: >= 14.x  
- **Docker**: >= 20.x  
- **Docker Compose**: >= 1.29  

---

## 📦 Installation  

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/your-username/notes-app.git
   cd notes-app
   ```

2. **Build the Docker Images**  
   Build the entire app using the Dockerfile provided:  
   ```bash
   docker build -t notes-app .
   ```

3. **Run the Application**  
   Start the app in a Docker container and expose it on `http://localhost:8000`:  
   ```bash
   docker run -d -p 8000:8000 notes-app:latest
   ```

4. **Using Docker Compose** (Optional)  
   For an even simpler setup (with Nginx and MySQL):  
   ```bash
   docker-compose up -d
   ```

---

## 📋 Configuration  

### Docker Compose Setup  
This app uses `docker-compose.yml` to configure and run the services:  
- **Backend (Django)**: Accessible via the internal Docker network.  
- **Frontend (React)**: Built and served via Nginx.  
- **Database (MySQL)**: Stores all user data persistently.  

You can modify the `docker-compose.yml` file for your specific environment:  
```yaml
version: "3.8"
services:
  app:
    build: .
    ports:
      - "8000:8000"
  nginx:
    image: nginx
    ...
  db:
    image: mysql:latest
    ...
```

---

## 🌐 Nginx Configuration  
An **Nginx** configuration file is included to act as a reverse proxy:  
- Redirects API requests to the Django backend.  
- Serves static files and the React frontend.  

```nginx
server {
  listen 80;
  server_name localhost;

  location /api/ {
    proxy_pass http://backend:8000/;
  }

  location / {
    root /usr/share/nginx/html;
    index index.html;
  }
}
```

---

## 🖥️ Usage  

- Navigate to `http://localhost:8000` to access the app.  
- Use the app to create, edit, and delete notes.  

---

## 🤝 Contributing  
Contributions are welcome! Feel free to submit a pull request or open an issue to improve this app.  

---

## 🧰 Project Structure  

```plaintext
├── backend/         # Django backend (APIs, models, etc.)
├── frontend/        # React frontend (components, assets)
├── nginx/           # Nginx configuration files
├── docker-compose.yml
├── Dockerfile
└── README.md
```

---

## 🏆 Why This Project?  

This app is perfect for demonstrating:  
- **Full Stack Development Skills**: Integration of Django and React.  
- **Containerization Expertise**: Using Docker for deployment.  
- **DevOps Practices**: Multi-service orchestration with Docker Compose.  
- **Web Server Management**: Nginx setup and configuration.  

Great for your **resume**, this project shows hands-on experience with modern web technologies.  

---



---

## 📜 License  
This project is licensed under the MIT License.  

---

## 🌟 Acknowledgements  
- **React Docs**: [React.js Official Documentation](https://reactjs.org/docs/)  
- **Django Docs**: [Django Official Documentation](https://docs.djangoproject.com/)  
- **Docker Docs**: [Docker Documentation](https://docs.docker.com/)  



