# CQRS, MetiatR, and Clean Architecture
![Blue Pink Gradient Fashion Banner](https://github.com/ruhul000/CQRS-with-CleanArchitecture/assets/38735317/ef8f63f9-0ed5-4fd2-8e8c-d0b9987a055b)

This project exemplifies industry-standard best practices for implementing CQRS and Clean Architecture principles using C# and .NET technologies. It demonstrates the application of domain-driven development for logical separation within the CQRS design pattern while utilizing a single database.

### **TOOLS, TECHNOLOGIES AND DESIGN PATTERN USED** 
1. .Net 8
2. Rest API
3. Minimal API
4. CQRS Pattern
5. MediatR
6. Mapster
7. Result Pattern
8. Repository Pattern
10. API versioning
11. Fluent Validation
12. Open API - Swagger
13. Entity Framework Core
14. Dependency Injection (DI)
15. Clean Architecture

### **NUGET PACKAGES** 
1. MediatR
2. Mapster
3. Newtonsoft.Json
4. Serilog.AspNetCore
5. Microsoft.Extensions.Logging
6. Swashbuckle.AspNetCore
7. Microsoft.EntityFrameworkCore
8. Microsoft.EntityFrameworkCore.SqlServer
9. Microsoft.AspNetCore.Mvc.Versioning
10. Microsoft.AspNetCore.Mvc.Versioning.ApiExplorer
11. AutoMapper.Extensions.Microsoft.DependencyInjection
13. FluentValidation.DependencyInjectionExtensions

#### **PREREQUISITES**
Before running the project, ensure you have the following installed:

- .NET 8 SDK
- SQL Server 

#### **GETTING STARTED**
1. Clone the repository:
    <pre>git clone https://github.com/ruhul000/CQRS-with-CleanArchitecture.git</pre>
2. Set up your database connection string in **appsettings.json** or **appsettings.Development.json** files.
3. Navigate to the **SqlScript** directory and run **DataBaseScript.sql**, **Sproc.sql**, **Seed.sql**.
4. Navigate to the **API Projects** directory and run the project accordingly.

#### **PROJECT TREE**
<pre>
src
│   ePos.sln
│
├───Product.Command
│   ├───Application
│   │   ├───Application.csproj
│   │   ├───AssemblyReference.cs
│   │   │
│   │   ├───Abstractions
│   │   │   └───Messaging
│   │   │       ├───ICommand.cs
│   │   │       └───ICommandHandler.cs
│   │   └───Products
│   │       └───Commands
│   │           └───CreateProduct
│   │               ├───CreateProductCommand.cs
│   │               ├───CreateProductCommandHandler.cs
│   │               ├───CreateProductCommandValidator.cs
│   │               └───CreateProductRequest.cs
│   │
│   ├───Domain
│   │   ├───Domain.csproj
│   │   │
│   │   ├───Abstractions
│   │   │   ├───IProductCommandRepository.cs
│   │   │   ├───IProductQueryRepository.cs
│   │   │   └───IUnitOfWork.cs
│   │   │
│   │   ├───Entities
│   │   │   └───Product.cs
│   │   │
│   │   ├───Primitives
│   │   │   └───Entity.cs
│   │   │
│   │   └───Utilities
│   │       ├───Error.cs
│   │       └───Result.cs
│   │
│   ├───Infrastructure
│   │   ├───AssemblyReference.cs
│   │   ├───Infrastructure.csproj
│   │   ├───ProductReadDbContext.cs
│   │   ├───ProductWriteDbContext.cs
│   │   │
│   │   └───Repositories
│   │       ├───ProductCommandRepository.cs
│   │       ├───ProductQueryRepository.cs
│   │       └───UnitOfWork.cs
│   │
│   └───ProductAPI
│       ├───appsettings.Development.json
│       ├───appsettings.json
│       ├───ProductAPI.csproj
│       ├───ProductAPI.csproj.user
│       ├───ProductAPI.http
│       ├───Program.cs
│       │
│       ├───Controllers
│       │   └───ProductController.cs
│       │
│       ├───OpenAPI
│       │   └───ConfigureSwaggerOptions.cs
│       │
│       └───Properties
│           └───launchSettings.json
│
└───Product.Query
    ├───Applcation
    │   ├───Application.csproj
    │   ├───AssemblyReference.cs
    │   │
    │   ├───Abstractions
    │   │   └───Messaging
    │   │    	├───IQuery.cs
    │   │    	└───IQueryHandler.cs
    │   │
    │   └───Products
    │       └───Queries
    │           ├───ProductResponse.cs
    │           │
    │           ├───GetAllProducts
    │           │   ├───GetAllProductsQuery.cs
    │           │   └───GetAllProductsQueryHandler.cs
    │           │
    │           ├───GetProductById
    │           │   ├───GetProductByIdQuery.cs
    │           │   └───GetProductByIdQueryHandler.cs
    │           │
    │           └───GetProductByName
    │               ├───GetProductByNameQuery.cs
    │               └───GetProductByNameQueryHandler.cs
	│
	├───Domain
	│   ├───Domain.csproj
	│   │
	│   ├───Abstractions
	│   │   └───IProductQueryRepository.cs
	│   │
	│   ├───Entities
	│   │   └───Product.cs
	│   │
	│   ├───Primitives
	│   │   └───Entity.cs
	│   │
	│   └───Utilities
	│       ├───Error.cs
	│       └───Result.cs
    │
    ├───Infrastructure
    │   ├───AssemblyReference.cs
    │   ├───Infrastructure.csproj
    │   ├───ProductReadDbContext.cs
    │   │
    │   └───Repositories
    │       └───ProductQueryRepository.cs
    │
    └───ProductAPI
        ├───appsettings.Development.json
        ├───appsettings.json
        ├───ProductAPI.csproj
        ├───ProductAPI.csproj.user
        ├───ProductAPI.http
        ├───Program.cs
        │
        ├───Endpoints
        │   └───ProductEndpoints.cs
        │
        ├───OpenAPI
        │   └───ConfigureSwaggerOptions.cs
        │
        └───Properties
            └───launchSettings.json
</pre>
