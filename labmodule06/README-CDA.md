# Constrained Device Application (Connected Devices)

## Lab Module 06

Be sure to implement all the PIOT-CDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi implementación se centra en la integración y gestión de un cliente MQTT dentro de un sistema de dispositivos conectados (CDA, Connected Devices Architecture). Específicamente, en los documentos mencionados, se abordan las tareas de conexión y desconexión del cliente MQTT con el broker, así como suscripción y publicación en temas específicos para la comunicación entre dispositivos. La implementación también cubre el manejo de la configuración del cliente MQTT, y la gestión de los paquetes de control del protocolo MQTT para asegurar una correcta operación y control de la comunicación entre el cliente y el broker.
Además, en los casos de prueba, se incluye la generación de todos los paquetes de control necesarios para trabajar con MQTT, abarcando los 14 tipos definidos en la especificación MQTT 3.1.1, utilizando tanto QoS 1 como QoS 2, y garantizando que se mantenga la conexión activa para permitir solicitudes de KeepAlive.

How does your implementation work?

-Inicialización del Cliente MQTT: En la clase DeviceDataManager, se verifica si se debe habilitar el cliente MQTT a partir de la configuración del sistema. Si es necesario, se crea una instancia de MqttClientConnector, que es la encargada de gestionar la comunicación con el broker MQTT.

-Conexión al Broker: Durante el inicio del sistema, el cliente MQTT se conecta al broker mediante el método connectClient(). Además, se suscribe a un tema específico utilizando subscribeToTopic(), lo que le permite recibir mensajes desde el broker. La suscripción se realiza con un nivel de calidad de servicio (QoS) que se configura previamente.

-Desconexión y Desuscripción: Cuando el sistema se detiene, se realiza una desconexión segura del broker. Esto se hace asegurándose de que el cliente MQTT esté conectado, desuscribiéndose del tema con unsubscribeFromTopic(), y finalmente cerrando la conexión con disconnectClient().

-Manejo de Paquetes de Control MQTT: La implementación también se asegura de gestionar adecuadamente los diferentes tipos de paquetes de control que define el protocolo MQTT, como CONNECT, PUBLISH, SUBSCRIBE, PINGREQ, entre otros. El cliente MQTT maneja estos paquetes de forma automática y garantiza la entrega de mensajes usando diferentes niveles de QoS (1 y 2).

-Pruebas de Integración: Para verificar que todo funcione correctamente, se crean pruebas de integración que comprueban que los paquetes de control MQTT se envíen y reciban correctamente. Estas pruebas también validan que el cliente MQTT se comporta según lo esperado, manejando la conexión, suscripción y publicación de manera adecuada, y generando los paquetes necesarios según las especificaciones del protocolo MQTT 3.1.1.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule06


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

![imagen](https://github.com/user-attachments/assets/557cc750-4023-4a2b-8460-6b8ddc91d6d9)

CONNECT:

![imagen](https://github.com/user-attachments/assets/b0897d0b-5d6b-477f-8e9b-8699fde99534)


CONNECT ACK:

![imagen](https://github.com/user-attachments/assets/27f17600-50f7-4818-84df-c19db12bfdf3)

SUBSCRIBE REQUEST:

![imagen](https://github.com/user-attachments/assets/279a64f1-228e-4b22-8439-7c40d40a35e9)

SUBSCRIBE ACK:

![imagen](https://github.com/user-attachments/assets/d0bb5ad0-16ec-4ee4-b524-af6bdc37b168)

UNSUSCRIBE REQUEST:

![imagen](https://github.com/user-attachments/assets/2c803491-faa7-446a-b70e-acd48cdeb287)

UNSUSCRIBE ACK:

![imagen](https://github.com/user-attachments/assets/d269fe33-9533-4366-a29d-6b0a24e7c7ef)

DISCONNECT REQ:

![imagen](https://github.com/user-attachments/assets/8c03fbe8-737f-48ea-b4bb-3d4e7879db52)

EOF.
