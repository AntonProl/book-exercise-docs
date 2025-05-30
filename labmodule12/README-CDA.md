# Constrained Device Application (Connected Devices)

## Lab Module 12 - Semester Project - CDA Components

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi CDA simula un dispositivo IoT que ahora mide la calidad del aire, además de la temperatura y humedad. Recoge estos datos y los de su propio rendimiento, y los envía de forma segura (MQTT con TLS) al GDA. Si la temperatura se sale de los límites, el CDA mismo activa un climatizador simulado. También obedece órdenes del GDA para encender un nuevo purificador de aire simulado o un LED, mostrando estas acciones en el emulador SenseHAT.

How does your implementation work?

Un DeviceDataManager en el CDA organiza la recolección periódica de datos del nuevo sensor de calidad del aire (y otros) y del rendimiento del sistema. Estos datos se envían al GDA usando un cliente MQTT seguro. Este cliente MQTT también escucha comandos del GDA: si llega una orden para el purificador de aire o el LED, se procesa y un ActuatorAdapterManager se encarga de que la simulación correspondiente (ej. AirPurifierActuatorSimTask) refleje la acción, actualizando el emulador SenseHAT. La lógica para el climatizador por temperatura funciona de manera similar, pero se decide localmente en el CDA.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: 


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- All

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- All

EOF.
