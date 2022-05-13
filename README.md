## OpenMRS HIE dockerized setup
This project contains the dockerized HIE setup for OpenMRS .
see [PLIR archtecture](https://wiki.openmrs.org/display/projects/Architectural+Design+Approach+to+support+an+integrated+approach+to+patient-level+indicator+reporting+for+OpenMRS)

Ensure you have Docker and Docker compose installed locally.
See Docker Installation Instructions for your environment.  If running on Linux, check https://docs.docker.com/compose/install/ to install docker compose.

To run the project , follow the instructions below .
1. Clone the repository locally

        git clone https://github.com/openmrs/openmrs-plir-dockerized-setup.git

2. Move to the project root directory and spin up the pre-configured OpenMRS ,OpenHIM ,Hapi-Fhir and the streaming-binlog pipeline instances . 

       ./run.sh

3. You should be able to acces the OpenMRS ,OpenHIM and Hapi-Fhir instances  at the following urls



| Instance  |     URL       | credentials (user : password)|
|---------- |:-------------:|------:                       |
| OpenMRS   |http://localhost:8080/openmrs| admin : Admin123 |
| OpenHIM   |    http://localhost:9000  |  root@openhim.org : openhim-password |
| Hapi FHir | http://localhost:8090 |    hapi : hapi123| 


   Note:

 * The Openhim instance is pre-configured with the necesary meta-data

  > Wait for the **plir-streaming-pipeline** container to start running before adding any data into OpenMRS. The running Pipeline will then listen to any  data changes  added in to OpenMRS and route them to the FHIR server through OpenHIM.

   


 7. To remove and clean out all created containers and volumes, run

          ./stop.sh




