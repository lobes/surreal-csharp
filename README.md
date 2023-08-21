# SurrealC#

Can I?: 
- [x] get a surreal db up and running
- [ ] use nothing but C# and some queries to interact with it
- [ ] have all the database logic, schemas, stored procedures, (other usually cryptic and hidden db shit) visible from C# code
- [ ] make a minimal API intereact with the db
- [ ] get a Blazor frontend to go through the API for CRUD


### Get a SurrealDB up and running
---

**Windows:**
```ps
iwr https://windows.surrealdb.com -useb | iex
```

**Mac/Linux:**
```bash
curl -sSf https://install.surrealdb.com | sh
```

**Start the Server:**
```
surreal start -b 0.0.0.0:8082 -u root -p root --log full
```

### Interact with C#
---

.NET stuff:
```ps
dotnet new sln
dotnet new gitignore
dotnet new webapi -n surreal-api
dotnet sln add .\surreal-api\surreal-api.csproj
```

SurrealDB.NET nuget packages:

Make your `.csproj` file look like this.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">

  <PropertyGroup>
    <TargetFramework>net7.0</TargetFramework>
    <Nullable>enable</Nullable>
    <ImplicitUsings>enable</ImplicitUsings>
    <RootNamespace>surreal_api</RootNamespace>
  </PropertyGroup>

  <ItemGroup>
    <PackageReference Include="SurrealDB.Driver.Rpc" Version="1.0.8" />
    <PackageReference Include="SurrealDB.Driver.Rest" Version="1.0.8" />
 		<PackageReference Include="SurrealDB.Extensions.Service" Version="1.0.8" />
  </ItemGroup>

</Project>
```

TODO: go follow the example