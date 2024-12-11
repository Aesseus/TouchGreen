# TouchGreen Mobile Application

## Development Environment Setup

### Prerequisites
- Visual Studio 2022 17.8 or later (Windows) or Visual Studio for Mac 17.6 or later
- .NET 8.0 SDK
- Unity 2023.1 or later
- Git 2.40 or later
- Node.js 18.0 or later (for development tools)

### First-Time Setup
1. Clone the repository:
   ```bash
   git clone https://github.com/Aesseus/TouchGreen.git
   cd TouchGreen
   ```

2. Install required .NET tools:
   ```bash
   dotnet tool install -g dotnet-ef
   dotnet tool install -g dotnet-format
   ```

3. Install NuGet packages:
   ```bash
   dotnet restore
   ```

4. Set up Unity integration:
   - Open Unity Hub
   - Add the TouchGreen.Game project
   - Install required Unity packages through Package Manager
   - Configure Unity project settings for your platform

### Local Development Configuration
1. Environment Variables:
   Create a `local.settings.json` file in the project root:
   ```json
   {
     "LocalDevelopment": {
       "ApiBaseUrl": "http://localhost:5000",
       "EnableDebugFeatures": true,
       "UnityProjectPath": "./TouchGreen.Game"
     }
   }
   ```

2. Unity Configuration:
   - Set up Unity Editor preferences
   - Configure scene loading
   - Set up debugging preferences

### Development Workflow
1. Before starting new work:
   ```bash
   git checkout develop
   git pull origin develop
   git checkout -b feature/your-feature-name
   ```

2. During development:
   - Write tests for new features
   - Follow the coding standards in this document
   - Keep commits focused and well-documented
   - Regular builds and local testing

3. Code Quality Checks:
   ```bash
   dotnet format
   dotnet test
   ```

4. Preparing for Pull Request:
   - Update documentation if needed
   - Ensure all tests pass
   - Review changes for coding standards compliance
   - Create detailed PR description

### Troubleshooting
Common issues and solutions:
1. Unity-MAUI Integration Issues:
   - Verify Unity project settings
   - Check build configurations
   - Validate platform-specific settings

2. Build Problems:
   - Clear solution cache: `dotnet clean`
   - Restore packages: `dotnet restore`
   - Rebuild solution: `dotnet build`