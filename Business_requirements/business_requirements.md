# Business Requirements Document

## Introduction

This document outlines the business requirements for the Fish Watch system. It describes the functionalities, features, and capabilities required to meet the needs of stakeholders and users.

## Stakeholders

- **Fish Farmers**: Primary users of the system, responsible for managing fish farms and monitoring fish health and environmental conditions.
- **Aquarium Owners**: Secondary users interested in using the system to monitor fish health and maintain optimal conditions in aquariums.
- **Livestock Insights Inc.**: The company developing the Fish Watch system and providing support and maintenance services.

## Functional Requirements

### Dashboard Customization

- **Requirement**: Farmers need to be able to customize dashboards to view relevant information based on their preferences.
- **Details**: Users should be able to select and arrange widgets, charts, and data visualizations on the dashboard.
- **Priority**: High

### Threshold Alerts

- **Requirement**: Farmers should be able to specify thresholds for triggering alerts based on environmental conditions.
- **Details**: Users should define thresholds for parameters such as pH levels, temperature, oxygen levels, etc., and receive alerts when conditions exceed or fall below these thresholds.
- **Priority**: High

### Advanced Warning for Adverse Weather Events

- **Requirement**: Users require advanced warnings for adverse weather events that may impact fish farms.
- **Details**: The system should integrate with weather APIs to provide forecasts and alerts for weather conditions such as storms, heavy rainfall, or extreme temperatures.
- **Priority**: Medium

### Fish Harvest Tracking

- **Requirement**: Farmers need to track information about the fish harvested from each farm.
- **Details**: The system should capture data on harvested fish, including species, quantity, size, and quality.
- **Priority**: High

### Model Building for Harvest Prediction

- **Requirement**: The system should build predictive models to determine factors contributing to successful harvests.
- **Details**: Analyze historical data on fish farms and harvests to identify patterns and correlations between environmental factors and harvest outcomes.
- **Priority**: High

### Multi-farm Insights

- **Requirement**: Large customers require the ability to drive insights across multiple farms.
- **Details**: Provide aggregated views and analytics across multiple fish farms, allowing users to compare performance, identify trends, and make informed decisions.
- **Priority**: Medium

## Non-functional Requirements

### Timely Alert Generation

- **Requirement**: Alerts should be generated in a timely manner to ensure prompt action by users.
- **Details**: The system should monitor data streams in real-time and trigger alerts immediately when predefined thresholds are breached.
- **Priority**: High

### Accessibility from Rugged Industrial Devices

- **Requirement**: The system needs to be accessible from rugged industrial devices used in harsh environments.
- **Details**: Ensure that the Fish Watch web interface is optimized for use on rugged devices with limited screen size and input capabilities.
- **Priority**: Medium

### Connectivity in Remote Locations

- **Requirement**: The system should work in remote locations with poor cellular signal.
- **Details**: Implement offline functionality and data synchronization mechanisms to ensure continuous operation even in areas with unreliable network connectivity.
- **Priority**: High

## Conclusion

The business requirements outlined in this document provide a clear understanding of the functionalities, features, and capabilities required for the successful development and deployment of the Fish Watch system. By meeting these requirements, the system will address the needs of stakeholders and users, leading to improved fish farm management and productivity.

## References

- [Weather APIs](https://openweathermap.org/api)
- [Fish Farming Best Practices](https://www.worldfishcenter.org/)
