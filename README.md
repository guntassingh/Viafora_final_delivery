# Url Shortener

Link shortening service that can be used to turn fully qualified URLs into short code to be usedin links.

## Installation

Package manager 
```bash
[Docker](https://www.docker.com/) to install Docker.


1-ConfigServerApplication-0.0.1-SNAPSHOT.jar
2-EurekaServer-0.0.1-SNAPSHOT.jar
3-ZuulGatewayService-0.0.1-SNAPSHOT.jar
4-URLShortener-0.0.1-SNAPSHOT.jar

## Step

##############Create network in Docker##############
**************Run the command**************
Create docker network springapp

##############Run docker mysql image in network created above##############
docker container run --name mysqldb -p 3306:3306 --network springapp -e MYSQL_ROOT_PASSWORD=root123 -e MYSQL_DATABASE=urlshortner -e MYSQL_USER=root  -d mysql:8

##############Start ELK on Docker##############
Browse to ELK folder 
**************Run the command**************
docker-compose -f docker-compose-ELK.yml up

##############Start FileBeat on Host Machine(LINUX)##############

Install filebeat 

**************Run the command to install FileBeat**************
apt-get install apt-transport-https
apt update
apt install filebeat

**************Copy FileBeat configurations**************
Browse to FileBeat folder
Copy filebeat.yml to /etc/filebeat 

**************Start FileBeat Service**************
filebeat -e -c /etc/filebeat/filebeat.yml

##############Create Index in Kibana##############
Open link http://hostmachineip:5601 in a browser.
Click on Index Patterns
Click on Create index
Define Index Pattern as filebeat*
In the next page, click on @timestamp

##############Start Microservices in Docker##############
Browse to Viafora folder open in terminal.
**************Run the command**************
export IP=(`hostname -I | awk '{print $1}'`)
IP=$IP docker-compose -f docker-compose.yml up



## Usage

1- Spring boot 2.1.8.
2- Java 8
3- SSL Certificate

```Java
import service

UrlService.find('MmM3MT') # returns Url
UrlService.createShortURL('CreateLinkDTO') # returns LinkDTO
StatisticService.create('Statistic') # returns Statistic
StatisticService.getStatisticsSummary()  # returns StatisticsSummaryDTO
StatisticService.getStatisticsSummaryByCode() # returns StatisticsSummaryDTO
```

## Request 
[Redirect Url](https://localhost:8443/v1/MmM3MT/)   ->   Open new page     
[Create Url](https://localhost:8443/v1/url)  
Header -  token =1234       
body-
{
  "customerId": "1112",
  "url": "http://yahoo.com"
 }


## Contributing
Please make sure to update tests as appropriate.

## License
[Rsystem](https://www.rsystems.com/)