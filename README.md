# CtrlFreaks

# Fish Watch System

Fish Watch is a comprehensive system designed to assist farmers in managing fish farms effectively. It provides real-time monitoring, customizable dashboards, alerting mechanisms, and insights to optimize harvests. This README file provides an overview of the Fish Watch system, its features, requirements, and considerations.

# Container Diagram

![alt text](https://github.com/janakigouda/IDfy_CtrlFreaks/blob/main/Diagrams/Container%20Diagram.png)


## The Architecture

### LoRaWAN Sensors
* Use appropriate sensors for monitoring parameters like water quality (pH, temperature, dissolved oxygen), fish behavior, * feeding patterns, etc.
* Integrate these sensors with LoRaWAN transceivers. Popular LoRaWAN sensor modules include those from companies like Libelium, Dragino, and Seeed.

### LoRaWAN Gateway
* Install a LoRaWAN gateway within range of the fish farm area to receive sensor data.
* The gateway will collect data from LoRaWAN sensors and forward it to the LoRaWAN network server.

### LoRaWAN Network Server
* Choose a LoRaWAN network server (open-source or commercial) to manage the LoRaWAN devices and data traffic.
* Network servers handle device authentication, data encryption, and manage the communication between LoRaWAN gateways and end devices (sensors).

### Google Cloud Platform (GCP) IoT Core
* This will act as the cloud-based IoT backend for device management and data ingestion.

### Integration Between LoRaWAN Network Server and GCP IoT Core
* Use MQTT (Message Queuing Telemetry Transport) or another protocol supported by both the LoRaWAN network server and GCP IoT Core to forward data.
* Configure the LoRaWAN network server to send sensor data as MQTT messages to the GCP IoT Core.

### Data Processing and Storage
* Set up cloud functions or data pipelines within GCP to ingest, process, and store incoming sensor data.
* Use services like Google Cloud Storage, Google Cloud Pub/Sub, or Google BigQuery for data storage and analytics.


## Features

- Real-time monitoring of crucial parameters such as pH levels, water temperature, oxygen levels, and weather conditions.
- Customizable dashboards allowing farmers to select and arrange specific parameters they wish to monitor.
- Alerting mechanisms to notify farmers when parameters exceed or fall below specified thresholds, including basic issues and advanced warnings for adverse weather events.
- Harvest tracking and modeling to correlate harvested fish information with raw data collected from farms.
- Multi-farm insights allowing large customers to analyze data across multiple farms.
- Accessibility from various devices, including rugged industrial devices used at sea.
- Support for poor cellular signals in remote farm locations.
- Scalability to accommodate richer information about fish behavior and water quality as technology advances.
- Potential expansion to cater to other livestock monitoring needs and aquarium health management.

## Folder Structure

- **/Architecture**: Contains documents outlining the architecture of the Fish Watch system.
- **/Diagrams**: Includes visual diagrams representing various aspects of the fish farm architecture.
- **/Business_requirements**: Contains documents specifying the business requirements of the Fish Watch system.
- **/readme**: Includes this README file.

