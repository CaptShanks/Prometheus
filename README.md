# Prometheus
Integration of Prometheus and Alertmanger(On Docker Swarm Cluster)



To set up a cluster of prometheus and alert manager, you need the following files with you :-
1. Prometheus.yaml
      The prometheus.yaml file contains the basic configurations for the prometheus being set up. You have to pass the location of alertmanger in this file along with the rules file.

2. alertmanager.yaml
      The alertmanger.yaml file contains the basic configuration for the alertmanager and you have to set the receiver(notification endpoints) in this file under the receiver part.

3. error.rules
      The error.rules file is used to specify the rules which will be executed on the time-series data collected by prometheus. These rules then trigger alerts based on the settings provided.

      You can provide all the PromQL expressions in this file and later use those expressions in the ALERTS part of the file. You have to provide the labels in the function as well so that the corresponding receiver can be invoked based on the type of alert being triggered.

4. Docker images of alertmanger and prometheus

Follow the below steps to set up the cluster:

1. Pull the docker image for prometheus and then copy the prometheus.yaml file to the container and create a new image.
2. Pull the alertmanger image from docker hub and pass the alertmanager.yaml file to the container and create a new image.
3. Push both the newly created images to DockerHub
4. Spin a docker swarm cluster (This demo is for docker swarm)
5  Run the compose.yaml file on the master.
