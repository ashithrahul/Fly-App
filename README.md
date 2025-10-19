# Fly-App

Added the Fullstack application Searchify With 2 Page 
1. Landing page 
2. Search result page


The App is Hoised in AWS

[LIVE Demo](http://54.237.209.95/)

## Summary

Techstack

- **Frontend**: React.js application with routing, RTK state management
- **Backend**: Express.js REST API with MySQL database integration using Sequelize ORM
- **Database**: MySQL 8.0 for data persistence
- **Containerization**: Docker/Docker compose support for easy deployment
- **Cloud**: AWS EC2

## Installation & Setup


### Option 1: Using Docker Compose (Recommended)

 [Fly-App](https://github.com/ashithrahul/Fly-App.git) Consist of docker-compose file which pulles the lastest imagies for BE/FE

 it also consist of Each repo as submodules 

1. **Clone the repository with submodules:**
   ```bash
   git clone --recursive https://github.com/ashithrahul/Fly-App.git
   cd Fly-App
   ```

2. **Add needed env:**
   As per the Docker Compose few env variable are expected, create .env file and add required env variable

3. **Start all services:**
   ```bash
   docker-compose up -d
   ```

4. **Wait for services to start** (approximately 1-2 minutes for MySQL to initialize)

5. **Verify all services are running:**
   ```bash
   docker-compose ps
   ```

### Option 2: Local Development Setup

Use  [Fly-App](https://github.com/ashithrahul/Fly-App.git) contain both FE/BE as submodule Or 
Use the induvidual repos [Fly-Frontend](https://github.com/ashithrahul/Fly-Frontend) and [Fly-Backend](https://github.com/ashithrahul/Fly-Backend)


1. **Clone the repository:**
   ```bash
   git clone --recursive https://github.com/ashithrahul/Fly-App.git
   cd Fly-App
   ```

2. **Setup Backend:**
   ```bash
   cd Fly-Backend
   npm install
   npm start
   ```

3. **Setup Frontend (in a new terminal):**
   ```bash
   cd Fly-Frontend
   npm install
   npm run dev
   ```

4. ** Other Setup:**
   - Install MySQL
   - Added needed .env for the Fly-Frontend/.env`
   - Update environment variables in `Fly-Backend/.env`

## Expected URLs

After successful installation, you can access:

| Service | URL | Description |
|---------|-----|-------------|
| **Frontend** | [http://localhost:3000](http://localhost:3000) | Main application interface |
| **Backend API** | [http://localhost:1001](http://localhost:1001) | REST API endpoints |
| **Landing Page** | [http://localhost:3000/](http://localhost:3000/) | Application home page |
| **Search Page** | [http://localhost:3000/search](http://localhost:3000/search) | Search functionality |
| **API Health** | [http://localhost:1001/api](http://localhost:1001/api) | API status check |
| **MySQL Database** | `localhost:3306` | Database connection (internal) |

### Environment Variables for Backend

Create a `.env` file in the `Fly-Backend` directory:

```env
# Database Configuration
MYSQL_ROOT_PASSWORD=<pass>
MYSQL_DATABASE=<name>
MYSQL_USER=<user>
MYSQL_PASSWORD=<pass>

# Backend Configuration
DB_HOST=mysql
DB_USER=<db user>
DB_PASSWORD=<db pass>
DB_NAME=<db name>
DB_PORT=3306
PORT=3000
NODE_ENV=production
FRONTEND_URL=<hoisted url>

# Frontend Configuration (for future use)
VITE_API_URL=<api url>

```
### Manual Database Setup

Use the [sql dump](https://github.com/ashithrahul/Fly-App/blob/main/items_backup.sql) file to prepopulate the data, Since data will be empty in the initial setup 


## Docker Images

The project provides the following Docker images on Docker Hub:
- `ashithrahul93/fly-backend:latest` - Backend only
- `ashithrahul93/fly-frontend:latest` - Frontend only
