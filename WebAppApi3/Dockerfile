#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["WebAppApi3/WebAppApi3.csproj", "WebAppApi3/"]
RUN dotnet restore "WebAppApi3/WebAppApi3.csproj"
COPY . .
WORKDIR "/src/WebAppApi3"
RUN dotnet build "WebAppApi3.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "WebAppApi3.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "WebAppApi3.dll"]