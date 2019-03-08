# Latest Version of Common Tags

The following tags are the latest stable versions of the most commonly used images. The complete set of tags is listed further down.

- [`dotnetapp`](https://github.com/Microsoft/dotnet-framework-docker/blob/master/samples/dotnetapp/Dockerfile)
- [`aspnetapp`](https://github.com/Microsoft/dotnet-framework-docker/blob/master/samples/aspnetapp/Dockerfile)
- [`wcfservice`](https://github.com/Microsoft/dotnet-framework-docker/blob/master/samples/wcfapp/Dockerfile.web)
- [`wcfclient`](https://github.com/Microsoft/dotnet-framework-docker/blob/master/samples/wcfapp/Dockerfile.client)

The [.NET Framework Docker samples](https://github.com/Microsoft/dotnet-framework-docker/blob/master/samples/README.md) show various ways to use .NET Framework and Docker together. See [Building Docker Images for .NET Framework Applications](https://docs.microsoft.com/dotnet/framework/docker/) to learn more.

Watch [dotnet/announcements](https://github.com/dotnet/announcements/labels/Docker) for Docker-related .NET announcements.

## Container sample: Run a simple application

Type the following command to run a sample console application with Docker:

```console
docker run --rm microsoft/dotnet-framework-samples
```

## Container sample: Run a web application

Type the following command to run a sample web application with Docker:

```console
docker run -it --rm -p 8000:80 --name aspnet_sample microsoft/dotnet-framework-samples:aspnetapp
```

After the application starts, navigate to `http://localhost:8000` in your web browser. You need to navigate to the application via IP address instead of `localhost` for earlier Windows versions, which is demonstrated in [View the ASP.NET app in a running container on Windows](https://github.com/microsoft/dotnet-framework-docker/blob/master/samples/aspnetapp/README.md#view-the-aspnet-app-in-a-running-container-on-windows).

## Container sample: Run WCF service and client applications

Type the following command to run a sample WCF service application with Docker:

```console
docker run -it --rm --name wcfservice_sample microsoft/dotnet-framework-samples:wcfservie
```
After the container starts, find the IP address of the container instance:
```console
docker inspect --format="{{.NetworkSettings.Networks.nat.IPAddress}}" wcfservice_sample
172.26.236.119
```
Type the following Docker command to start a WCF client container, set environment variable HOST to the IP address of the wcfservice_sample container:
```console
docker run --name wcfclient_sample --rm -it -e HOST=172.26.236.119 microsoft/dotnet-framework-samples:wcfclient
```

# Full Tag Listing

## Windows Server 2019 amd64 tags

- [`dotnetapp-windowsservercore-ltsc2019`, `dotnetapp`, `latest` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/dotnetapp/Dockerfile)
- [`aspnetapp-windowsservercore-ltsc2019`, `aspnetapp` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)
- [`wcfservice-windowsservercore-ltsc2019`, `wcfservice` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.web)
- [`wcfclient-windowsservercore-ltsc2019`, `wcfclient` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.client)

## Windows Server, version 1803 amd64 tags

- [`dotnetapp-windowsservercore-1803`, `dotnetapp`, `latest` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/dotnetapp/Dockerfile)
- [`aspnetapp-windowsservercore-1803`, `aspnetapp` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)
- [`wcfservice-windowsservercore-1803`, `wcfservice` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.web)
- [`wcfclient-windowsservercore-1803`, `wcfclient` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.client)

## Windows Server, version 1709 amd64 tags

- [`dotnetapp-windowsservercore-1709`, `dotnetapp`, `latest` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/dotnetapp/Dockerfile)
- [`aspnetapp-windowsservercore-1709`, `aspnetapp` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)
- [`wcfservice-windowsservercore-1709`, `wcfservice` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.web)
- [`wcfclient-windowsservercore-1709`, `wcfclient` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.client)

## Windows Server 2016 amd64 tags

- [`dotnetapp-windowsservercore-ltsc2016`, `dotnetapp`, `latest` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/dotnetapp/Dockerfile)
- [`aspnetapp-windowsservercore-ltsc2016`, `aspnetapp` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/aspnetapp/Dockerfile)
- [`wcfservice-windowsservercore-ltsc2016`, `wcfservice` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.web)
- [`wcfclient-windowsservercore-ltsc2016`, `wcfclient` (*Dockerfile*)](https://github.com/dotnet/dotnet-docker/blob/master/samples/wcfapp/Dockerfile.client)

# Support

See the [.NET Framework Lifecycle FAQ](https://support.microsoft.com/en-us/help/17455/lifecycle-faq-net-framework)

# Feedback

* [File a .NET Framework Docker issue](https://github.com/microsoft/dotnet-framework-docker/issues)
* [Report a .NET Framework problem](https://developercommunity.visualstudio.com/spaces/61/index.html)
* [Ask on Stack Overflow](https://stackoverflow.com/questions/tagged/.net)
* [Contact Microsoft Support](https://support.microsoft.com/contactus/)

# License

* [.NET Framework and Windows Server Core license](https://hub.docker.com/_/microsoft-windows-servercore/)
* [Pricing and licensing for Windows Server 2019](https://www.microsoft.com/en-us/cloud-platform/windows-server-pricing)