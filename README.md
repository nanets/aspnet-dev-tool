# ASP.NET Dev Tool

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![.NET](https://img.shields.io/badge/.NET-9.0-blue.svg)](https://dotnet.microsoft.com/)
[![Build Status](https://img.shields.io/github/actions/workflow/status/nanets/aspnet-dev-tool/build.yml)](https://github.com/nanets/aspnet-dev-tool/actions)
[![GitHub issues](https://img.shields.io/github/issues/nanets/aspnet-dev-tool)](https://github.com/nanets/aspnet-dev-tool/issues)
[![GitHub stars](https://img.shields.io/github/stars/nanets/aspnet-dev-tool)](https://github.com/nanets/aspnet-dev-tool/stargazers)

A powerful .NET WPF application designed for advanced ASP.NET development server management and mobile testing. Built to streamline your development workflow with comprehensive project analysis, robust server lifecycle management, and seamless mobile device testing capabilities.

**Developed by Knull**

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Architecture](#architecture)
- [How It Works](#how-it-works)
- [Installation & Setup](#installation--setup)
- [Usage Guide](#usage-guide)
- [Supported Project Types](#supported-project-types)
- [Development](#development)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [License](#license)
- [About the Developer](#about-the-developer)
- [Support](#support)
- [Acknowledgments](#acknowledgments)

## Overview

ASP.NET Dev Tool is a comprehensive desktop application built with WPF that empowers developers to efficiently manage ASP.NET development servers. Beyond basic project analysis and local server management, it provides advanced features including mobile testing via QR codes, network access configuration, and robust process lifecycle management to prevent common development issues like port conflicts and orphaned processes.

## Features

### 🔍 **Project Detection & Analysis**

- Validates if a directory contains a valid ASP.NET project
- Supports both modern ASP.NET Core and legacy ASP.NET Framework projects
- Analyzes project structure and configuration files

### 🚀 **Advanced Server Management**

- Start and stop ASP.NET projects with comprehensive process cleanup
- Real-time server status monitoring and uptime tracking
- Intelligent port management with conflict resolution
- Multi-layer process termination to prevent orphaned processes
- Network binding configuration for mobile device access
- Integrated console output and logging with color-coded status

### 📱 **Mobile Testing & QR Code Integration**

- Generate QR codes for instant mobile device access
- Network connectivity testing and diagnostics
- Cross-device testing workflow automation
- Mobile-friendly server configuration

### 📊 **Project Type Identification**

- **Modern ASP.NET Core Projects:**

  - Web API
  - MVC Application
  - Blazor Server App
  - Blazor WebAssembly App
  - Web App
  - Minimal API
  - Razor Pages
  - SignalR
  - gRPC Service

- **Legacy ASP.NET Framework Projects:**
  - Web Forms
  - Web API
  - MVC

### 📈 **Detailed Analysis**

- Framework version detection
- Target framework identification
- Dependency analysis
- NuGet package listing
- Project structure analysis (Controllers, Views, Pages, Components)
- Configuration file detection (Startup.cs, Program.cs, Web.config, appsettings.json)
- Project size and file count
- Last modified date
- Error and warning reporting

### 🎨 **User Interface & Management**

- Clean, modern WPF interface
- Folder selection dialog
- Real-time project analysis
- Server control panel (Start/Stop/Restart)
- Live server logs and output monitoring
- Detailed project information display
- Color-coded status indicators (Analysis + Server Status)
- Issue reporting with error/warning counts
- Browser integration for quick testing
- **System Tray Integration**: Minimize to tray with context menu (Show/Kill Dotnet/Exit)

## Architecture

### 🏗️ **Project Structure**

```
AspNetDevTool.WPF/
├── Models/
│   ├── ProjectInfo.cs          # Project information model
│   ├── ProjectType.cs          # Project type enumeration
│   └── ServerStatus.cs         # Server status and monitoring
├── Services/
│   ├── IProjectAnalyzer.cs     # Analysis service interface
│   └── ProjectAnalyzer.cs      # Implementation of analysis logic
├── ViewModels/
│   └── MainViewModel.cs        # MVVM pattern with server management
├── MainWindow.xaml             # Main application window
├── MainWindow.xaml.cs          # Main window code-behind
├── App.xaml                    # Application configuration
└── App.xaml.cs                 # Application startup logic
```

### 🔧 **Technologies Used**

- **.NET 9.0** - Latest .NET runtime
- **WPF (Windows Presentation Foundation)** - Modern desktop UI framework
- **MVVM Pattern** - Model-View-ViewModel architecture
- **QRCoder Library** - QR code generation for mobile access
- **Advanced Process Management** - Comprehensive server lifecycle control
- **Network Programming** - Socket-based connectivity testing
- **Real-time Monitoring** - Live server output capture and status tracking

## How It Works

### 1. **Project Analysis**

- User selects a directory using the folder browser dialog
- Application scans and analyzes the selected directory
- Validates project structure and determines project type

### 2. **Server Management**

- Once a valid project is detected, server controls become available
- Start/Stop/Restart buttons for local development server
- Automatic port detection or manual configuration
- Real-time monitoring of server status and output

### 3. **Mobile Testing Workflow**

- Enable "Allow Network Access" to bind server to all network interfaces
- Click "📱 Mobile Access QR" to generate QR code for the server URL
- Scan QR code with mobile device to instantly access your development server
- Test responsive design and mobile functionality in real-time

### 4. **Advanced Development Workflow**

- Integrated browser launch for quick testing
- Live log monitoring with comprehensive error tracking
- Quick project switching and management
- Intelligent server restart with port conflict resolution
- Network connectivity diagnostics and troubleshooting

## Installation & Setup

### Prerequisites

- Windows 10/11
- .NET 9.0 Runtime or later
- Visual Studio 2022 (for development)

### Building from Source

1. Clone the repository
2. Open `AspNetDevTool.sln` in Visual Studio
3. Restore NuGet packages (including QRCoder)
4. Build the solution (Ctrl+Shift+B)
5. Run the application (F5)

### Command Line Build

```powershell
# Restore dependencies
dotnet restore

# Build the solution
dotnet build

# Run the application
dotnet run --project AspNetDevTool.WPF
```

## Usage Guide

### Basic Usage

1. Launch ASP.NET Dev Tool
2. Click "Browse" button to select your ASP.NET project directory
3. Click "Analyze" to examine the project structure and configuration
4. Review the detailed analysis results in the project information panel
5. Configure server settings (port, HTTPS, network access)
6. Use "Start Server" to launch the development server with enhanced process management
7. Monitor server status, uptime, and logs in real-time
8. Enable "📱 Allow Network Access" for mobile device testing
9. Click "📱 Mobile Access QR" to generate QR code for instant mobile access
10. Click "Open Browser" to test your application locally
11. **System Tray**: Close the window to minimize to tray - right-click tray icon for options

### System Tray Usage

The application features system tray integration for better workflow:

- **Minimize to Tray**: Closing the main window minimizes to system tray instead of exiting
- **Tray Icon**: Shows application status in Windows system tray
- **Context Menu Options**:
  - **Show**: Restore the main application window
  - **Kill Dotnet**: Terminate all running development servers
  - **Exit**: Properly close the application and clean up all processes
- **Double-click**: Double-click tray icon to quickly show the application

#### ✅ **Valid Project**

- Green indicator showing "Valid ASP.NET Project"
- Project type clearly identified
- Framework version displayed
- Characteristics and features listed

#### ❌ **Invalid Project**

- Red indicator showing "Invalid Project"
- Error messages explaining why validation failed
- Suggestions for what might be missing

#### ⚠️ **Warnings**

- Yellow indicators for non-critical issues
- Compatibility warnings
- Deprecated feature notifications

## Supported Project Types

### Modern ASP.NET Core Projects

| Type              | Description            | Key Identifiers                 |
| ----------------- | ---------------------- | ------------------------------- |
| **Web API**       | REST API services      | Controllers, API routing        |
| **MVC App**       | Model-View-Controller  | Controllers, Views, Models      |
| **Blazor Server** | Server-side Blazor     | Blazor components, SignalR      |
| **Blazor WASM**   | Client-side Blazor     | WebAssembly, static files       |
| **Minimal API**   | Lightweight API        | Program.cs with minimal hosting |
| **Razor Pages**   | Page-focused framework | Pages folder, .cshtml files     |

### Legacy ASP.NET Framework Projects

| Type          | Description       | Key Identifiers           |
| ------------- | ----------------- | ------------------------- |
| **Web Forms** | Server controls   | .aspx pages, Web.config   |
| **Web API**   | REST API (legacy) | ApiController, Web.config |
| **MVC**       | MVC (legacy)      | Controllers, Global.asax  |

## Development

### Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

### Code Style

- Follow C# coding conventions
- Use meaningful variable and method names
- Add XML documentation for public APIs
- Implement proper error handling

### Testing

```powershell
# Run unit tests
dotnet test

# Run with coverage
dotnet test --collect:"XPlat Code Coverage"
```

## Troubleshooting

### Common Issues

#### "Project not recognized"

- Ensure the directory contains a valid project file (.csproj, .vbproj, .fsproj)
- Check that the project file is not corrupted
- Verify file permissions

#### "Port already in use" errors

- ASP.NET Dev Tool automatically handles port conflicts with multi-layer cleanup
- The application terminates orphaned processes using the target port
- If issues persist, manually check for processes using `netstat -ano | findstr :PORT`

#### "QR code not working" for mobile access

- Ensure "Allow Network Access" is enabled
- Verify your device is on the same network
- Check Windows Firewall settings for the application
- Use the network connectivity test feature

### Logging

- Application logs are written to the console output panel
- Server output is captured and displayed in real-time with color coding
- Process management actions are logged with detailed status information

## Roadmap

### Upcoming Features

- [x] System tray integration with process management
- [x] Enhanced installer with version detection
- [ ] Multi-project workspace management
- [ ] Custom environment variable configuration
- [ ] Database connection testing and management
- [ ] Export analysis results and server logs
- [ ] Project health scoring and recommendations
- [ ] Hot reload and live debugging integration
- [ ] Docker container support and management
- [ ] Integration with Visual Studio and VS Code
- [ ] Command-line interface for CI/CD automation
- [ ] Plugin architecture for custom server configurations

### Version History

- **v2.1.5** - System tray integration, enhanced installer with version detection, improved process management
- **v2.1.5** - Added system tray functionality and enhanced installer with version checking
- **v1.2.0** - Enhanced server lifecycle management and process cleanup
- **v1.1.0** - Added QR code mobile testing and network access features
- **v1.0.0** - Initial release with project analysis and basic server management

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## About the Developer

**ASP.NET Dev Tool** is developed by **Knull** - a passionate developer focused on creating tools that enhance the development experience and streamline workflow automation.

## Support

For issues, questions, or feature requests:

- Create an issue on GitHub
- Email: knullnanets@gmail.com

## Acknowledgments

- Microsoft ASP.NET team for comprehensive framework documentation
- QRCoder library contributors for excellent QR code generation
- .NET WPF community for UI/UX patterns and best practices
- Beta testers who provided valuable feedback on mobile testing features

---

**🚀 Empowering ASP.NET developers with advanced server management and mobile testing capabilities**  
**💻 Developed by Knull with ❤️ for the developer community**
