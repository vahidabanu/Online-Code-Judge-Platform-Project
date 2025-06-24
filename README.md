# Online-Code-Judge-Platform-Project
# 🚀 Online Code Judge Platform

A comprehensive online coding platform that allows students to register, solve coding problems, and compete on leaderboards with automated code execution and evaluation.

![CodeJudge Platform](https://img.shields.io/badge/Java-17-orange?style=for-the-badge&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2.0-green?style=for-the-badge&logo=spring)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=for-the-badge&logo=mysql)
![Docker](https://img.shields.io/badge/Docker-Enabled-blue?style=for-the-badge&logo=docker)

## 📋 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Architecture](#-architecture)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [Usage](#-usage)
- [API Documentation](#-api-documentation)
- [Development](#-development)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

## ✨ Features

### 🎯 Core Functionality
- **User Management**: Registration, authentication, and profile management
- **Problem Management**: Create and manage coding problems with test cases
- **Code Execution Engine**: Safe sandboxed execution for Java code using Docker
- **Real-time Results**: Immediate feedback on code submissions
- **Leaderboards**: Performance ranking and competition tracking
- **Multi-language Support**: Java (extensible to Python, C++, JavaScript)

### 🔒 Security Features
- **Docker Sandboxing**: Isolated execution environments
- **JWT Authentication**: Secure token-based authentication
- **Role-based Access**: Student, Teacher, and Admin roles
- **Input Validation**: Comprehensive input sanitization
- **Rate Limiting**: Protection against abuse

### 📊 Analytics & Monitoring
- **Submission Statistics**: Detailed performance metrics
- **Problem Analytics**: Success rates and difficulty analysis
- **User Progress Tracking**: Individual and comparative statistics
- **Health Monitoring**: Application and service health checks

## 🛠 Tech Stack

### Backend
- **Java 17**: Core programming language
- **Spring Boot 3.2.0**: Application framework
- **Spring Security**: Authentication and authorization
- **Spring Data JPA**: Database access layer
- **MySQL 8.0**: Primary database
- **JWT**: Token-based authentication
- **Docker Java Client**: Container management

### Frontend
- **HTML5**: Semantic markup
- **CSS3**: Modern styling with responsive design
- **JavaScript (ES6+)**: Interactive functionality
- **Font Awesome**: Icon library
- **Inter Font**: Modern typography

### Infrastructure
- **Docker**: Containerization
- **Docker Compose**: Multi-service orchestration
- **Nginx**: Reverse proxy and static file serving
- **Redis**: Caching and session management
- **GitHub Actions**: CI/CD pipeline
- **AWS EC2**: Cloud deployment

### Development Tools
- **Maven**: Build tool and dependency management
- **Lombok**: Boilerplate code reduction
- **JUnit**: Unit testing
- **MySQL Workbench**: Database management

## 🏗 Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │    Backend      │    │   Database      │
│   (HTML/CSS/JS) │◄──►│  (Spring Boot)  │◄──►│    (MySQL)      │
└─────────────────┘    └─────────────────┘    └─────────────────┘
         │                       │                       │
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Nginx         │    │  Docker Engine  │    │   Redis Cache   │
│   (Reverse      │    │  (Code          │    │   (Sessions)    │
│    Proxy)       │    │   Execution)    │    │                 │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Key Components

1. **Code Execution Engine**: Docker-based sandboxed environment
2. **User Management System**: Authentication and authorization
3. **Problem Management**: CRUD operations for coding problems
4. **Submission System**: Code submission and evaluation
5. **Leaderboard System**: Performance ranking and statistics
6. **API Layer**: RESTful endpoints for all operations

## 🚀 Quick Start

### Prerequisites
- Java 17 or higher
- Maven 3.6 or higher
- MySQL 8.0 or higher
- Docker (optional, for containerized deployment)

### Option 1: Docker (Recommended)

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd online-code-judge-platform
   ```

2. **Start with Docker Compose**
   ```bash
   docker compose up -d
   ```

3. **Access the application**
   - Frontend: http://localhost:3000
   - Backend API: http://localhost:8080
   - Database: localhost:3306

### Option 2: Manual Setup

1. **Install dependencies** (see [SETUP_GUIDE.md](SETUP_GUIDE.md))

2. **Set up database**
   ```bash
   mysql -u root -p < database/init.sql
   ```

3. **Start backend**
   ```bash
   cd backend
   mvn clean install
   mvn spring-boot:run
   ```

4. **Access frontend**
   - Open `frontend/index.html` in your browser
   - Or serve with a local server: `python -m http.server 3000`

## 📦 Installation

### Detailed Setup Instructions

For comprehensive installation instructions, see [SETUP_GUIDE.md](SETUP_GUIDE.md).

### Environment Variables

Create a `.env` file for Docker deployment:

```env
# Database
MYSQL_ROOT_PASSWORD=codejudge123
MYSQL_DATABASE=codejudge
MYSQL_USER=codejudge
MYSQL_PASSWORD=codejudge123

# Backend
SPRING_PROFILES_ACTIVE=docker
JWT_SECRET=your-secret-key-here

# Docker
CODE_EXECUTION_DOCKER_IMAGE=openjdk:17-jdk-slim
CODE_EXECUTION_TIMEOUT=30
CODE_EXECUTION_MEMORY_LIMIT=512m
```

## 🎮 Usage

### Getting Started

1. **Register/Login**
   - Visit the application
   - Register a new account or login with existing credentials
   - Sample accounts available (see [Sample Data](#sample-data))

2. **Browse Problems**
   - View available coding problems
   - Filter by difficulty (Easy, Medium, Hard, Expert)
   - Search for specific problems

3. **Solve Problems**
   - Select a problem to view details
   - Write your solution in the code editor
   - Choose programming language
   - Submit and get immediate feedback

4. **Track Progress**
   - View your submission history
   - Check leaderboard rankings
   - Monitor your statistics

### Sample Data

The platform comes with pre-loaded sample data:

**Users:**
- Admin: `admin` / `password123`
- Teacher: `teacher` / `password123`
- Students: `student1`, `student2`, `student3` / `password123`

**Problems:**
- Hello World (Easy)
- Sum of Two Numbers (Easy)
- Factorial (Medium)
- Fibonacci Sequence (Medium)
- Prime Number Check (Hard)

### Code Submission Example

```java
// Java solution for "Hello World" problem
public class Solution {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## 📚 API Documentation

Comprehensive API documentation is available in [docs/API_DOCUMENTATION.md](docs/API_DOCUMENTATION.md).

### Key Endpoints

- `POST /api/users/register` - User registration
- `POST /api/users/login` - User authentication
- `GET /api/problems` - List problems
- `POST /api/submissions` - Submit code
- `GET /api/users/leaderboard` - Get leaderboard

### Authentication

All protected endpoints require JWT token in Authorization header:
```
Authorization: Bearer <your-jwt-token>
```

## 🛠 Development

### Project Structure

```
├── backend/                 # Spring Boot application
│   ├── src/main/java/      # Java source code
│   ├── src/main/resources/ # Configuration files
│   └── Dockerfile          # Backend containerization
├── frontend/               # Web interface
│   ├── static/            # HTML, CSS, JS files
│   └── Dockerfile         # Frontend containerization
├── database/              # Database scripts
├── docker/                # Docker configuration
├── scripts/               # Deployment scripts
├── docs/                  # Documentation
└── tests/                 # Test suites
```

### Running Tests

```bash
# Backend tests
cd backend
mvn test

# Frontend tests (if configured)
cd frontend
npm test
```

### Code Style

- **Java**: Follow Google Java Style Guide
- **JavaScript**: Use ESLint configuration
- **CSS**: Follow BEM methodology
- **HTML**: Semantic markup with accessibility

### Adding New Features

1. **Backend Changes**
   - Add new entities in `backend/src/main/java/com/codejudge/entity/`
   - Create services in `backend/src/main/java/com/codejudge/service/`
   - Add controllers in `backend/src/main/java/com/codejudge/controller/`

2. **Frontend Changes**
   - Update HTML in `frontend/index.html`
   - Modify styles in `frontend/static/css/style.css`
   - Add functionality in `frontend/static/js/`

3. **Database Changes**
   - Update entities and let JPA handle schema changes
   - Or manually update `database/init.sql`

## 🚀 Deployment

### Local Development

```bash
# Start all services
docker compose up -d

# View logs
docker compose logs -f

# Stop services
docker compose down
```

### Production Deployment

1. **AWS EC2 Setup**
   ```bash
   # Install Docker on EC2
   sudo yum update -y
   sudo yum install -y docker
   sudo service docker start
   sudo usermod -a -G docker ec2-user
   
   # Install Docker Compose
   sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   sudo chmod +x /usr/local/bin/docker-compose
   ```

2. **Deploy Application**
   ```bash
   # Clone repository
   git clone <repository-url>
   cd online-code-judge-platform
   
   # Start services
   docker compose up -d
   ```

3. **Configure Domain**
   - Set up domain name and SSL certificates
   - Configure Nginx for production
   - Set up monitoring and logging

### CI/CD Pipeline

The project includes GitHub Actions for automated deployment:

- **Testing**: Automated unit and integration tests
- **Building**: Docker image creation
- **Deployment**: Automatic deployment to AWS EC2
- **Monitoring**: Health checks and notifications

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/amazing-feature
   ```
3. **Make your changes**
4. **Add tests** for new functionality
5. **Commit your changes**
   ```bash
   git commit -m 'Add amazing feature'
   ```
6. **Push to the branch**
   ```bash
   git push origin feature/amazing-feature
   ```
7. **Open a Pull Request**

### Development Guidelines

- Write clear, descriptive commit messages
- Follow the existing code style
- Add tests for new features
- Update documentation as needed
- Ensure all tests pass before submitting

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Support

### Getting Help

- **Documentation**: Check the [docs/](docs/) directory
- **Issues**: Create an issue on GitHub
- **Discussions**: Use GitHub Discussions for questions

### Common Issues

1. **Docker not starting**
   - Ensure Docker Desktop is running
   - Check system requirements
   - Restart Docker service

2. **Database connection errors**
   - Verify MySQL is running
   - Check credentials in configuration
   - Ensure database exists

3. **Port conflicts**
   - Change ports in configuration files
   - Check for other services using same ports

### Troubleshooting

For detailed troubleshooting steps, see [SETUP_GUIDE.md](SETUP_GUIDE.md).

## 🙏 Acknowledgments

- **Spring Boot Team** for the excellent framework
- **Docker Team** for containerization technology
- **MySQL Team** for the database system
- **Open Source Community** for various libraries and tools

## 📈 Roadmap

### Planned Features
- [ ] Support for additional programming languages (Python, C++, JavaScript)
- [ ] Real-time collaborative coding
- [ ] Advanced analytics and insights
- [ ] Mobile application
- [ ] Integration with learning management systems
- [ ] Code plagiarism detection
- [ ] Automated problem generation
- [ ] Contest management system

### Performance Improvements
- [ ] Caching layer implementation
- [ ] Database query optimization
- [ ] Load balancing setup
- [ ] CDN integration for static assets

---

**Made with ❤️ by the CodeJudge Team**

For questions, issues, or contributions, please visit our [GitHub repository](https://github.com/your-username/online-code-judge-platform).
