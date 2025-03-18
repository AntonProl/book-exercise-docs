# Constrained Device Application (Connected Devices)

## Lab Module 04

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Se realiza la conexión con el simuladado de una Raspberry Pi, ya que no he implementado un sensor real.
Además se implementan las conexiones de los datos relativos al emulador para así poder generar datos sintéticos para probar su funcionamiento. Además se conectan los actuadores para que así se puedan controlar tanto la temperatura como la presión.
He realizado un cambio en la versión utilizada de python debido a errores de dependencias, ya que estaba utilizando python 3.12 y algunas librerías no estaban disponibles para esta versión, por lo tanto he cambiado la versión a, 3.10.10. Además con este cambio se elimina el problema con las rutas relativas descrito anteriormente.

How does your implementation work?
Se implementan emuladores para los sensores de temperatura, humedad y presión, cada uno heredando de sus respectivas clases base para proporcionar valores simulados. Para esto, se sobrecarga el método generateTelemetry en cada uno de los sensores, de modo que generen y devuelvan datos simulados de acuerdo a las necesidades del sistema.

Además, se desarrollan emuladores para los actuadores, como HVAC, Humidifier y LED display, que también heredan de las clases base correspondientes. Al igual que en los sensores, se sobrescribe el método generateTelemetry para que estos actuadores puedan devolver valores simulados según el estado en el que se encuentren.

La gestión de los sensores se centraliza en la clase SensorAdapterManager, que tiene la responsabilidad de manejar los sensores simulados. Esta clase asegura que los datos generados por los sensores se gestionen correctamente y se integren al sistema de monitoreo.

De manera similar, los actuadores se gestionan a través de la clase ActuatorAdapterManager, que centraliza su manejo y generación de datos. Este administrador se encarga de ejecutar los comandos para los actuadores, simular sus respuestas y actualizar su estado según los datos recibido.

Las partes opcionales relativas al uso de hardware real (Raspberry Pi) no se han implementado por falta del mismo.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule04


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ConfigUtilTest.py
- SystemCpuUtilTaskTest.py
- SystemMemUtilTaskTest.py
- ActuatorDataTest.py
- SensorDataTest.py
- SystemPerformanceDataTest.py
- HumiditySensorSimTaskTest.py
- PressureSensorSimTaskTest.py
- TemperatureSensorSimTaskTest.py
- HumidifierActuatorSimTaskTest.py
- HvacActuatorSimTaskTest.py


### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- ConstrainedDeviceAppTest.py
- SystemPerformanceManagerTest.py
- SensorAdapterManagerTest.py
- ActuatorAdapterManagerTest.py
- DeviceDataManagerNoCommsTest.py
- SenseHatEmulatorQuickTest.py
- HumidityEmulatorTaskTest.py
- PressureEmulatorTaskTest.py
- TemperatureEmulatorTaskTest.py
- HumidifierEmulatorTaskTest.py
- HvacEmulatorTaskTest.py
- LedDisplayEmulatorTaskTest.py
- SensorEmulatorManagerTest.py
- ActuatorEmulatorManagerTest.py 

EOF.
