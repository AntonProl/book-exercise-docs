# Gateway Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi GDA se conecta de forma segura a MQTT y escucha los datos del CDA (sensores, rendimiento, respuestas de actuadores). Lo más importante es que si el CDA informa que la humedad está mal durante un tiempo, el GDA le ordena al CDA (vía MQTT) que active el humidificador para arreglarlo.

How does your implementation work?

El GDA, al conectarse a MQTT (usando credenciales y TLS si es necesario), se suscribe para recibir mensajes del CDA. Cuando llega un mensaje (ej. datos de humedad en JSON), lo convierte a un objeto y se lo pasa al DeviceDataManager. Este revisa si la humedad está fuera de los límites establecidos; si es así, crea un comando para el humidificador y lo envía como un mensaje JSON por MQTT de vuelta al CDA.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule10



### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- All part01
- All part02

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- All part01
- All part02

EOF.
