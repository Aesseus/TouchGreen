# TouchGreen Mobile Application

## Project Overview
TouchGreen is a gamified mobile application designed to help users monitor and reduce their carbon footprint through interactive challenges and a virtual ecosystem. The app combines real-world sustainability actions with virtual game elements to create an engaging experience for environmental consciousness.

## Technology Stack
- **.NET MAUI**: Cross-platform framework for mobile and desktop applications
- **C#**: Primary programming language
- **MVVM Architecture**: Design pattern for clear separation of concerns
- **Unity**: Game engine for the virtual ecosystem component
- Additional stack components will be updated as the backend architecture is defined

## Project Structure and Naming Conventions

### Solution Structure
```
TouchGreen.sln
├── TouchGreen.Core/               # Core business logic and models
├── TouchGreen.Services/           # Service implementations
├── TouchGreen.ViewModels/         # MVVM ViewModels
├── TouchGreen.Views/              # MAUI Views
├── TouchGreen.Game/               # Unity game integration
└── TouchGreen.Tests/              # Unit and integration tests
```

### Naming Conventions

#### General Rules
- Use PascalCase for class names, public properties, and methods
- Use camelCase for private fields and local variables
- Use UPPERCASE for constants
- Prefix interfaces with 'I'
- Avoid abbreviations in names
- Use meaningful and descriptive names

#### Examples
```csharp
public class UserProfileViewModel    // Class names in PascalCase
{
    private readonly IUserService _userService;    // Private fields with underscore prefix
    
    public string FirstName { get; set; }         // Public properties in PascalCase
    
    private void calculateFootprint() { }         // Private methods in camelCase
    
    public async Task UpdateProfileAsync() { }    // Public methods in PascalCase
}
```

## MVVM Implementation Guidelines

### MVVM Community Toolkit Integration
We use the .NET Community Toolkit MVVM package for implementing the MVVM pattern. This provides a robust and efficient way to handle property changes, commands, and messaging.

```xml
<PackageReference Include="CommunityToolkit.Mvvm" Version="8.2.2" />
```

### View Models
- All ViewModels should inherit from `ObservableObject`
- Use source generators with attributes for property and command generation
- Implement observable properties using `[ObservableProperty]` attribute
- Use `[RelayCommand]` for commands
- Avoid code-behind in views

Example ViewModel:
```csharp
using CommunityToolkit.Mvvm.ComponentModel;
using CommunityToolkit.Mvvm.Input;

namespace TouchGreen.ViewModels;

public partial class UserProfileViewModel : ObservableObject
{
    [ObservableProperty]
    private string firstName;

    [ObservableProperty]
    private string lastName;

    [ObservableProperty]
    private double carbonFootprint;

    [RelayCommand]
    private async Task UpdateProfileAsync()
    {
        try
        {
            // Implementation
        }
        catch (Exception ex)
        {
            // Error handling
        }
    }
}
```

### Services
- Use dependency injection
- Interface-based design
- Implement service registration in `MauiProgram.cs`

```csharp
public static class MauiProgram
{
    public static MauiApp CreateMauiApp()
    {
        var builder = MauiApp.CreateBuilder();
        
        // Register services
        builder.Services.AddSingleton<IUserService, UserService>();
        builder.Services.AddSingleton<ICarbonCalculatorService, CarbonCalculatorService>();
        
        // Register views and viewmodels
        builder.Services.AddTransient<UserProfilePage>();
        builder.Services.AddTransient<UserProfileViewModel>();
        
        return builder.Build();
    }
}
```

## Git Workflow

### Branch Naming Convention
- Feature branches: `feature/description`
- Bug fixes: `bugfix/description`
- Releases: `release/version`
- Hotfixes: `hotfix/description`

### Commit Message Format
```
<type>(<scope>): <description>

[optional body]

[optional footer]
```

Types:
- feat: New feature
- fix: Bug fix
- docs: Documentation changes
- style: Code style changes
- refactor: Code refactoring
- test: Adding tests
- chore: Maintenance

Example:
```
feat(profile): add carbon footprint calculator

- Implements daily emission tracking
- Adds visualization component
- Integrates with game rewards system

Resolves: #123
```

### Pull Request Process
1. Create feature branch from `develop`
2. Implement changes
3. Submit PR to `develop`
4. Require at least one code review
5. Pass all automated tests
6. Merge using squash and merge strategy

## Code Quality Standards
- Use nullable reference types
- Implement unit tests for business logic
- Maintain test coverage above 80%
- Follow SOLID principles
- Use async/await for asynchronous operations
- Implement proper exception handling
- Use logging for debugging and monitoring

## Documentation
- XML documentation for public APIs
- Keep README updated
- Document architectural decisions
- Include inline comments for complex logic

---
*Note: This README will be updated with additional sections for backend architecture and infrastructure as they are defined.*
