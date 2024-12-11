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
## Setting Up Version Control Ignores

When working with a hybrid Unity and .NET MAUI project, proper Git ignore configuration is crucial for maintaining a clean repository. We need to ignore build artifacts, local configurations, and temporary files from both environments.

### Creating the .gitignore File

Create the .gitignore file in your project root:

```bash
# Navigate to project root
cd TouchGreen

# Create .gitignore file
touch .gitignore
```

Add the following content to your .gitignore file:

```gitignore
# Unity Generated
[Ll]ibrary/
[Tt]emp/
[Oo]bj/
[Bb]uild/
[Bb]uilds/
[Ll]ogs/
[Uu]ser[Ss]ettings/
[Mm]emoryCaptures/

# Unity3D Generated Meta Files
*.pidb.meta
*.pdb.meta
*.mdb.meta

# Unity3D Generated File On Crash Reports
sysinfo.txt

# Builds
*.apk
*.aab
*.unitypackage
*.app

# Visual Studio / VS Code Generated
.vs/
.vscode/
*.csproj
*.unityproj
*.sln
*.suo
*.tmp
*.user
*.userprefs
*.pidb
*.booproj
*.svd
*.pdb
*.mdb
*.opendb
*.VC.db

# .NET MAUI Generated
bin/
obj/
[Bb]in/
[Oo]bj/
[Dd]ebug/
[Rr]elease/
x64/
x86/
[Aa][Rr][Mm]/
[Aa][Rr][Mm]64/
bld/
[Bb]in/
[Oo]bj/
[Ll]og/
[Ll]ogs/

# .NET MAUI Platform Specific
Resource.designer.cs
*.designer.cs
*.Designer.cs

# macOS
.DS_Store
.AppleDouble
.LSOverride
._*

# iOS Build
*.ipa
*.dSYM.zip
*.dSYM

# Android Build
*.apk
*.aab
*.ap_
*.dex

# IDE Specific Files
.idea/
*.swp
*.swo
.vs/
.vscode/
*.user
*.userosscache
*.sln.docstates

# Local Configuration
local.settings.json
appsettings.*.json
!appsettings.json

# NuGet
packages/
*.nupkg
# NuGet Symbol Packages
*.snupkg
# The packages folder can be ignored because of Package Restore
**/[Pp]ackages/*
# except build/, which is used as an MSBuild target.
!**/[Pp]ackages/build/

# Node.js Dependencies (if using any web components)
node_modules/
npm-debug.log
yarn-debug.log
yarn-error.log

# Unity Package Manager
/[Aa]ssets/[Pp]ackages
/[Aa]ssets/[Pp]ackages.meta

# Crashlytics Generated File
crashlytics-build.properties
```

### Applying the .gitignore

After creating the .gitignore file, if you've already committed any files that should be ignored:

```bash
# Remove tracked files that should be ignored
git rm -r --cached .
git add .
git commit -m "chore: update gitignore and remove tracked files

- Add comprehensive ignore rules for Unity and MAUI
- Remove previously tracked files that should be ignored
- Clean up repository from build artifacts"
```

### Testing Your .gitignore

To verify your .gitignore is working correctly:

```bash
# Check what files Git is tracking
git status

# See what files would be included in the next commit
git add -A -n
```

The output should not show any of the ignored file patterns listed in your .gitignore.

### Important Notes

1. Unity-specific considerations:
   - We ignore Library/ and Temp/ folders as they contain Unity's local cache
   - Meta files are crucial and should NOT be ignored (they're not in the ignore list)
   - Build outputs are ignored but build settings are tracked

2. .NET MAUI considerations:
   - bin/ and obj/ folders contain compiled outputs and should be ignored
   - Platform-specific generated files are ignored
   - Keep configuration templates but ignore local settings

3. IDE and OS-specific files:
   - Various IDE settings are ignored to avoid conflicts between team members
   - OS-specific files (like .DS_Store) are ignored
   - Editor and user-specific settings are ignored

Remember to commit the .gitignore file itself:

```bash
git add .gitignore
git commit -m "chore: add comprehensive gitignore

- Add Unity-specific ignore patterns
- Add .NET MAUI ignore patterns
- Include IDE and OS-specific ignores
- Document ignore file structure"
```

### Understanding Git Workflow

Our development process follows a structured Git workflow.:

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
