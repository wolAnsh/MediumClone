Conduit: Full-Stack Blogging API (Medium Clone)

A production-ready RESTful API for a content-driven social blogging platform, inspired by Medium. Built with FastAPI, PostgreSQL, and Docker, this project demonstrates clean backend architecture, secure authentication, and automated CI/CD pipelines.

🚀 Tech Stack

Framework: FastAPI (Python 3.8+)

Database: PostgreSQL with async asyncpg driver

ORM / Migrations: Databases, SQLAlchemy (Core), Alembic

Authentication: JWT (JSON Web Tokens) with Passlib

Containerization: Docker & Docker Compose

Testing: Pytest & Coverage

CI/CD: GitHub Actions

✨ Features

User Authentication: Secure JWT-based registration and login.

Profile Management: Update bios, avatars, and follow/unfollow other authors.

Article Engine: Full CRUD operations for markdown-based articles.

Social Engagement: Comment on posts and favorite/unfavorite articles.

Content Discovery: Filter feeds by specific tags, authors, or favorited content.

🐳 Quickstart (Docker)

The easiest way to run the application is via Docker Compose, which spins up both the FastAPI backend and the PostgreSQL database.

Clone the repository:

git clone https://github.com/wolAnsh/MediumClone.git
cd MediumClone


Set up environment variables:

cp .env.example .env
# Generate a secure secret key and add it to your .env file
echo "SECRET_KEY=$(openssl rand -hex 32)" >> .env


Build and run the containers:

docker-compose up --build


The API will be available at http://localhost:8000.
Interactive Swagger API documentation is automatically generated and accessible at http://localhost:8000/docs.

💻 Local Development (Poetry)

If you prefer to run the application locally without Docker, you will need an active PostgreSQL instance.

Install dependencies using Poetry:

poetry install
poetry shell


Configure your Database:
Update your .env file with your local PostgreSQL credentials:

DATABASE_URL=postgresql://user:password@localhost:5432/rwdb


Run database migrations:

alembic upgrade head


Start the development server:

uvicorn app.main:app --reload


🧪 Testing

The test suite is built with pytest. To execute all tests and check coverage, run:

pytest


📂 Project Structure

app
├── api              # Web routes, dependency injection, and error handlers
├── core             # App configuration, security, and lifecycle events
├── db               # Database repositories, queries, and Alembic migrations
├── models           # Pydantic models (domain logic and request/response schemas)
├── resources        # Static strings and response messages
├── services         # Core business logic (JWT generation, hashing, etc.)
└── main.py          # FastAPI application factory
