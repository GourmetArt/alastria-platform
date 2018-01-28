# Reference architecture of a blockchain
The reference architecture of blockchain and distributed ledger technology consists of five layers, as well as a cross-layer feature set across the layers. They are depicted in the following pictures, and the following sections describe the layers and each of the individual components.

![](https://docs.google.com/drawings/d/e/2PACX-1vQnYqNAfekzwVrKIwAkchLN2D9m99WJdeZNpjgm2xxN_4cldvGrVAgG7QIaW_JN0A0UVnWzC9QobB9W/pub?w=1130&h=660)

![](https://docs.google.com/drawings/d/e/2PACX-1vT93ch52Ep-6YkqFiOZpPRUyv5-fDhEwki9itMILAAg6_g3ZF0DaSRu4pGUBc3-z_OudckU4j4Vr_v5/pub?w=1071&h=798)

# Infrastructure layer

The Infrastructure layer provides the operating environment, including networking and compute and storage components required for the normal operation of a blockchain system. It may be provided as a set of cloud computing resources or it may be provided as on-premises equipment.

## Data Storage

Physical location to put data for the ledger and other data store requirements
Data Storage function should meet the following requirements:
- can be deployed and used by each node in peer-to-peer network
- can be deployed distributed or local
- can support appropriate data sovereignty
- can provide data writing and query services efficiently, safely and stably

## Runtime Environment (Compute)

Runtime environment function provides the execution capabilities for the operation of the blockchain system, including but not limited to container technology, virtual machine technology and cloud computing technology. Generally, runtime environments should be provided to each node in the blockchain system.

## Communication Networks

Communication networks are required for the peer-to-peer networking of the DLT system nodes and also for communication between the DLT system and the entities in the user layer and in the non-DLT systems.

# DLT Platform layer

DLT Platform layer contains the core functions of the DLT system that can run in a DLT node and which also involves communication between nodes.
Key capabilities include:
- Consensus mechanisms which coordinates the data and account records in the ledger between nodes. This consensus mechanism lays the foundation of DLT system.
- Communications between DLT nodes and perhaps systems via events and secure protocols.
- Crypto services functions which includes privacy protection, encryption, digital signature and other capabilities to ensure security compliance and tampering resistance of DLT system.
- Smart contracts running in a secure runtime can automatically implement scheduled.

The DLT Platform layer connects hardware or network infrastructure provided by the Infrastructure layer, to relevant functional support services in the API layer. In detail, the capabilities supported by the DLT Platform Layer includes:
- Secure runtime
- Smart contract
- Ledger
- Transaction System Membership Services State Management Consensus Mechanism
- Event Distribution
- Crypto Services
- Secure Inter Node Communications

## Secure Runtime

During runtime, a transaction may invoke smart contract functions requiring a secure environment. A secure runtime environment is a hosting environment for server-side DLT business logic. An example is the use of a secure container that contains a set of signed runtime components such as a secure operating system, libraries for DLT-supported programming languages, their respective runtimes, and the like.

## Smart Contract

A Smart contract is a distributed application running on and distributed with the distributed ledger. It represents more the process of agreeing on an outcome than its legal status. Its outcome may or may not be legally binding.

Smart contracts (also termed chaincode, programmable asset or programmable contract) are instantiated as computer programs that execute in a secure environment within the DLT platform of any node in the DLT system, when a user sends a transaction of a particular type to the DLT system.

## Ledger

A ledger is an information store which keeps a final and definitive record of (business) transactions.
A ledger includes data store capabilities. Data Storage function supports writing and query of various types of data, generated during the operation of the DLT system, such as the ledger, transaction information, etc. Technical implementation can be relational database, key-value pair database, file database, and so on. It should support data fragmentation and routing capabilities where database sharding is supported.

## Transaction System

The transaction system is the component that manages the addition of transactions to the ledger.

## Membership Services

Membership Services are services that manage the identity, privacy, confidentiality and auditability within the DLT system. Membership services only apply to permissioned DLT systems, like Alastria.

## State Management

The state management component keeps track of the state of assets which are held on the ledger, updating that state when new transactions are committed to the ledger.

## Consensus Mechanism

Consensus is a set of rules and procedures that allow the DLT system to maintain and update the distributed ledger and to ensure the trustworthiness of the records in the ledger - i.e. their reliability, authenticity and accuracy.
Consensus mechanisms are implementations by which consensus is achieved in DLT systems. There are many alternative consensus mechanisms in use in different DLT systems. Examples of consensus mechanisms include Delegated Proof-of-Stake, Paxos algorithm, Practical Byzantine Fault Tolerance, Proof-of-Authority, Proof-of-Burn, Proof-of-Capacity, Proof-of-ownership, Proof-of-stake, Zero knowledge proof, Proof-of-work.

## Event Distribution

The event distribution component handles the distribution of events generated within the DLT platform. An example is an event generated by the execution of a smart contract, which might be used by a user application to signal the completion of a transaction to the end user.

## Crypto Services

The Cryptographic Services component provides the DLT system with access to the necessary cryptographic algorithms, either directly or by providing an interface to hardware or software that implements the algorithms. Hash functions and digital signatures are examples of algorithms that are commonly used in DLT systems. Hash functions are often used to protect the ledger from modifications. Any change to information in the ledger will result in a computed hash that is different from the hash that was previously computed and stored for the ledger. A new hash is computed each time a transaction is added to the ledger. Digital signatures ensure that the receiver receives the transactions without intermediate parties modifying or forging the contents of transactions, while also ensuring that the transactions originated from senders (signed with private keys) and not imposters.

## Secure Inter-Node Communication

The secure inter-node communication component handles communication between nodes over the network, enabling the operation of the distributed ledger.
The inter-node protocol, also called the backbone protocol runs via this component.

# API layer

The API layer contains functions that provide reliable and efficient access to the DLT system for applications, users and non-DLT systems, by calling functional components in the DLT Platform layer, and provides unified access and node management. The API layer can enable increased performance by facilitating efficient cache, reliable storage, load balancing, and provide users with reliable and efficient access capabilities.
We can distinguish three different types of APIs.

## External Interfaces

Off-chain access services provide secure means to access capabilities outside the DLT system such as trusted data sources or functions.

## User API

Application programming interface that provides access to domain specific function meant to accomplish some business purpose (for the business user).

## Admin API

Application programming interface that provides access to administrator and operator functions.

# User layer

User layer contains functions to enable DLT customers to interact with DLT functions, DLT operators, and administrative functions. User layer can also communicate to other layers to provide support for DLT cross-layer functions.

## User Applications

User Applications are applications which run separately from the DLT systems that acts as a client to the DLT system, used by users, usually to perform domain specific or applications specific functions.

## Administration Applications

Administration Applications are applications which runs separately from the DLT systems that acts as a client to the DLT system, used by administrators supporting capabilities to maintain and/or update applications and systems.

# Non-DLT Systems Layer

The non-DLT systems layer contains systems outside the DLT system that a DLT system communicates with in order to accomplish its business goals. This includes:

## DLT Oracles
A DLT oracle is a trusted service designed to supply external data to a DLT system.

## Non DLT Applications

Non-DLT applications are any applications outside the DLT system with which the DLT system communicates, either to send or receive data. An example is a Core Banking System connected to a Smart Contract that tokenizes fiat money.

## Off Ledger Data

Off-Ledger data is any data store outside the DLT system that can hold data that relates to the DLT system in some way. An example might be a database holding additional data relating to transactions held on the ledger.
Off-Ledger Data is a critical component needed to implement proper data privacy functions.




# Technical Architecture

1. ARQUITECTURA TÉCNICA
    1. General
        1. Plataforma
        2. Estructura
        3. Arquitectura Lógica Nodos
        4. Capa de comunicación
        5. Capa de Servicios
        6. Capa de Datos
        7. Capa de Conectividad
        8. Puertos conocidos

    1. Entornos

        1. Entorno Desarrollo (descripción/características)
        1. Equipo (máquina) de desarrollo (recomendaciónes)
        1. Proceso de desarrollo
        1. Proceso de Pruebas (descripción/características)
        1. Entornos Preproducción/Producción (descripción/características)
        1. Acceso usuario
        1. Estimación del Sizing Nodos por tipos de nodo
        1. Base de datos
        1. Almacenamiento
        1. Servidor de aplicaciones
        1. Alta disponibilidad

1. ARQUITECTURA DE SEGURIDAD
    1. General
        1. Roles
        2. Seguridad acceso a Fuentes de Datos
        3. Configuración de cifrado
        4. Almacén de Credenciales
        5. Seguridad transacciones
        6. Datos - Cifrado
        7. Datos - Privacidad
        8. Datos - Auditoría
        9. Red - Autenticación
        10. Red - Gestión
        11. Red - Autorizaciones
        12. Puertos conocidos
        13. Bastionado de equipos y electrónica de red
        14. Filtrado de tráfico

    1. Certificados
        1. Gestión de certificados
        2. Autoridad de Certificación
        3. Firma Digital de documentos
        4. Certificados para Servidores Web

1. ARQUITECTURA DE INTEGRACION
    1. Interacción de Alastria con sistemas backend/core de negocio
    2. Interacción de Alastria con otras redes (interoperabilidad)
    3. Interacción de Alastria con otros servicios (por ejemplo almacenamiento)
    4. Interacción con otras tecnologías
    5. Conexiones con Bases de Datos (por ejemplo cache de transacciones)
    6. APIs para acceder a los servicios proporcionados
    7. Protocolos de conexión/integración Soportados
    8. Intercambio de Ficheros (por ejemplo de configuración de los nodos)

1. ARQUITECTURA DE DESARROLLO
    1. General
        1. Estructura de Aplicaciones/smart contract
        2. Lenguaje de desarrollo
        3. Metodología de Desarrollo
        4. Modelo de Datos
        5. Interfaz de usuario
        6. Tecnologías de Creación de Interfaz de Usuario
        7. Control de Versiones
        8. Paso entre entornos
        9. Jobs

    1. Pruebas
        1. Unitarias de nodo
        1. Integradas de nodo
        1. Integradas de red
        1. Stress de nodo
        1. Stress de red
        1. Seguridad

1. INSTALACIÓN Y CONFIGURACIÓN DE NODOS
    1. Requerimientos previos a la instalación
    1. Instalación de Nodo Alastria
    1. Descarga de los componentes
    1. Instalación de los componentes
    1. Asignación de Roles
    1. Alta del nuevo nodo en Validadores o Regulares
    1. Conectividad con Nodos de terceros

1. POLITICA DE DESPLIEGUE Y MANTENIMIENTO
    1. Despliegue
        1. Tareas previas de despliegue
        2. Gestión de incidencias
        3. Gestión Incidencias de Usuario
        4. Gestión Incidencias de Producto
        5. Políticas de actualización
        6. Aplicación de parches
        7. Plan de cambio de versión

    1. Operación
        1. ANS e Indicadores de operación
        2. Procedimientos de Back Up

    1. Procedimientos rutinarios
        1. Logs: Revisión/Protección/Retención
        2. Auditoria

    1. Monitorización
        1. Monitorización común en los elementos de red
        2. Monitorización de la capacidad de los recursos
        3. Monitorización de la disponibilidad
        4. Transferencia de ficheros
        5. Conexiones B2B
        6. Certificados digitales
        7. Servidores Web
        8. Conexiones de usuarios desde el exterior
        9. Servidores y Electrónica de Red
        10. Control de acceso
        11. Acceso de administración a los SSII
        12. Usuarios especiales
        13. Entorno LAN
        14. Informes de gestión de vulnerabilidades
