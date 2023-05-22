# Monitoring Solution with Prometheus, Grafana, and ELK Stack

This project demonstrates the implementation of a robust monitoring solution using Prometheus, Grafana, and the ELK stack (Elasticsearch, Logstash, Kibana). It collects, analyzes, and visualizes application logs and metrics.

## Prerequisites

- Docker: Install Docker from the official website (https://www.docker.com/get-started).

## Getting Started

1. Clone this repository and navigate to the project directory.

2. Set up Prometheus and Grafana:

    ```bash
    # Build Prometheus Docker image
    docker build -t my-prometheus .

    # Run Prometheus container
    docker run -p 9090:9090 --name prometheus my-prometheus
    ```

    Access Prometheus in your browser by visiting `http://localhost:9090`.

    - Download and install Grafana from the official Grafana website (https://grafana.com/get).
    - Open Grafana in your browser by visiting `http://localhost:3000`.
    - Log in using the default username and password (admin/admin). Change the password after logging in.

3. Set up the ELK Stack:

    ```bash
    # Start the ELK stack containers
    docker-compose up -d
    ```

    Access Kibana in your browser by visiting `http://localhost:5601`.

4. Integration with Sample Application:

    - Create a sample application (e.g., Node.js, Python) that exposes the necessary metrics and logs.
    - Include a library or middleware that supports Prometheus metrics in your application.
    - Expose a `/metrics` endpoint in your application accessible at the address specified in `prometheus.yml`.
    - Include a logging library or framework that sends logs to Logstash. Configure it to send logs to `logstash:5000`.
    - Restart your sample application.

5. Configure Grafana Dashboards:

    - In Grafana, create a new data source with Prometheus as the data source type (`http://localhost:9090`).
    - Import relevant pre-built dashboards from the Grafana Dashboard website (https://grafana.com/grafana/dashboards).
    - Customize and configure the imported dashboards as per your requirements.

6. Verify Monitoring Solution:

    - Generate traffic or perform actions in your sample application to trigger logs and metrics.
    - Access Grafana at `http://localhost:3000` to view metrics and logs visualizations.
    - Access Kibana at `http://localhost:5601` to explore and search application logs.

