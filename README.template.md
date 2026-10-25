# ${name}

Welcome to your new project generated with the Clean Architecture template!

## Getting Started

- Build the solution:
  ```sh
  dotnet build
  ```
- Run the application:
  ```sh
  dotnet run --project src/Your.ProjectName.Web
  ```
- Update the database (if using EF Core):
  ```sh
  dotnet ef database update -c AppDbContext -p src/Your.ProjectName.Infrastructure/Your.ProjectName.Infrastructure.csproj -s src/Your.ProjectName.Web/Your.ProjectName.Web.csproj
  ```

## Solution Structure

- **Core**: Domain entities, value objects, interfaces
- **UseCases**: Application logic, CQRS handlers
- **Infrastructure**: Data access, external services
- **Web**: API endpoints (FastEndpoints)

## Aspire AppHost

Restore and build the AppHost before running the distributed application:

```sh
dotnet build src/Clean.Architecture.AspireHost/Clean.Architecture.AspireHost.csproj
```

The SDK version is in the AppHost project; integration and testing package
versions are managed independently in `Directory.Packages.props`. Aspire CLI
generation supplies its SDK identity and resolves these packages from the
effective NuGet feeds. When custom feeds are needed, retain the CLI-generated
root `NuGet.config` and its inherited NuGet sources when moving this project.
Ordinary `dotnet new` generation uses stable Aspire defaults and the template's
original `nuget.config`.

For more details, see the documentation or visit the [Clean Architecture Template repository](https://github.com/ardalis/CleanArchitecture).
