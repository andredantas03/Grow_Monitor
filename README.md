# Grow_Monitor
App suite for monitoring a home grow

Proposed Architecture (Containers)
the system will be splited into separate containers:

1. Data Collection (Python + Sensors):
Container 1 (Data Collection) is the heart of the homegrow monitoring system. Its main function is to read the sensors connected to the Raspberry Pi, process the data and send it to the InfluxDB.

2. InfluxDB: 
Container 2 (Database) is the central storage of your monitoring system, responsible for storing, organizing and providing access to data collected by sensors. It works as a "library" where all the information about the homegrow (temperature, humidity, etc.) is saved in a structured way for future consultations, dashboards and analyses.

3. Web Server/Dashboard Flask:
Container 3 (Web Server/Dashboard) is the interface human-machine of the homegrow monitoring system, responsible for displaying the collected data visually and interactively in a browser (via mobile phone, laptop, etc.). It consumes the data stored in Container 2 (Database) and transforms it into easy-to-understand graphs, tables and alerts.

4. MQTT Broker (Mosquitto):
Container 4 (MQTT Broker) is the "nervous system" of the homegrow, responsible for managing real-time communication between all devices and services in your project (sensors, Raspberry Pi, dashboards, alerts, etc.). It acts as an intelligent intermediary that receives, filters and distributes messages efficiently, even on limited networks (such as home Wi-Fi).

5. Reverse Proxy Nginx: Container 5 (Reverse Proxy) is responsible for managing, optimizing and protecting access to the homegrow services (Flask, Grafana, Mosquitto, etc.). It acts as an intermediary between the internet/local network and your containers, bringing critical benefits to security, performance and organization.
