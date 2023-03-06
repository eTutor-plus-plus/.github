# eTutor-plus-plus

An interactice, adaptive learning platform based on individual achievements of learning goals.
The system comprises different services, below is a simple architecture diagram highlighting the connections of the different services, which can all be found in the respective repositories of this organization.
Detailed information on the services can be found in the corresponding repository.


![image](https://user-images.githubusercontent.com/52571862/217237374-b29e54fa-6c3c-46d5-b2a3-78255925ebbc.png)
For further information, do not hesitate to contact kschuetz@dke.uni-linz.ac.at


## Continuous Integration

Every service of the system is equipped with a CI-Pipeline based on Github Actions. 
The pipelines generically build the services and a Docker image containing the application, and push those images to the Docker Hub [repository](https://hub.docker.com/repositories/etutorplusplus).
The pipelines are generally triggered by a push or a resolved pull request on the main/master branch of a service.
Images are tagged according to the schema etutorplusplus/<repository>:<branch>-<date>, where <repository> refers to the name of the respective services' repository, <branch> to the branch (so main/master), and <date> to the date on which the image has been created.

The [deploy repository](https://github.com/eTutor-plus-plus/local-deploy) contains the docker-compose configuration to deploy the whole system based on the automatically created images.
