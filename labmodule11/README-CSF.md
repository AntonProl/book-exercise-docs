# Cloud Service Functions (Connected Devices)

## Lab Module 11

These optional components may be included in your assignment, but are not required. If you choose to implement them, be sure to complete this README and review all the PIOT-CSF-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi servicio en la nube (Ubidots STEM) recibe y guarda de forma segura los datos que le envía mi GDA. Estos datos incluyen lecturas de sensores como temperatura y humedad del CDA, y datos de cómo están funcionando tanto el CDA como el GDA. Además, desde un panel de control en Ubidots, puedo enviar una orden para encender o apagar un LED en el CDA, demostrando un control básico desde la nube.

How does your implementation work?

He configurado Ubidots creando un "Dispositivo" y "Variables" para cada tipo de dato (temperatura, uso de CPU, etc.). El GDA publica estos datos usando MQTT a los tópicos correctos de Ubidots (ej. /v1.6/devices/mi-gda/temperatura). Para controlar el LED, creé una variable "control-led" en Ubidots con un interruptor. Cuando uso el interruptor, Ubidots envía un mensaje (0 o 1) por MQTT a un tópico específico. El GDA está escuchando ese tópico, recibe el mensaje, y le dice al CDA que cambie el estado del LED. Todo esto se hace configurando Ubidots, sin escribir código para la nube.

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
