# Hello World Demo App (Multi-Env)

![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Azure](https://img.shields.io/badge/Azure-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)

A lightweight **ASP.NET Core 9.0 Web Application** designed as a demonstration payload for testing multi-environment Azure infrastructure deployments. This application serves as the "Hello World" artifact for validating CI/CD pipelines across Dev, Test, and Production environments.

## 📋 Table of Contents

- [Overview](#overview)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Building & Testing](#building--testing)
- [Deployment](#deployment)

## 🎯 Overview

This is a standard Model-View-Controller (MVC) application. Its primary purpose is to verify that:
1.  The Azure App Service is running correctly.
2.  The deployment pipeline successfully delivers code.
3.  Environment-specific configurations are properly applied.

## 💻 Tech Stack

- **Framework**: [.NET 9.0](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)
- **Type**: ASP.NET Core Web App (MVC)
- **Language**: C# 12
- **Server**: Kestrel (Local) / IIS (Azure)

## 📁 Project Structure

```
App/
├── HelloWorldApp.sln           # Visual Studio Solution
└── HelloWorldApp.web/          # Web Project
    ├── Controllers/            # MVC Controllers (Logic)
    ├── Models/                 # Data Models
    ├── Views/                  # Razor Views (UI)
    ├── wwwroot/                # Static assets (CSS, JS, Images)
    ├── Program.cs              # Entry point & startup configuration
    └── appsettings.json        # Application configuration
```

## ✅ Prerequisites

To run this application locally, you need:

- **[.NET 9.0 SDK](https://dotnet.microsoft.com/en-us/download/dotnet/9.0)** (or later)
- **Visual Studio 2022** (v17.8+) OR **VS Code** (with C# Dev Kit)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd "Multi-Env in Github/App"
```

### 2. Restore Dependencies

Navigate to the project directory and restore NuGet packages:

```bash
cd HelloWorldApp.web
dotnet restore
```

### 3. Run Locally

Start the application:

```bash
dotnet run
```

Access the app in your browser at:
- `http://localhost:5000`
- `https://localhost:5001`

## 🛠️ Building & Testing

### Build for Release

To generate the deployment artifacts locally:

```bash
dotnet publish -c Release -o ./publish
```

This commands creates a `publish` folder containing the compiled DLLs and web.config, ready for Azure App Service deployment.

## 🚢 Deployment

This application is designed to be deployed via the **Azure DevOps Pipeline** defined in the companion infrastructure repository.

### Pipeline Integration

The pipeline performs the following steps:
1.  **Build**: Compiles the .NET code
2.  **Publish**: Zips the application artifacts
3.  **Deploy**: Pushes the zip file to the target Azure App Service slot (Dev/Test/Prod)

> [!NOTE]
> Ensure the target Azure App Service is configured with **.NET 9** runtime stack.

---

**Last Updated**: February 2026
