# Gateway Device Application (Connected Devices)

## Lab Module 05

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 
Esta implementación desarrolla las capacidades necesarias para generar y estructurar datos en el gateway device. La aplicación principal incluye un gestor de datos que activa un módulo encargado de obtener información sobre el rendimiento del sistema, como el uso de CPU, disco y memoria. Esto se logra a través de módulos especializados para cada tarea. El objetivo principal es crear una base funcional que permita generar datos sobre el estado del gateway y gestionar la información de los dispositivos conectados de manera eficiente.

How does your implementation work?
Esta implementación abarca varios módulos destinados a gestionar los datos de los sensores y actuadores. Se crean las clases SensorData, ActuatorData, SystemPerformanceData y SystemStateData, todas ellas heredando de BaseIoTData. Estos módulos incluyen funciones clave como métodos para manejar y actualizar los datos específicos de cada uno, y un método handleUpdateData que facilita las modificaciones necesarias en los objetos cuando se actualizan. Además, SystemPerformanceManager se adapta para gestionar datos de rendimiento del sistema, como el uso de la CPU y la memoria, y se encarga de enviar esta información a la nube. Los módulos de DataUtil implementan funciones para convertir estos datos a JSON y viceversa, asegurando una comunicación adecuada entre los componentes del sistema.
En cuanto a DeviceDataManager, se encarga de la configuración de la comunicación con otros módulos y de la inicialización de SystemPerformanceManager. A través de sus métodos, gestiona los mensajes y realiza las operaciones necesarias para integrar el rendimiento del sistema con los dispositivos conectados. Por último, GatewayDeviceApp ofrece una implementación básica que permite ejecutar la aplicación en un ciclo continuo, con DeviceDataManager como el componente clave que controla tanto los sensores como los actuadores y la telemetría del sistema.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule05


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ConfigUtilTest
- SystemCpuUtilTaskTest
- SystemMemUtilTaskTest
- ActuatorDataTest
- SensorDataTest
- SystemPerformanceDataTest
- SystemStateDataTest
- DataUtilTest
- BaseIotDataTest


### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- SystemPerformanceManagerTest
- GatewayDeviceAppTest
- DeviceDataManagerTest
- DataIntegrationTest

EOF.
