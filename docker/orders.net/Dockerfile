FROM microsoft/dotnet:latest

ARG source  
RUN echo "source: $source"  
WORKDIR /app  
COPY ${source:-/} .  

COPY . /app

WORKDIR /app

RUN ["dotnet", "restore"]
RUN apt-get update && apt-get install -y tcpdump jq
RUN ["dotnet", "build"]

EXPOSE 80/tcp

ENTRYPOINT ["dotnet", "run", "--server.urls", "http://0.0.0.0:80"]
