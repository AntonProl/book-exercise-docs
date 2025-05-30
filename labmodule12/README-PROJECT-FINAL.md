# Lab Module 12 - Semester Project - Final Write-up

NOTE: Be sure to implement all the Lab Module 12 requirements listed at Lab Module 12.


## Description

Describe your idea in 1 paragraph (at least 2 or 3 sentences).

Mi proyecto implementa un sistema de monitoreo ambiental y control de calidad del aire en interiores, utilizando un dispositivo restringido (CDA) para medir la temperatura, humedad y calidad del aire, y un dispositivo de pasarela (GDA) para agregar datos, tomar decisiones locales y conectarse a la nube. 


## What - The Problem 

What problem did you tackle and why does it matter? Write 1 to 2 paragraphs in response.



## Why - Who Cares? 

Why do you care about this particular problem? Write 1 to 2 paragraphs in response.



## How - Expected Technical Approach

Write 1 to 2 paragraphs describing the outcomes you achieved.


### System Diagram

Embed a block diagram depicting your overall design, including the CDA, GDA, and Cloud Services interactions.
Be sure to include arrows depicting data flow from one application / service to the next.

    CDA -> GDA: SensorData (Temp, Hum, AirQuality), SystemPerformanceData (vía MQTT/TLS)

    GDA -> CDA: ActuatorData (Comando Purificador, Comando LED) (vía MQTT/TLS)

    GDA -> Nube (Ubidots): SensorData (Temp, Hum, AirQuality del CDA), SystemPerformanceData (CDA y GDA) (vía MQTT/TLS)

    Nube (Ubidots) -> GDA: ActuatorData (Comando LED) (vía MQTT/TLS))

Write 1 to 2 paragraphs describing your design.



### What THREE (3) sensors and ONE (1) actuator did you use (add more if you wish)?

    CDA Sensor 1: Temperature Sensor (Sensor de Temperatura)

    CDA Sensor 2: Humidity Sensor (Sensor de Humedad)

    CDA Sensor 3: Air Quality Sensor (Sensor de Calidad del Aire)

    CDA Actuator 1: Air Purifier Actuator (Actuador Purificador de Aire) (Además del LED y el HVAC que ya estaban)



### What ONE (1) CDA protocol and TWO (2) GDA protocols did you implement (add more if you wish)?

    CDA to GDA Protocol: MQTT (with TLS)

    GDA to CDA Protocol: MQTT (with TLS)

    GDA to Cloud Protocol: MQTT (with TLS)

    Cloud to GDA Protocol: MQTT (with TLS)

 
### What TWO (2) cloud services / capabilities did you use (add more if you wish)?

- Cloud Service 1 (data ingress - all inputs):

- Cloud Service 2 (data egress - all actuation events):



## Screen Shots Representing Cloud Services



### Screen Shots Representing Visualized Data

NOTE: Include (at least) TWO (2) screen shots - one showing at least 1 hour
of time-series data from the CDA, and one showing an event being triggered
that results in an actuation event sent to your GDA and then to your CDA.



EOF.
