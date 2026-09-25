# ACTIVIDAD-6
a)
Métrica para la Evaluación del Desempeño de Usuarios en CoinkPara evaluar y calificar el desempeño de los usuarios contenidos en la muestra de depósitos en las máquinas Oink (depositos_oink.csv), se diseñó un modelo analítico denominado Coink Score. Este indicador ponderado se construyó adaptando la metodología RFM (Recencia, Frecuencia y Valor Monetario), ampliamente utilizada en ciencia de datos para medir el compromiso y valor de los clientes.En una plataforma de alcancías digitales y terminales físicas IoT, un "buen usuario" no se define únicamente por depositar grandes sumas de dinero, sino por mantener un hábito de ahorro constante, un uso recurrente de la infraestructura y una alta retención en el tiempo.Definición y Ponderación de las Sub-Métricas (Escala 0 a 100)El Coink Score consolida cuatro componentes clave calculados a partir de los datos históricos de depósitos. Para garantizar una calificación justa e independiente de la escala de medición de cada variable, cada métrica se transforma a un percentil relativo entre 0 y 100:Recencia ($R_{score}$ - Ponderación del 20%):Definición: Mide el número de días transcurridos desde el último depósito registrado por el usuario hasta la fecha de corte del análisis.Justificación: Evalúa el riesgo de abandono (churn). A menor número de días inactivo, mayor es el puntaje invertido asignado.Frecuencia ($F_{score}$ - Ponderación del 30%):Definición: Representa el número total de transacciones de depósito realizadas en las máquinas Oink.Justificación: Es el reflejo directo del hábito de ahorro y la interacción continua con los dispositivos físicos de la compañía.Monto Total Depositado ($M_{score}$ - Ponderación del 35%):Definición: Suma acumulada de dinero ingresado a la cuenta del usuario a través de las máquinas ($).Justificación: Representa el volumen financiero directo aportado por el usuario a la captura de saldos de la empresa.Ticket Promedio ($T_{score}$ - Ponderación del 15%):Definición: Valor promedio ahorrado en cada visita o transacción ($/\text{depósito}$).Justificación: Mide la eficiencia operativa de las visitas al punto físico. A mayor depósito promedio, mayor rendimiento por transacción.Formulación Matemática de la Calificación GlobalPara homogenizar las métricas y calcular el puntaje final de cada usuario, se aplican las siguientes etapas:Estandarización por Percentiles:$$\text{Métrica}_{score} = \text{Percentil}(\text{Valor de la Variable}) \times 100$$(Para la Recencia, la escala se invierte: $R_{score} = (1 - \text{Percentil}(\text{Días})) \times 100$)Cálculo del Coink Score:$$\text{Coink Score} = (0.20 \times R_{score}) + (0.30 \times F_{score}) + (0.35 \times M_{score}) + (0.15 \times T_{score})$$Segmentación y Clasificación de Usuarios:Ahorrador Campeón (80 - 100 pts): Usuarios con excelente frecuencia, altos montos depositados e interacción reciente.Ahorrador Frecuente (60 - 79 pts): Usuarios con un hábito de uso constante pero con montos o tickets moderados.Usuario Ocasional (40 - 59 pts): Usuarios de uso esporádico o con depósitos de menor valor.Usuario en Riesgo / Inactivo (< 40 pts): Usuarios con largos periodos de inactividad o un compromiso muy bajo con la plataforma.Estructura de Visualización Gráfica RequeridaPara sustentar estas métricas en la presentación del proyecto o en el tablero de control, se estructuran las siguientes dos gráficas principales:Histograma de Distribución del Coink Score: Permite observar la concentración de la población de usuarios a lo largo de la escala de 0 a 100 puntos, identificando si la muestra tiende a ser activa o inactiva.Gráfica de Proporción por Segmentos (Torta/Dona): Muestra el porcentaje de usuarios clasificados en las cuatro categorías (Campeones, Frecuentes, Ocasionales y En Riesgo) para orientar decisiones de marketing y fidelización.

b)
Una base de datos relacional (RDBMS) organiza la información en tablas estrictas compuestas por filas y columnas, interconectadas entre sí mediante claves (primary keys y foreign keys). Utilizan el lenguaje SQL y garantizan integridad de los datos bajo las propiedades ACID (Atomicidad, Consistencia, Aislamiento y Durabilidad). Son ideales para estructurar datos donde las relaciones entre entidades son claras y no cambian con frecuencia.

Una base de datos no relacional (NoSQL) almacena la información sin un esquema fijo, utilizando formatos flexibles como documentos (JSON/BSON), clave-valor, grafos o columnas anchas. Permiten escalar horizontalmente con facilidad y manipular volúmenes masivos de datos variados o no estructurados sin la rigidez de las tablas tradicionales.

Análisis y selección para el ejercicio propuesto
Para el proyecto del chatbot del grupo de clase, la opción superior y más adecuada es una base de datos relacional.

Fundamentación de la elección:
Estructura fija y predecible de los datos:
Los perfiles del grupo poseen una estructura idéntica y bien definida por campos específicos:

Compañeros: Nombre, película favorita, canción preferida, deporte, comida e intensidad/materia de interés.

Categorías: Películas, Música, Deportes, Comidas, Materias.

Esta uniformidad encaja directamente en una estructura relacional de tablas (por ejemplo, Estudiantes, Gustos, Categorías), eliminando la necesidad de esquemas dinámicos o variables que justificaran el uso de NoSQL.

Relaciones directas y consultas estructuradas:
El chatbot necesita responder preguntas cruzadas del tipo: ¿A quiénes les gusta el fútbol? o ¿Qué materia le gusta al Compañero 3?. En una base de datos relacional, estas consultas se resuelven de forma eficiente mediante operaciones simples de selección y cruce (JOIN):

Consistencia de la información e integridad referencial:
Si un integrante actualiza un gusto o se añade un nuevo parámetro al grupo, las reglas de integridad referencial de un modelo relacional evitan duplicaciones, inconsistencias o datos huérfanos.

Escala y volumen del proyecto:
El ejercicio maneja un volumen de datos pequeño y acotado (los datos de 5 integrantes). La principal ventaja de NoSQL —el escalamiento horizontal masivo para millones de registros por segundo— no aporta ningún beneficio en este contexto y agregaría complejidad innecesaria en la gestión de consultas.

Una base de datos relacional ofrece la estructura precisa, la integridad de datos y la capacidad de consulta relacional requeridas para soportar la información del grupo de forma ordenada y eficiente.
<img width="469" height="156" alt="image" src="https://github.com/user-attachments/assets/aeeb0fdf-e33b-4390-8c33-e9cbbcf14426" />

c)
1. Explicación Detallada del Diagrama de Flujo (Proceso Completo)
El ciclo de vida del dinero desde su formato físico hasta su digitalización y eventual retiro se divide en cuatro grandes etapas secuenciales e interconectadas:

A. Fase de Autenticación, Ingreso y Lectura Física (Hardware OINK)
Autenticación e Inicio de Sesión: El usuario interactúa primeramente con la pantalla táctil o la cámara del OINK. Puede identificarse mediante la digitación de su documento de identidad o mediante la lectura de un código QR dinámico generado desde su aplicación móvil. Este paso vincula unívocamente la sesión del dispositivo con la cuenta del usuario en la base de datos central.
Recepción y Movimiento Mecánico: El usuario introduce la moneda por la ranura superior. Internamente, un mecanismo de rampa e inclinación calibrada hace rodar la moneda a una velocidad constante para garantizar una lectura uniforme por parte de los sensores.
Validación Multisensorial: La moneda atraviesa un conjunto de sensores de alta precisión:
Sensores Ópticos / Fotocélulas: Miden el diámetro exacto y detectan imperfecciones físicas o perforaciones.
Sensores Inductivos / Electromagnéticos: Generan un campo magnético de alta frecuencia para evaluar la composición metálica, el grosor y la conductividad eléctrica del material.
Decisión de Aceptación o Rechazo:
Si la moneda cumple con los patrones predefinidos: Se activa un solenoide electromecánico que abre la compuerta hacia el canal primario, depositando el dinero en la bóveda de seguridad interna. Un contador lógico incrementa la variable local de dinero aceptado.
Si la moneda es ilegible, falsa o no corresponde a las denominaciones legales: El solenoide permanece cerrado, dirigiendo la moneda hacia el canal de rechazo y devolviéndola en la bandeja exterior para el usuario.
B. Fase de Procesamiento Local y Transmisión Cifrada (IoT & Middleware)
Finalización de la Sesión: Una vez depositadas todas las monedas, el usuario presiona el botón "Finalizar" en la pantalla (o el sistema activa un temporizador de inactividad que cierra la sesión automáticamente).
Generación del Payload: El microcontrolador embebido estructura un paquete de datos cifrado (payload) que contiene la identificación del dispositivo (ID_Dispositivo), el token de la sesión (ID_Usuario), la fecha/hora (Timestamp) y el desglose de monedas depositadas con el monto total acumulado.
Transmisión de Red: El dispositivo envía la petición cifrada mediante protocolos de comunicación segura (HTTPS/TLS o WebSockets) utilizando conexiones celulares (4G/LTE) o redes Wi-Fi dedicadas hacia la API del servidor central (Backend).
C. Fase de Billetera Digital y Sincronización en el Aplicativo Móvil
Registro en el Libro Mayor (Ledger): El servidor Backend autentica la firma criptográfica enviada por el OINK. Una vez validada, ejecuta una transacción en la base de datos relacional/Ledger para evitar la duplicidad de abonos, actualizando la variable Saldo_Disponible del usuario.
Sincronización en Tiempo Real: El backend emite una notificación Push y envía una señal mediante Webhooks o sockets hacia la aplicación móvil del usuario.
Visualización en la App: La interfaz de usuario (UI) actualiza el saldo visualmente de manera inmediata, genera un recibo digital detallado con el desglose de las monedas ingresadas e incrementa las metas de ahorro o beneficios dentro del aplicativo.
D. Fase de Solicitud y Ejecución de Retiros
Configuración de la Solicitud: Si el usuario decide disponer de su saldo, ingresa al módulo de retiros en la app móvil y define el monto exacto a debitar.
Selección del Método de Retiro:
Transfiriendo a entidades financieras: A través de pasarelas de pago como PSE, Nequi, Daviplata o transferencias bancarias directas.
Retiro en efectivo: Generando un código PIN dinámico con tiempo de caducidad para cobrar en corresponsales bancarios o cajeros automáticos aliados.
Validación de Seguridad (Doble Factor - 2FA): Para autorizar la salida del dinero, la app exige un segundo factor de autenticación, como la lectura de biometría (huella dactilar o reconocimiento facial) o el ingreso de una clave dinámica OTP enviado por SMS/Correo.
Efectuación del Débito y Desembolso: El servidor autentica el 2FA, descuenta el valor de la variable Saldo_Disponible en la billetera y liquida la instrucción consumiendo la API de la entidad financiera o aliada encargada del desembolso de los fondos.
2. Funcionamiento del Dispositivo Físico (Hardware OINK)
El quiosco o alcancía inteligente OINK opera como un terminal de punto de venta (POS) inverso o punto de captura física de efectivo. Sus funciones principales se dividen en tres áreas:

Gestión Mecánica y de Entrada:
Posee una ranura protegida con un mecanismo anti-pesca (anti-fishing) para evitar que las monedas sean extraídas con hilos u objetos delgados tras haber sido leídas. La rampa interna guía las monedas por gravedad asegurando una trayectoria fluida hacia los sensores.
Procesamiento de Borde (Edge Computing):
El dispositivo cuenta con un procesador embebido encargado de interpretar las señales analógicas de los sensores en tiempo real. En lugar de enviar una señal al servidor central por cada moneda que cae (lo que saturaría la red), el dispositivo procesa el conteo localmente durante toda la sesión y solo transmite el resultado consolidado al momento de cerrar la transacción.
Bóveda de Alta Seguridad:
Las monedas validadas caen por gravedad a una caja fuerte blindada ubicada en la parte inferior del equipo. Esta bóveda cuenta con sensores de manipulación (tamper switches) que emiten alertas de seguridad en tiempo real al servidor en caso de intentos de apertura no autorizada o golpes.
3. Integración Sistémica de las Variables
El correcto funcionamiento del ecosistema OINK depende de la constante comunicación y actualización de variables a través de sus distintos componentes:

<img width="512" height="307" alt="image" src="https://github.com/user-attachments/assets/a7ef439c-a3af-413c-8403-0d8d77e34d9e" />

1. Sistema Kiosco Terminal para Depósito y Conversión de Efectivo Físico a Saldo Digital
Plataforma / ID de Patente: USPTO (US Patent US10453298B2)

Campo: Finanzas / Fintech / Retail

Componentes de Hardware: Aceptador y validador óptico/magnético de monedas y billetes, microcontrolador de almacenamiento local y módulo de comunicación IoT (4G/5G).

Relación con Bases de Datos:

Emplea una Base de Datos Relacional (RDBMS) en la nube con soporte de transacciones ACID.

Cada depósito registra de forma atómica: el valor de la denominación, fecha/hora (timestamp), ID del terminal y estado de la cuenta.

Aplica replicación de bases de datos para garantizar la consistencia del saldo disponible del usuario en tiempo real sin riesgo de pérdidas de datos.

Utilidad: Automatizar la recepción de efectivo físico y reflejar de inmediato su equivalente en una billetera digital, eliminando el manejo manual del dinero.

2. Dispositivo Embebido de Telemetría para Vehículos con Base de Datos de Borde (Edge Database)
Plataforma / ID de Patente: Espacenet / WIPO (WO2021183201A1)

Campo: Logística / Internet de las Cosas (IoT)

Componentes de Hardware: Sensores CAN-bus, acelerómetros, receptor GPS, memoria flash de estado sólido y procesador de bajo consumo.

Relación con Bases de Datos:

Utiliza una Base de Datos Embebida de Series de Tiempo (Time-Series DB) dentro del propio chip del hardware (como SQLite o LevelDB).

Almacena datos locales si el vehículo pierde conectividad a internet. Al restablecer la red, ejecuta un proceso de sincronización por lotes (batch sync) con la base de datos central.

Utilidad: Garantizar que las métricas operativas de flotas (velocidad, consumo, ubicación) no se pierdan cuando los dispositivos operan sin señal.

3. Red de Puntos de Venta (POS) Inteligentes con Cifrado P2PE y Tokenización en Base de Datos
Plataforma / ID de Patente: Lens Patents (US9842328B2)

Campo: Pasarelas y Medios de Pago

Componentes de Hardware: Lector de tarjetas con chip EMV/NFC, Módulo de Seguridad de Hardware (HSM) integrado y microprocesador cifrado.

Relación con Bases de Datos:

Se conecta con Bases de Datos Relacionales Distribuidas mediante canales cifrados TLS.

La base de datos almacena tokens financieros en lugar de datos sensibles de la tarjeta (cumplimiento de la norma PCI-DSS), relacionando cada token con las claves públicas/privadas del hardware transaccional.

Utilidad: Evitar que los datos de las tarjetas de crédito o débito sean interceptados en tránsito o expuestos en caso de filtraciones en la base de datos del comercio.

4. Dispensador Farmacéutico Mecatrónico con Verificación Biométrica e Integración a Registros Médicos
Plataforma / ID de Patente: Patentscope (WO2019055910A1)

Campo: Salud Digital (HealthTech)

Componentes de Hardware: Lector dactilar/óptico biométrico, actuadores mecánicos de dispensado y lector de códigos de barras/QR.

Relación con Bases de Datos:

Se conecta con una Base de Datos NoSQL Orientada a Documentos o Grafos (como MongoDB o Neo4j).

Asocia la huella dactilar capturada por el hardware con la historia clínica del paciente, las prescripciones activas y el inventario físico disponible en las celdas del dispensador.

Utilidad: Prevenir la entrega errónea o no autorizada de medicamentos controlados y actualizar el inventario médico en tiempo real tras cada dispensación.

5. Medidor Inteligente de Redes Eléctricas (Smart Grid) con Base de Datos de Métricas Masivas
Plataforma / ID de Patente: USPTO (US9274148B2)

Campo: Servicios Públicos / Utilities

Componentes de Hardware: Transformadores de corriente, relés de corte remoto, unidad de microprocesamiento y módem de radiofrecuencia (LoRaWAN/NB-IoT).

Relación con Bases de Datos:

Envía un flujo constante de telemetría a Bases de Datos Distribuidas NoSQL de Alta Escala (como Apache Cassandra o AWS Timestream).

Soporta millones de escrituras concurrentes por segundo para almacenar históricos de consumo minuto a minuto.

Utilidad: Permitir a las empresas de energía detectar caídas del servicio, prevenir fraudes, equilibrar la carga de la red y facturar tarifas dinámicas según el uso.

1. Amazon Web Services (AWS)
Es la plataforma de nube de Amazon. Ofrece una amplia gama de bases de datos completamente administradas, adaptadas a diversos modelos de datos.

Estructuradas / Relacionales:

Amazon RDS: Servicio administrado que soporta motores tradicionales como PostgreSQL, MySQL, MariaDB, Oracle y SQL Server.

Amazon Aurora: Motor relacional de alto rendimiento compatible con MySQL y PostgreSQL, diseñado para escala empresarial con replicación automática.

No Estructuradas / No Relacionales:

Amazon DynamoDB: Base de datos NoSQL de clave-valor y documentos que ofrece latencias de un solo dígito en milisegundos a cualquier escala.

Amazon DocumentDB: Base de datos NoSQL administrada compatible con cargas de trabajo de MongoDB.

Amazon S3: Almacenamiento de objetos (Object Storage) para guardar volúmenes masivos de datos no estructurados (imágenes, archivos, data lakes).

2. Google Cloud Platform (GCP)
La nube de Google destaca por su infraestructura orientada al análisis masivo de datos y aprendizaje automático.

Estructuradas / Relacionales:

Cloud SQL: Servicio administrado para bases de datos relacionales como MySQL, PostgreSQL y SQL Server.

Cloud Spanner: Base de datos relacional con escalabilidad horizontal global y consistencia fuerte de datos.

No Estructuradas / No Relacionales:

Bigtable: Base de datos NoSQL de columna ancha ideal para grandes volúmenes de datos analíticos e IoT.

Firestore: Base de datos NoSQL orientada a documentos con sincronización en tiempo real para aplicaciones móviles y web.

Google Cloud Storage (GCS): Almacenamiento de objetos de alta durabilidad para datos no estructurados.

3. Microsoft Azure
La plataforma en la nube de Microsoft está altamente integrada con el entorno corporativo y herramientas de desarrollo tradicionales.

Estructuradas / Relacionales:

Azure SQL Database: Servicio administrado PaaS basado en el motor Microsoft SQL Server.

Azure Database for PostgreSQL / MySQL: Servicios administrados de código abierto.

No Estructuradas / No Relacionales:

Azure Cosmos DB: Base de datos NoSQL distribuida globalmente y multimodelo (admite APIs para documentos, Cassandra, Gremlin y MongoDB).

Azure Blob Storage: Almacenamiento masivo para objetos y datos no estructurados (archivos multimedia, logs, respaldos).

4. Oracle Cloud Infrastructure (OCI)
Especializada en cargas de trabajo de misión crítica para grandes empresas y sistemas financieros.

Estructuradas / Relacionales:

Oracle Autonomous Database: Base de datos relacional con inteligencia artificial integrada que automatiza el parcheo, afinación y escalamiento (para procesamiento transaccional o Data Warehouse).

MySQL HeatWave: Motor relacional en memoria optimizado para analítica y transacciones combinadas.

No Estructuradas / No Relacionales:

Oracle NoSQL Database Cloud Service: Almacenamiento enfocado en clave-valor y documentos JSON de alta velocidad.

OCI Object Storage: Almacenamiento no estructurado distribuido.

5. IBM Cloud
Enfocada en entornos de nube híbrida, seguridad avanzada y cumplimiento regulatorio en sectores como la banca y la salud.

Estructuradas / Relacionales:

IBM Db2 on Cloud: Base de datos relacional empresarial diseñada para transacciones complejas y análisis corporativo.

IBM Cloud Databases for PostgreSQL / MySQL: Infraestructura administrada para motores abiertos.

No Estructuradas / No Relacionales:

IBM Cloudant: Base de datos NoSQL administrada orientada a documentos JSON, basada en Apache CouchDB.

IBM Cloud Object Storage (COS): Almacenamiento no estructurado altamente escalable y cifrado.

