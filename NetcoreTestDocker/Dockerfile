FROM microsoft/dotnet:2.1-aspnetcore-runtime AS base
WORKDIR /app
EXPOSE 80

FROM microsoft/dotnet:2.1-sdk AS build
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
EXPOSE 5000
ENTRYPOINT ["dotnet", "NetcoreTestDocker.dll"]
