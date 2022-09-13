# Requirements to perform the demo:

-   Docker
-   Postman

# Steps:

-   gh repo clone Engineering-Research-and-Development/iotagent-opcua
-   In the AGECONF folder, then:
-   Delete the `config.json` provided as example
-   Edit the config.properties replacing the value of the endpoint property with the url of the server you want to
    connect to (Car server = `opc.tcp://136.243.156.113:9092/UA/CarServer` or Boiler server =
    `opc.tcp://opcua.demo-this.com:51210/UA/SampleServer`)
-   Run: `docker-compose -f docker-compose-external-server.yml up`
-   If you're using the Car Server run the http requests in the postman collection in the following order:
    `Get CarSpeed, doAccelerate, Get CarSpeed, doStop, Get CarSpeed`

(Be aware! if you're using the public Car Server, if some of you is hitting the commands at the same time you cannot
obtain the expected result. It's only a demo server, the concurrency is not managed) If you mind to change the server
url Run: `docker-compose -f docker-compose-external-server.yml down -v` then repeat the first 3 steps.
