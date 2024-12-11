# TouchGreen Mobile Application

## Project Overview
TouchGreen is a gamified mobile application designed to help users monitor and reduce their carbon footprint through interactive challenges and a virtual ecosystem. The app combines real-world sustainability actions with virtual game elements to create an engaging experience for environmental consciousness.

## Technology Stack
* **.NET MAUI**: Cross-platform framework for mobile and desktop applications
* **C#**: Primary programming language
* **MVVM Architecture**: Design pattern for clear separation of concerns
* **Unity**: Game engine for the virtual ecosystem component
* **Community Toolkit MVVM**: Framework for implementing MVVM pattern
* Additional stack components will be updated as the backend architecture is defined

## Setting Up Your Development Environment

### Prerequisites Installation
Before we begin, you'll need to install the following tools:

1. Visual Studio 2022 (17.8 or later) with these workloads:
   - .NET MAUI development
   - .NET desktop development
   - Mobile development with .NET

2. Unity Hub and Unity Editor:
   - Install Unity Hub from [unity.com](https://unity.com/download)
   - Install Unity 2023.1 LTS or later
   - Add these modules during installation:
     - Android Build Support
     - iOS Build Support (if on Mac)
     - Visual Studio Code Editor

3. Git:
   - Download from [git-scm.com](https://git-scm.com)
   - Install with default settings

### Getting Started with TouchGreen

Let's set up your development environment step by step:

1. Clone the Repository:
   ```bash
   # Open your terminal and navigate to where you want the project
   cd your/preferred/directory
   
   # Clone the TouchGreen repository
   git clone https://github.com/Aesseus/TouchGreen.git
   
   # Navigate into the project
   cd TouchGreen
   ```

2. Set Up the .NET MAUI Project:
   ```bash
   # Restore NuGet packages
   dotnet restore
   
   # Install required .NET tools
   dotnet tool install -g dotnet-ef
   dotnet tool install -g dotnet-format
   ```

3. Configure Unity Project:
   - Open Unity Hub
   - Click "Add" and browse to the TouchGreen.Game folder
   - Open the project in Unity Editor
   - Install required packages via Package Manager:
     - Input System
     - TextMeshPro
     - Mobile Notifications

### Understanding Git Workflow

Our development process follows a structured Git workflow. Think of it like writing chapters in a book:

1. The Main Branch (`main`):
   - This is like our published book
   - Contains stable, production-ready code
   - Never commit directly to main

2. Feature Branches:
   ```bash
   # Create a new branch for your feature
   git checkout -b feature/your-feature-name
   
   # Make your changes and stage them
   git add .
   
   # Commit with a descriptive message
   git commit -m "feat: add carbon footprint calculator"
   
   # Push your changes
   git push origin feature/your-feature-name
   ```

3. Creating a Pull Request (PR):
   - Go to GitHub repository
   - Click "New Pull Request"
   - Select your feature branch
   - Write a descriptive title and description
   - Request reviews from team members

4. Code Review Process:
   - Reviewers will check your code
   - Address any feedback
   - Make requested changes
   - Update your PR
   - Once approved, merge into main

### Daily Development Workflow

1. Start Your Day:
   ```bash
   # Get latest changes
   git checkout main
   git pull origin main
   
   # Create your feature branch
   git checkout -b feature/todays-task
   ```

2. During Development:
   ```bash
   # Save your progress regularly
   git add .
   git commit -m "feat: describe your changes"
   
   # Keep your branch updated
   git fetch origin
   git rebase origin/main
   ```

3. When Ready to Share:
   ```bash
   # Push your changes
   git push origin feature/todays-task
   
   # Create PR on GitHub
   # Wait for code review
   # Address feedback if needed
   ```

### Best Practices for Commits

Write clear, descriptive commit messages:
```
feat(scope): brief description

- Detailed bullet point about change 1
- Detailed bullet point about change 2

Resolves: #123
```

Types of commits:
- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Formatting changes
- `refactor`: Code restructuring
- `test`: Adding tests
- `chore`: Maintenance

[Rest of the original content follows: MVVM Implementation, Code Standards, etc.]

## MVVM Implementation Guidelines
[Previous MVVM content as before]

## Code Quality Standards
[Previous standards content as before]

## Documentation
[Previous documentation section as before]

---

*Note: Backend infrastructure documentation, including API specifications, data models, and cloud service integration, will be provided in a future update. The current focus is on establishing the foundation for frontend implementation.*

Created: December 2024
Last Updated: December 2024
Version: 1.0
