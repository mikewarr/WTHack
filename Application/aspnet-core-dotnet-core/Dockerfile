FROM microsoft/aspnetcore-build:1.1 AS build
WORKDIR /app

# Copy the published web app
COPY . /app
RUN dotnet restore
# build
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/aspnetcore:1.1
WORKDIR /app
COPY --from=build /app/out .
# Run command
ENTRYPOINT ["dotnet", "aspnet-core-dotnet-core.dll"]

