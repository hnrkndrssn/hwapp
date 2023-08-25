FROM mcr.microsoft.com/dotnet/core/sdk:3.1

RUN apt-get update && \
    apt-get install -y \
        curl \
        groff \
        jq \
        less \
        python \
        python-pip \
        unzip \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN pip install awscli

# Install the AWS PowerShell command-line tools
RUN pwsh -Command Install-Module -Name AWSPowerShell.NetCore -Force

# Confirm that aws cli is on the path
RUN aws --version

# Confirm that Powershell is on the path
RUN pwsh --version

# Confirm that Bash is on the path
RUN bash --version

WORKDIR /src

CMD [ "/bin/bash" ]
