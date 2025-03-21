# Constrained Device Application (Connected Devices)

## Lab Module 05

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Esta implementación mejora la conversión de datos entre objetos y JSON en la CDA, esencial para la comunicación eficiente entre los componentes del sistema. Se actualiza SystemPerformanceManager para recopilar telemetría de CPU y memoria, y se optimiza DataUtil para convertir datos de sensores, actuadores y rendimiento a JSON y viceversa. Esto facilita el almacenamiento, envío y procesamiento de datos en el sistema.

How does your implementation work?
La implementación actualiza el *SystemPerformanceManager* para recopilar telemetría de CPU y memoria y añade un *setter* para asignar un *dataMessageListener*. Además, mejora la clase *DataUtil* para convertir datos de sensores, actuadores y rendimiento del sistema hacia y desde JSON. Esto incluye métodos para transformar JSON en diccionarios, objetos en cadenas JSON con formato y para actualizar objetos con datos extraídos de JSON, optimizando la comunicación y el manejo de datos en el sistema.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule05


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
- Part 2 tests

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
- DataIntegrationTest.py

EOF.
