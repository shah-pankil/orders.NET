FROM microsoft/dotnet:latest

RUN ["dotnet", "restore"]
RUN apt-get update && apt-get install -y tcpdump jq

WORKDIR /app

RUN ["dotnet", "run"]
ONBUILD COPY . /app

RUN ["dotnet", "restore"]
RUN apt-get update && apt-get install -y tcpdump jq

EXPOSE 80/tcp

ENTRYPOINT ["dotnet", "run", "--server.urls", "http://0.0.0.0:80"]
