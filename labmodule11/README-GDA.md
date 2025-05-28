# Gateway Device Application (Connected Devices)

## Lab Module 11

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi GDA ahora habla con la nube (Ubidots) de forma segura. Le envía datos de los sensores que recoge del CDA y de sí mismo. También, si la nube le manda una orden (como "enciende un LED"), el GDA la recibe y se la pasa al CDA para que la ejecute.

How does your implementation work?

El GDA usa un conector MQTT especial (CloudClientConnector) para conectarse a Ubidots con certificados y claves. Este conector traduce los nombres de los tópicos para que Ubidots los entienda y así poder enviarle datos. Para recibir órdenes de la nube (como la del LED), se suscribe a un tópico específico de Ubidots. Cuando llega una orden, un "oyente" la procesa, la convierte en un ActuatorData, y se la da al DeviceDataManager, quien finalmente la envía al CDA por el MQTT local.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule11


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- 
- 
- 

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- 
- 
- CloudClientConnectorTest

EOF.
