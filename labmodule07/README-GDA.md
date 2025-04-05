# Gateway Device Application (Connected Devices)

## Lab Module 07

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi implementación permite integrar el cliente MQTT dentro del DeviceDataManager, habilitando la comunicación entre dispositivos mediante este protocolo. Esto permite que el sistema se conecte a un broker MQTT, envíe y reciba mensajes, y se suscriba a los tópicos necesarios para la gestión de dispositivos.

How does your implementation work?

La implementación comienza habilitando MQTT en DeviceDataManager mediante un parámetro de configuración que determina si se debe usar el cliente MQTT o no. Si se habilita, se crea una instancia de MqttClientConnector dentro del constructor de DeviceDataManager. Luego, en el método initManager(), se verifica si el cliente debe ser instanciado y, en caso afirmativo, se conecta al broker MQTT.

Una vez conectado, el sistema se suscribe a los tópicos relevantes (como GDA_MGMT_STATUS_MSG_RESOURCE, CDA_ACTUATOR_RESPONSE_RESOURCE, entre otros), lo que permite recibir mensajes de otros dispositivos. En el método startManager(), se gestionan las suscripciones y la conexión al broker.

Cuando el sistema deja de ser necesario o se apaga, en el método stopManager(), se desconecta del broker, se cancelan las suscripciones a los tópicos y se asegura que la conexión se cierre correctamente. Esto garantiza una gestión adecuada de los recursos y una comunicación eficiente entre dispositivos.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule07


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
- MqttClientConnectorTest
- MqttClientControlPacketTest

EOF.
