EpiData
=====================================
EpiData is an IoT Data Science Platform. It integrates IoT and Data Science capabilities in a lightweight and open-source framework. The EpiData platform enables development and deployment of machine learning and deep learning algorithms for smarter industrial solutions including energy management, smart manufacturing and building automation.

You can find out more about EpiData at https://epidata.io.


Installation and Launch
------------------------
- Docker Container:
The epidata-community docker image is available as a stand-alone package with all code and required components. To build and start a docker container, simply execute the command shown below (replacing 'epidata123' with a custom token):  
    - docker run -p 443:443 -it -e token=epidata123 epidataio/epidata-community:0.11.0

    Below are other useful docker commands:
    - Pull the docker image:
        - docker pull epidataio/epidata-community:0.11.0
    - List all docker containers:
        - docker ps -a
    - Stop a docker container:
        - docker stop <container_id>
    - Start a stopped docker container:
        - docker start <container_id>
    - Start epidata application on a running docker container:
        - docker exec -it <container_id> ./epidata-start.sh -p 443:443

- Installation Scripts:
One can also set up EpiData platform by following the installation and launch scripts available in epidata-install repository. We recommend cloning epidata-community repository to epidata folder within ubuntu user's home directory (/home/ubuntu).


Configuration
--------------
- Authentication:
Access to EpiData platform is managed via tokens and OAuth 2 authorization (with GitHub). The configuration settings for tokens are available in play/conf/application.conf, and OAuth 2 are available in play/conf/securesocial.conf. Authenticated users can be added to the system manually via Cassandra's CQL commands.

- Measurement Class:
EpiData platform can be configured to operate on 'sensor measurement' or 'automated test' data. To enable sensor measurement data, play's application.conf must set measurement-class to sensor_measurement. In addition, spark's spark-defaults.conf must set spark.epidata.measurementClass to sensor_measurement. To enable automated test data, play's application.conf must set measurement-class to automated_test. In addition, spark's spark-defaults.conf must set spark.epidata.measurementClass to automated_test.


Usage
------
After launch, EpiData platform is ready to ingest and process sensor data. To access ingestion scripts and Jupyter Notebook tutorial, you can visit https://<epidata_url>, where epidata_url is the url for the server hosting EpiData platform.


Resources
----------
EpiData community-edition is managed via this GitHub repository site. For enterprise support and services, please contact the EpiData Team via https://epidata.io.
