# escape=`

FROM mcr.microsoft.com/windows/insider:10.0.19023.1

# Enable detection of running in a container
ENV DOTNET_RUNNING_IN_CONTAINER=true

# Ngen top of assembly graph to optimize a set of frequently used assemblies
RUN \Windows\Microsoft.NET\Framework64\v4.0.30319\ngen install "Microsoft.PowerShell.Utility.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" `
    && \Windows\Microsoft.NET\Framework\v4.0.30319\ngen install "Microsoft.PowerShell.Utility.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"
