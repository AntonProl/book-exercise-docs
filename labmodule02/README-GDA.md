# Gateway Device Application (Connected Devices)

## Lab Module 02

Be sure to implement all the PIOT-GDA-* issues.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Se crea una aplicación de gateway autoadministrada (GDA) que no solo ejecuta sus funcionalidades principales, sino que también monitorea continuamente el rendimiento del sistema. Integra módulos para recopilar datos de telemetría, como el uso de CPU y memoria, y registra estos valores periódicamente, asegurando que el monitoreo se gestione junto con el ciclo de vida de la aplicación.

How does your implementation work?

La clase GatewayDeviceApp inicializa el SystemPerformanceManager, que a su vez crea dos tareas especializadas, SystemCpuUtilTask y SystemMemUtilTask, que extienden de BaseSystemUtilTask. Estas tareas usan la API ManagementFactory de Java para obtener el uso de CPU y la memoria JVM. El SystemPerformanceManager utiliza ScheduledExecutorService para ejecutar periódicamente un proceso que llama a los métodos getTelemetryValue() de ambas tareas y registra las métricas de rendimiento
Además se realizó un cambio en la clase *BaseSystemUtilTask*, ya que el *Logger*, que inicialmente era privado, tuvo que modificarse a protegido. Esto fue necesario debido a los errores que surgían en las pruebas de *SystemCpuUtilTask* y *SystemMemUtilTask*, ya que no podían acceder al *Logger* cuando este era privado.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule02


### Unit Tests Executed

NOTE: The instructor will execute your unit tests. You only need to list each test case below
(e.g. ConfigUtilTest, DataUtilTest, etc). Be sure to include all previous tests, too,
since you need to ensure you haven't introduced regressions.

- ConfigUtilTest
- SystemCpuUtilTaskTest
- SystemMemUtilTaskTest

### Integration Tests Executed

NOTE: The instructor will execute most of your integration tests using their own environment, with
some exceptions (such as your cloud connectivity tests). In such cases, they'll review
your code to ensure it's correct. As for the tests you execute, you only need to list each
test case below (e.g. SensorSimAdapterManagerTest, DeviceDataManagerTest, etc.)

- GatewayDeviceAppTest
- SystemPerformanceManagerTest

EOF.
