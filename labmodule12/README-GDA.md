# Gateway Device Application (Connected Devices)

## Lab Module 12 - Semester Project - GDA Components

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi GDA actúa como un puente seguro entre un CDA local (que ahora incluye un sensor de calidad del aire) y la nube (Ubidots). Recoge datos de sensores del CDA, como temperatura y la nueva lectura de calidad del aire, y los datos de rendimiento de ambos dispositivos, enviándolos a la nube. De forma inteligente, si el GDA detecta que la calidad del aire reportada por el CDA es mala según unos umbrales, ordena al CDA que active un nuevo actuador, un purificador de aire. Además, el GDA recibe comandos de la nube, como encender un LED, y los retransmite al CDA para su ejecución. Para mantener informado, envía correos ante eventos de actuación y guarda datos localmente.

How does your implementation work?

El GDA utiliza MQTT con TLS para comunicarse de forma segura tanto con el CDA como con Ubidots. Un DeviceDataManager central gestiona el flujo: cuando llegan datos del sensor de calidad del aire del CDA, los analiza. Si la calidad es consistentemente pobre (superando un umbral por un tiempo definido), el DeviceDataManager crea un comando ActuatorData para el nuevo purificador de aire y lo envía al CDA vía MQTT. Los datos de este nuevo sensor, junto con otros, se envían a la nube usando CloudClientConnector, que adapta los tópicos para Ubidots. Para comandos desde la nube (ej. LED), CloudClientConnector se suscribe a un tópico de Ubidots; al recibir una señal, un listener interno la convierte a ActuatorData y la pasa a DeviceDataManager, que la reenvía al CDA. Un SmtpClientConnector se encarga de las notificaciones por correo cuando se activan actuadores.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule12



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
