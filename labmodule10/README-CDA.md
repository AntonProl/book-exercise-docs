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

URL: 


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
- 

EOF.
