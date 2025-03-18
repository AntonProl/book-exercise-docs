# Constrained Device Application (Connected Devices)

## Lab Module 02

Be sure to implement all the PIOT-CDA-* issues (requirements).

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

La implementación mejora la aplicación CDA al agregar un módulo que monitorea el rendimiento del sistema. Este módulo recopila información sobre el uso de la CPU y la memoria, permitiendo que la aplicación controle el consumo de recursos. El *SystemPerformanceManager* gestiona estas tareas, asegurando que se realicen a intervalos regulares y se puedan activar o detener cuando sea necesario. También se realizan pruebas para asegurar que todo funcione bien. Finalmente, el trabajo se integró con el proyecto principal.
En esta implementación se han cambiado las rutas relativas de los archivos pertinentes por rutas absolutas ya que he tenido problemas con las rutas relativas debido a la versión de python utilizada.

How does your implementation work?

La implementación integra un sistema de monitoreo de recursos en la aplicación CDA mediante el **SystemPerformanceManager**, que gestiona las tareas de monitoreo de CPU y memoria, ejecutándolas a intervalos definidos usando la librería *apscheduler*. Estas tareas, **SystemCpuUtilTask** y **SystemMemUtilTask**, heredan de la clase base **BaseSystemUtilTask** y utilizan *psutil* para obtener los porcentajes de uso de la CPU y la memoria del sistema. El **SystemPerformanceManager** se integra dentro de la CDA, garantizando que el monitoreo de los recursos comience y termine junto con la ejecución de la aplicación, recopilando los datos de rendimiento durante su funcionamiento. Se realizaron **pruebas unitarias** para verificar el funcionamiento correcto de las tareas de monitoreo, y **pruebas de integración** para asegurar que el *SystemPerformanceManager* se configura y ejecuta correctamente las tareas de recolección de datos.

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/Python-Components/tree/labmodule02

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

- ConstrainedDeviceAppTest
- SystemPerformanceManagerTest

EOF.
