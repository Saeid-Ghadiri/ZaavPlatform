# ZaavApp.Admin

Admin panel for Zaavosh Platform built with Blazor WebAssembly.

## Technology Stack
- **Framework**: Blazor WebAssembly
- **Styling**: Bootstrap 5.3 RTL
- **Authentication**: JWT with Microsoft Identity
- **State Management**: Fluxor (optional)

## Features
- Multi-language support (fa-IR, en-US)
- Responsive design
- Integration with ZaavApp.Api
- Role-based access control
- Persian calendar support

## Project Structure
```
ZaavApp.Admin/
├── Pages/
├── Components/
├── Services/
├── Models/
├── Layouts/
├── wwwroot/
└── Program.cs
```

## Setup Instructions
```bash
# Install dependencies
dotnet restore

# Run development server
dotnet run

# Publish for production
dotnet publish -c Release
```