# Cloud Service Functions (Connected Devices)

## Lab Module 12 - Semester Project - CSF Components

Be sure to implement all the PIOT-CSF-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi servicio en la nube (Ubidots STEM) es donde todos los datos de mis dispositivos IoT (CDA y GDA) terminan. Se conecta de forma segura al GDA para recibir y guardar datos de sensores como temperatura, humedad y calidad del aire, además del rendimiento de los dispositivos. Puedo ver toda esta información en gráficos en Ubidots. También he configurado Ubidots para que pueda enviar una orden para encender o apagar un LED en el CDA; esto lo hago desde un interruptor en el dashboard de Ubidots, demostrando control remoto desde la nube.

How does your implementation work?

Uso la plataforma Ubidots STEM sin escribir código para la nube. He creado un "Dispositivo" virtual para mi GDA y "Variables" para cada dato que quiero guardar. El GDA publica estos datos usando MQTT a los tópicos correctos de Ubidots (ej. /v1.6/devices/mi-gda/calidad-aire). Para controlar el LED, creé otra variable en Ubidots (comando-led) con un interruptor en el dashboard. 

### Code Documentation (only applies if you wrote CSF-specific code, otherwise, ignore)

#### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: 


#### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- 
- 
- 

#### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- 
- 
- 

EOF.
