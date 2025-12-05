# Smart-Property-Management-System

Overview

This scaffold provides a ready-to-publish portfolio project for a Property Management System (PMS). It focuses on backend architecture, cloud-native design, multi-tenant support, event-driven notifications, and a polished Angular frontend. The repository layout below includes starter code for the API, EF Core models, a basic Angular app, and deployment CI/CD templates.

Smart Property Management — Quick Start

This project demonstrates a cloud-native property management system built with .NET 8 and Angular, designed for multi-tenant usage and extensibility.

Local prerequisites

.NET 8 SDK

Node.js 18+

Docker & docker-compose

SQL Server (or use docker-compose postgres/sqlserver in the repo)

Run locally with Docker

# from repo root
cd backend
docker-compose up --build
# open http://localhost:5000/swagger


# start frontend
cd frontend/angular-app
docker build -t spm-frontend .
docker run -p 4200:80 spm-frontend
# open http://localhost:4200

Run migrations (if running .NET locally)

cd backend/src/SPM.Infrastructure
dotnet ef database update --project ../SPM.Infrastructure --startup-project ../SPM.Api

Deploy to Azure

Use infra/bicep/main.bicep to deploy Azure SQL, App Service, Event Grid topics and Function Apps.

Use azure-pipelines.yml or GitHub Actions to build and push images to ACR and deploy to App Service.
