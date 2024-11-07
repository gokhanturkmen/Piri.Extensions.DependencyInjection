# Piri.Extensions.DependencyInjection

## Overview
Piri.Extensions.DependencyInjection is a .NET library that provides extensions for integrating the Piri Object Mapper with the .NET Dependency Injection framework. This package simplifies the configuration and usage of the Piri Object Mapper in your .NET applications.

## Features
- Seamless integration with .NET Dependency Injection
- Easy configuration of Piri Object Mapper
- Support for .NET 8

## Installation
You can install the package via NuGet Package Manager or the .NET CLI.

### NuGet Package Manager
```bash
Install-Package Piri.Extensions.DependencyInjection
```
### .NET CLI

```bash
dotnet add package Piri.Extensions.DependencyInjection
```
## Usage
To use the Piri Object Mapper with Dependency Injection, follow these steps:

1. **Configure Services:**
   In your `Program.cs` or wherever you configure your services, add the Piri Object Mapper services.
    ```csharp
    using Microsoft.Extensions.DependencyInjection;
    using Piri.Extensions.DependencyInjection;

    var builder = WebApplication.CreateBuilder(args);

    builder.Services.AddPiriMapper(options => {
        options.EnableDefaultMapping();
    });
    // Other service configurations
    var app = builder.Build();
    // Configure the HTTP request pipeline.
    await app.RunAsync();
    ```
2. **Inject and Use:**
   Inject the ```IMapper``` interface into your classes and use it as needed.
    ```csharp
    using Piri.Core;

    public class MyService {
        private readonly IMapper _mapper;
        public MyService(IMapper mapper)
        {
            _mapper = mapper;
        }

       public void MyMethod()
       {
           // Use the mapper
           var destination = _mapper.Map<DestinationType>(source);
       }
    }
    ```
## Contributing
Contributions are welcome! Please open an issue or submit a pull request on GitHub.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact
For any questions or feedback, please contact us at me@gturkmen.com.
