FROM microsoft/dotnet:1.1-sdk
WORKDIR /home/hackathon/cpr/cpr/cpr

# copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# copy and build everything else
COPY . ./
RUN dotnet publish -c Release -o out

ENV ASPNETCORE_URLS http://*:5003
EXPOSE 5003

ENTRYPOINT ["dotnet", "out/cpr.dll"]
