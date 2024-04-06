# Data Ingestion Layer
## PubSub
    * Utilizes Pub/Sub for efficient and scalable message queuing, enabling seamless and decoupled data ingestion from various sources.
## Dataflow Streaming Pipeline
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

# Dashboard generation for farmers
    * When the farmer logs in there will be a section in the app to generate dashboards , he/she can select from the already pre-existing panels which they deem is important to them. They will have separate analytical and real time sections.
    * The selected questions will generate dashboard via post request in metabase/ grafana which will get embedded into the application

