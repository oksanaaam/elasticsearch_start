# Connecting Jupyter Notebook to Elasticsearch and Inserting OpenFlights Data

This guide walks you through the process of connecting a Jupyter Notebook to an Elasticsearch instance running in Docker and inserting airport data from the OpenFlights dataset into Elasticsearch.

## Prerequisites

- Docker: Ensure that Docker is installed on your local machine.
- Python: Make sure you have Python installed, along with the elasticsearch and elasticsearch-dsl Python libraries.

## Steps


1. Pull Elasticsearch Docker image: Run the following command to fetch the Elasticsearch Docker image (replace `<version>` with the desired version, e.g., "7.14.0"):`docker pull docker.elastic.co/elasticsearch/elasticsearch:7.14.0`


2. Run Elasticsearch in Docker: Create and start a Docker container with Elasticsearch, exposing ports 9200 and 9300:

`docker run -d --name elasticsearch -p 9200:9200 -p 9300:9300 docker.elastic.co/`

![elastic_connection.png](img%20for%20README.md%2Felastic_connection.png)

On http://localhost:9200/ you will see:

![localhost9200.png](img%20for%20README.md%2Flocalhost9200.png)


Run Kibana in Docker: Create and start a Docker container with Kibana, exposing ports 5601:

`docker run -d --name kibana --net my_network -p 5601:5601 docker.elastic.co/kibana/kibana:7.14.0`

After that, insert data and make the opportunity to refresh the index to make the data available for search immediately.

On  http://localhost:5601/ you can see structured info:

![kibana.png](img%20for%20README.md%2Fkibana.png)


And the last thing, you could find info similar to your search through the terminal in Elasticsearch:

![find_info.png](img%20for%20README.md%2Ffind_info.png)
