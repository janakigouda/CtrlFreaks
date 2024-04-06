# Data Ingestion Layer
## PubSub
* Utilizes Pub/Sub for efficient and scalable message queuing, enabling seamless and decoupled data ingestion from various sources.
## Dataflow Streaming Pipeline
* Since the hardware devices operate in poor bandwidth area hence the input data from the source will not have the metadata such as enclosure_id, farm_id etc. We will only be sending the current reading along with the device id for ensuring smaller data packets.
* Aggregates data every 30 seconds, acting as a limit check on the amount of storage being utilized, particularly if the frequency from hardware devices is high.
* Enriches the data using Apache Beam pipeline's side input functionality. It fetches data from PostgreSQL, caching it to map the enclosure and farm for any input coming from a device.
* Updated periodically via a cron job every hour.
* Utilizes BigQueryIO and InfluxDBIO plugins for writing data points.
## Data Warehouse
* Chose BigQuery for its reliability, high availability, and industry-leading capabilities in handling big data.
## InfluxDB
* Selected due to its optimization for querying time-based data, especially for short durations. Given that many customers would frequently query the live feed, a time series database was deemed optimal for performance.
## Dataflow Batch Pipeline
* Due to the unstructured and high volume of data in BigQuery, querying it directly would result in exorbitant costs. Therefore, multiple batch dataflow pipelines are proposed to aggregate data periodically (daily/hourly) and provide it in a more structured format.
## MariaDB
* Data will be stored in an analytical database optimized for querying data over longer time ranges, suitable for visualizing trends over extended periods.

# Data Visualization Layer
## Grafana
* The time series database can be integrated with Grafana for visually appealing visualizations and streamlined filtering.
* Grafana also serves as our alerting module due to its powerful and well-managed alerting system.
## Metabase
* Ideal for visualizing analytical data, Metabase offers excellent support for analytical use cases.


# Application
## Communication protocol between farmer and app
* Since the farmer may reside in an area with poor network bandwidth, utilizing web sockets, which would be ideal for periodically updating data, becomes impractical. Therefore, we opt for a normal HTTP connection. In this setup, if necessary, the frontend code can independently make AJAX calls periodically to fetch the updated data, especially for live metrics.
## Dashboard generation for farmers
* When the farmer logs in there will be a section in the app to generate dashboards , he/she can select from the already pre-existing panels which they deem is important to them. They will have separate analytical and real time sections.
* The selected questions will generate a dashboard via a POST request in Metabase/Grafana, which will need to be embedded into the application maybe by admin and its id gets stored in postgres corresponding to customer.
* Upon opening the application the corrsponding dashboards for the customer will only be fetched.

