FROM mcr.microsoft.com/dotnet/core/sdk:2.2-stretch 

RUN mkdir /work/
WORKDIR /work/

COPY ./src/work.csproj /work/work.csproj
RUN dotnet restore

COPY ./src/ /work/
CMD ["dotnet", "run"]
