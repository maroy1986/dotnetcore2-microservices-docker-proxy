FROM microsoft/aspnetcore:2.0 AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/aspnetcore-build:2.0 AS build
WORKDIR /src
COPY NetcoreTestDocker/NetcoreTestDocker.csproj NetcoreTestDocker/
RUN dotnet restore NetcoreTestDocker/NetcoreTestDocker.csproj
COPY . .
WORKDIR /src/NetcoreTestDocker
RUN dotnet build NetcoreTestDocker.csproj -c Release -o /app

FROM build AS publish
RUN dotnet publish NetcoreTestDocker.csproj -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "NetcoreTestDocker.dll"]
