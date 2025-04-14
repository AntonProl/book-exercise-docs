# Gateway Device Application (Connected Devices)

## Lab Module 08

Be sure to implement all the PIOT-GDA-* issues (requirements) listed.

### Description

NOTE: Include two full paragraphs describing your implementation approach by answering the questions listed below.

What does your implementation do? 

Mi implementación establece un servidor CoAP (Constrained Application Protocol) para facilitar la comunicación con dispositivos IoT. Permite la adición dinámica de recursos, tanto durante la inicialización del servidor como en tiempo de ejecución. El servidor gestiona recursos organizados en una estructura jerárquica, permitiendo interacciones como GET y POST en dichos recursos.

How does your implementation work?

Mi implementación establece un servidor CoAP para facilitar la comunicación con dispositivos IoT, gestionando recursos en una estructura jerárquica. Se inicializa con recursos predeterminados, y permite agregar nuevos recursos tanto al inicio como en tiempo de ejecución mediante métodos como addResource. La creación de recursos se organiza jerárquicamente con createAndAddResourceChain. El servidor maneja solicitudes a través de manejadores específicos, como UpdateSystemPerformanceResourceHandler, y se puede iniciar o detener con startServer() y stopServer(). 

### Code Repository and Branch

NOTE: Be sure to include the branch.

URL: https://github.com/AntonProl/java-components/tree/labmodule08


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

EOF.
