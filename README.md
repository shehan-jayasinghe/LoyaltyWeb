# LoyaltyWeb

A .NET 8 ASP.NET Core MVC application for a loyalty-oriented web experience.

## Overview

The solution is structured as a multi-project .NET application with a web layer and supporting model, data-access, and utility projects. The web application uses MVC controllers and views, serves static assets, and configures HTTPS redirection and production exception handling.

## Architecture

```text
Browser
   |
   v
ASP.NET Core MVC
   |
   +--> Controllers
   +--> Models
   +--> Views
   |
   +--> Loyalty.DataAccess
   +--> Loyalty.Utility
   |
   v
Application / Data Services
```

## Solution Structure

- `LoyaltyWeb/` — ASP.NET Core MVC web application.
- `Loyalty.DataAccess/` — data-access layer.
- `Loyalty.Models/` — shared application/domain models.
- `Loyalty.Utility/` — shared utility functionality.
- `LoyaltyWeb.sln` — solution file.

## Web Application

The web project targets .NET 8 and enables nullable reference types and implicit usings. The application registers MVC controllers with views and maps the conventional route:

```text
/{controller=Home}/{action=Index}/{id?}
```

The HTTP pipeline includes:

- HTTPS redirection
- Static-file serving
- Routing
- Authorization
- Production exception handling
- HSTS outside development

## Development

Restore and build the solution:

```bash
dotnet restore
dotnet build
```

Run the web application:

```bash
dotnet run --project LoyaltyWeb
```

## Security

Production traffic is configured for HTTPS redirection and HSTS. Keep database credentials, API keys, and other environment-specific secrets outside source control.

## Project Status

The repository provides an ASP.NET Core MVC foundation with separated models, data-access, utility, and web concerns.
