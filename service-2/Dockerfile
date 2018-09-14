FROM microsoft/dotnet:2.1-sdk AS build-env
WORKDIR /app

# Copy csproj and restore as distinct layers
COPY *.csproj ./
RUN dotnet restore

# Copy everything else and build
COPY . ./
RUN dotnet publish -c Release -o out

# Build runtime image
FROM microsoft/dotnet:aspnetcore-runtime
WORKDIR /app
EXPOSE 5002 5003
ENV ASPNETCORE_URLS=http://+:5003
COPY --from=build-env /app/out .
ENTRYPOINT ["dotnet", "service-2.dll"]