== Data Flow - Kubernetes with Spring Cloud


This project provides support for deploying streaming and task/batch data pipelines to Kubernetes.
Instead of building, maintaining, and shipping individual server-implementations, we have consolidated them into a single server, and all the supported libraries are bundled in it.

That would mean, as a user, you don't need to pick different JARs or Docker-images depending on what platform you want to run. 

The other notable benefit to this approach is the ability to configure the single-server with multiple platform backends. The same server can be configured against Local, "n" number of Cloud Foundry `org/space` combinations, and as well against "n" number of Kubernetes clusters and the associated `namespace`. At the time of stream-deployment or task-launches, you would be able to pick-and-choose the platform where you want to orchestrate the deployment. It would further simplify and promote CI/CD practices for data pipelines.

=== Building

Clone the repo and type 

----
$ ./mvnw clean install 
----

To build the docker image for the Data Flow Server

----
$ ./mvnw package docker:build -pl :server-kubernetes
----
