# Data Ingestion

- Download the dataset from 'data\source\data.txt'
- Create an EC2 instance > docker container > mcr.microsoft.com/mssq    l/server:2002-latest
- Spin up the legacy MSSQL Server

docker run -e "ACCEPT_EULA=Y" -e  "MSSQL_SA_PASSWORD=FdeEnterprisePass123!" -p 1433:1433 --name legacy-mssql -d mcr.microsoft.com/mssql/server:2022-latest

 # docker commands
docker ps -a
docker images
docker stop <container id>
docker rm <container id>

# multiline in windows
docker run -e "ACCEPT_EULA=Y" ^
-e "MSSQL_SA_PASSWORD=FdeEnterprisePass123!" ^
-p 1433:1433 --name legacy-mssql ^
-d mcr.microsoft.com/mssql/server:2022-latest

# command with volume in EC2
docker run -v mssql_data:/var/opt/mssql
-e "ACCEPT_EULA=Y" \
-e "MSSQL_SA_PASSWORD=FdeEnterprisePass123!" \
-p 1433:1433 \
--name legacy-mssql \
-d mcr.microsoft.com/mssql/server:2022-latest

......After a docker run

install the req: > pip install -r requirements.txt
Update pip - > python.exe -m pip install --upgrade pip

