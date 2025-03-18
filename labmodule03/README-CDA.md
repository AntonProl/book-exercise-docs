# Constrained Device Application (Connected Devices)

## Lab Module 03

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Esta implementación se encarga de simular los sensores y actuadores en el ConstrainedDeviceApp, definiendo plantillas de datos para cada tipo. Se crean datos básicos de un dispositivo IoT, a partir de los cuales se generan los datos para los sensores y actuadores, como nombre, ID y valor. Se incluyen sensores de humedad, presión y temperatura, y actuadores como el Hunididier y el sistema HVAC). Los sensores producen telemetría, mientras que los actuadores simulan su activación o desactivación según su estado. También se desarrollan clases para gestionar estos componentes (SensorAdapterManager, ActuatorAdapterManager, DeviceDataManager).

How does your implementation work?
La implementación comienza con la clase BaseIotData, que sirve como base para ActuatorData, SensorData y SystemPerformanceData, incluyendo atributos comunes como tipo, ID, estado, nombre y valor, con sus métodos getter y setter. Las clases hijas añaden detalles específicos para sensores y actuadores. Luego, se crea la clase base BaseSensorSimTask, que define la información y los métodos de telemetría de un sensor genérico, de la cual heredan los sensores de temperatura, presión y humedad, que generarán datos simulados más adelante. Se sigue un enfoque similar con BaseActuatorSimTask, donde los actuadores gestionan su estado y respuestas mediante comandos simulados.

Después, se implementa SensorAdapterManager para gestionar todos los sensores, configurando actualizaciones y emulación de datos, y permitiendo iniciar y detener los sensores. ActuatorAdapterManager hace lo mismo pero para gestionar los comandos de los actuadores. DeviceDataManager reúne las funciones de los dos gestores y la performance del sistema con SystemPerformanceManager, gestionando la inicialización, parada y comunicación de los componentes. DeviceDataManager se crea en ConstrainedDeviceApp, que es el punto de entrada de la aplicación, llamando a los gestores y ejecutando todo en un bucle. La implementación sigue el código de ejemplo, adaptándolo para evitar errores de ejecución, sin cambiar demasiado la estructura original.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule03

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
- ConstrainedDeviceAppTest.py

EOF.
