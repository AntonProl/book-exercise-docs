# Constrained Device Application (Connected Devices)

## Lab Module 09

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

La implementación permite al cliente CoAP observar recursos IoT, específicamente los comandos de actuadores, a través de solicitudes de tipo OBSERVE. Gestiona la suscripción y la cancelación de observaciones de recursos, y procesa las respuestas de los actuadores en formato JSON, integrándolas con un listener para manejar los comandos de manera eficiente.

How does your implementation work?

Cuando se invoca startObserver(), el cliente CoAP inicia la observación de un recurso especificado y gestiona las respuestas de los actuadores a través de un manejador, HandleActuatorEvent, que decodifica los datos JSON usando DataUtil. Si se recibe una respuesta, esta se pasa al listener para su procesamiento. Además, se incluye la capacidad de cancelar la observación con stopObserver(). Se registran eventos y errores para asegurar el funcionamiento correcto. Esto asegura que los recursos sean observados de forma continua y se respondan de manera adecuada.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule09



### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- All part01
- All part02

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)


- All part01
- All part02

EOF.
