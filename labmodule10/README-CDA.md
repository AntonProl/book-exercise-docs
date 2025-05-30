# Constrained Device Application (Connected Devices)

## Lab Module 10

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Mi CDA ahora se comunica de forma segura por MQTT (si se activa TLS), recibe órdenes del GDA (como "enciende el aire acondicionado") y las ejecuta en sus actuadores simulados. También envía datos de sus sensores (temperatura, etc.) y de su propio rendimiento al GDA. Lo más destacado es que si detecta, por ejemplo, que la temperatura es muy alta o baja según unos límites, puede decidir por sí mismo activar el climatizador para corregirlo, sin esperar una orden del GDA. Además, el envío de mensajes MQTT lo hace de forma más eficiente, sin quedarse esperando la confirmación de cada uno.

How does your implementation work?
Cuando el CDA arranca, prepara su conexión MQTT (con seguridad TLS si está configurada). Al conectarse al servidor MQTT, se pone a escuchar por si llegan comandos para sus actuadores desde el GDA. Si llega un comando (por ejemplo, un mensaje JSON para controlar el climatizador), lo entiende y le dice a la parte encargada de los actuadores que realice la acción. Por otro lado, el CDA constantemente recoge datos de sus sensores y de cómo está funcionando. Revisa los datos de los sensores; si la temperatura, por ejemplo, se sale de los valores permitidos, el mismo CDA genera una orden para el climatizador. Finalmente, todos estos datos (de sensores y de rendimiento) los convierte a formato JSON y los envía al GDA usando MQTT, de una manera que no interrumpe otras tareas que esté haciendo.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule10


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- All part 01
- All part 02

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- All part 01
- All part 02


CDA MQTT Client Performance Test 
testConnectAndDisconnect

2025-05-30 16:56:53,224:ConfigUtil:INFO:Loading config: /home/antonprol/Escritorio/practicas_pic/Python-Components/config/PiotConfig.props
2025-05-30 16:56:53,224:ConfigUtil:DEBUG:Config: ['Mqtt.GatewayService', 'Coap.GatewayService', 'ConstrainedDevice']
2025-05-30 16:56:53,224:ConfigUtil:INFO:Created instance of ConfigUtil: <programmingtheiot.common.ConfigUtil.ConfigUtil object at 0x76eb90a0e770>
2025-05-30 16:56:53,224:MqttClientConnector:INFO:	MQTT Client ID:   CDAMqttClientPerformanceTest001
2025-05-30 16:56:53,224:MqttClientConnector:INFO:	MQTT Broker Host: localhost
2025-05-30 16:56:53,224:MqttClientConnector:INFO:	MQTT Broker Port: 1883
2025-05-30 16:56:53,224:MqttClientConnector:INFO:	MQTT Keep Alive:  60
2025-05-30 16:56:53,224:MqttClientConnector:DEBUG:ConnectClient: Nueva instancia de Paho client creada.
2025-05-30 16:56:53,225:MqttClientConnector:INFO:ConnectClient: Conectando a broker: localhost:1883
2025-05-30 16:56:53,226:MqttClientConnector:DEBUG:ConnectClient: loop_start() invocado.
2025-05-30 16:56:53,226:MqttClientConnector:INFO:MQTT client connected to broker: <paho.mqtt.client.Client object at 0x76eb90a0e680>
2025-05-30 16:56:53,226:MqttClientConnector:INFO:MQTT client connected successfully.
2025-05-30 16:56:53,226:MqttClientConnector:INFO:MQTT client subscribed: <paho.mqtt.client.Client object at 0x76eb90a0e680>
2025-05-30 16:56:55,228:MqttClientConnector:INFO:ConnectClient: Conexión exitosa verificada después de la espera.
2025-05-30 16:56:55,228:MqttClientPerformanceTest:DEBUG:Disconnecting MQTT client...
2025-05-30 16:56:55,228:MqttClientConnector:INFO:Disconnecting MQTT client from broker: localhost
2025-05-30 16:56:56,230:MqttClientConnector:INFO:MQTT client disconnected from broker: <paho.mqtt.client.Client object at 0x76eb90a0e680>
2025-05-30 16:56:56,230:MqttClientPerformanceTest:DEBUG:Disconnect result: True
2025-05-30 16:56:56,230:MqttClientPerformanceTest:INFO:Connect and Disconnect: 3005.264244 ms


testPublishQoS0

2025-05-30 16:55:43,819:MqttClientConnector:INFO:MQTT message published: <paho.mqtt.client.Client object at 0x77f9aa1167a0>
2025-05-30 16:55:43,819:MqttClientConnector:INFO:Disconnecting MQTT client from broker: localhost
2025-05-30 16:55:44,820:MqttClientConnector:INFO:MQTT client disconnected from broker: <paho.mqtt.client.Client object at 0x77f9aa1167a0>
2025-05-30 16:55:44,820:MqttClientPerformanceTest:INFO:
	Testing Publish: QoS = 0 | msgs = 10000 | payload size = 264 | start = 1748616943383536.8 | end = 1748616943819142.5 | elapsed = 0.43560555
2025-05-30 16:55:44,820:MqttClientPerformanceTest:INFO:Publish message - QoS 0 [10000]: 435.60555 ms


testPublishQoS1

2025-05-30 16:57:51,662:MqttClientConnector:INFO:MQTT message published: <paho.mqtt.client.Client object at 0x73cce81427a0>
2025-05-30 16:57:51,662:MqttClientConnector:INFO:Disconnecting MQTT client from broker: localhost
2025-05-30 16:57:52,664:MqttClientConnector:INFO:MQTT client disconnected from broker: <paho.mqtt.client.Client object at 0x73cce81427a0>
2025-05-30 16:57:52,664:MqttClientPerformanceTest:INFO:
	Testing Publish: QoS = 1 | msgs = 10000 | payload size = 264 | start = 1748617070852429.2 | end = 1748617071662791.5 | elapsed = 0.810362349
2025-05-30 16:57:52,664:MqttClientPerformanceTest:INFO:Publish message - QoS 1 [10000]: 810.362349 ms


testPublishQoS2

2025-05-30 16:58:25,447:MqttClientConnector:INFO:MQTT message published: <paho.mqtt.client.Client object at 0x722d085127a0>
2025-05-30 16:58:25,447:MqttClientConnector:INFO:Disconnecting MQTT client from broker: localhost
2025-05-30 16:58:26,447:MqttClientConnector:INFO:MQTT client disconnected from broker: <paho.mqtt.client.Client object at 0x722d085127a0>
2025-05-30 16:58:26,447:MqttClientPerformanceTest:INFO:
	Testing Publish: QoS = 2 | msgs = 10000 | payload size = 264 | start = 1748617104245584.0 | end = 1748617105447114.2 | elapsed = 1.2015303960000001
2025-05-30 16:58:26,447:MqttClientPerformanceTest:INFO:Publish message - QoS 2 [10000]: 1201.530396 ms



EOF.
