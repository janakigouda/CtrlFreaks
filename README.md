# CtrlFreaks
O'Reilly Architecture Katas

## The Architecture

#### Hardware Architechture

LoRaWAN Sensors:
* Use appropriate sensors for monitoring parameters like water quality (pH, temperature, dissolved oxygen), fish behavior, * feeding patterns, etc.
* Integrate these sensors with LoRaWAN transceivers. Popular LoRaWAN sensor modules include those from companies like Libelium, Dragino, and Seeed.

LoRaWAN Gateway:
* Install a LoRaWAN gateway within range of the fish farm area to receive sensor data.
* The gateway will collect data from LoRaWAN sensors and forward it to the LoRaWAN network server.

LoRaWAN Network Server:
* Choose a LoRaWAN network server (open-source or commercial) to manage the LoRaWAN devices and data traffic.
* Network servers handle device authentication, data encryption, and manage the communication between LoRaWAN gateways and end devices (sensors).

Google Cloud Platform (GCP) IoT Core:
* This will act as the cloud-based IoT backend for device management and data ingestion.

Integration Between LoRaWAN Network Server and GCP IoT Core:
* Use MQTT (Message Queuing Telemetry Transport) or another protocol supported by both the LoRaWAN network server and GCP IoT Core to forward data.
* Configure the LoRaWAN network server to send sensor data as MQTT messages to the GCP IoT Core.

Data Processing and Storage:
* Set up cloud functions or data pipelines within GCP to ingest, process, and store incoming sensor data.
* Use services like Google Cloud Storage, Google Cloud Pub/Sub, or Google BigQuery for data storage and analytics.
