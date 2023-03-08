ARG WINDOWS_VERSION
FROM mcr.microsoft.com/dotnet/framework/sdk:4.8-windowsservercore-$WINDOWS_VERSION AS build
WORKDIR /app

ARG TargetFramework

# copy csproj and restore as distinct layers
COPY *.csproj .
RUN dotnet restore

# copy and build everything else
COPY . .
WORKDIR /app
RUN dotnet publish -c Release -o out --no-restore


# Define the image name that you want to use for testing here
FROM mcr.microsoft.com/windows/servercore:$WINDOWS_VERSION AS runtime
WORKDIR /app
COPY --from=build /app/out ./
ENTRYPOINT ["dotnetapp.exe"]
