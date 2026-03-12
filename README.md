# Guía de Estudio AWS Certified Cloud Practitioner (CLF-C02)


## ☁️ Conceptos de la nube

### **A. Agilidad (Agility)**
* **Concepto:** Es la **velocidad de innovación**.
* **Cómo recordarlo:** En la nube, un servidor se crea en segundos, no en semanas.
* **Pregunta de examen típica:** "¿Qué beneficio permite a los desarrolladores experimentar y fallar rápido con bajo costo?". **Respuesta: Agilidad.**

### **B. Elasticidad (Elasticity)**
* **Concepto:** Es la capacidad de **ajustar los recursos automáticamente** según la demanda (subir y BAJAR).
* **Cómo recordarlo:** Como un **chicle**. Se estira cuando hay mucha gente (Black Friday) y se encoge cuando no hay nadie (madrugada) para ahorrar dinero.
* **Servicio clave:** **Amazon EC2 Auto Scaling**.

### **C. Alta Disponibilidad (High Availability - HA)**
* **Concepto:** Asegurar que el sistema esté funcionando el mayor tiempo posible **sin interrupciones**.
* **Cómo recordarlo:** **Redundancia**. Si algo se rompe, hay otro igual listo para sustituirlo.
* **Pregunta de examen típica:** "¿Cómo se logra la HA en AWS?". **Respuesta: Desplegando en múltiples Zonas de Disponibilidad (Multi-AZ).**

### **D. Alcance Global (Global Reach)**
* **Concepto:** Capacidad de desplegar recursos y contenido en múltiples ubicaciones geográficas para estar físicamente cerca de los usuarios finales.
* **Pregunta de examen típica:** "¿Qué beneficio de AWS permite a una empresa desplegar una aplicación a usuarios de todo el mundo con baja latencia en cuestión de minutos?". **Respuesta: Alcance Global (vía Regiones y Edge Locations).**

### **E. Economía de Escala (Economies of Scale)**

* **Concepto:** Es el beneficio de que AWS, al tener millones de clientes, compra hardware en cantidades masivas, lo que reduce sus costos operativos. AWS traslada esos ahorros a los clientes en forma de **precios más bajos**.
* **Pregunta de examen típica:** "¿Por qué AWS puede reducir los precios de sus servicios periódicamente para sus clientes?". **Respuesta: Debido a las economías de escala.**

### **F. Pago por uso (Pay-as-you-go / Modelo de Consumo)**

* **Concepto:** Método de facturación donde solo pagas por la cantidad exacta de recursos que utilizas, sin contratos a largo plazo ni inversiones iniciales.
* **Pregunta de examen típica:** "¿Qué característica de la nube de AWS permite a una empresa cambiar gastos de capital (CapEx) por gastos operativos (OpEx)?". **Respuesta: El modelo de precios de pago por uso.**

### **Tabla Resumen**

| Concepto | **Palabras Clave (Disparadores)** | **Escenario Típico del Examen** | **Respuesta Ganadora** |
| --- | --- | --- | --- |
| **Agilidad** | *Innovación, rapidez, experimentar, fallar rápido, bajo costo.* | "La empresa quiere probar nuevas ideas sin gastar mucho dinero ni esperar meses..." | **Agilidad** |
| **Elasticidad** | *Auto Scaling, demanda variable, picos de tráfico, estirar/encoger.* | "Una web de flores tiene mucho tráfico en San Valentín pero poco el resto del año..." | **Elasticidad** |
| **Alta Disponibilidad** | *Redundancia, Multi-AZ, sin interrupciones, tiempo de actividad.* | "¿Cómo se asegura que una aplicación siga funcionando si un centro de datos falla?" | **Alta Disponibilidad** |
| **Alcance Global** | *Baja latencia, usuarios en todo el mundo, proximidad, milisegundos.* | "Una empresa en España quiere que sus clientes en Australia vean la web rápido..." | **Alcance Global** |
| **Economía de Escala** | *Precios más bajos, volumen, pagar menos al crecer AWS.* | "¿Por qué AWS puede ofrecer precios tan bajos a sus clientes?" | **Economía de Escala** |
| **Pago por uso** | *OpEx, gasto variable, sin inversión inicial, eliminar CapEx.* | "La empresa quiere dejar de comprar servidores físicos y pagar solo por lo consumido..." | **Modelo de Consumo** |

------------------------------------------------------------

### **Servicios de Protección de Recursos**

#### **1. Amazon Inspector**

* **Concepto:** Servicio que busca **vulnerabilidades** y desviaciones de las mejores prácticas en tus recursos.
* **Pregunta de examen típica:** "¿Qué servicio automatiza la evaluación de seguridad de las instancias **EC2** para encontrar vulnerabilidades de software?". **Respuesta: Amazon Inspector.**

#### **2. Amazon GuardDuty**

* **Concepto:** Detección de **amenazas inteligentes** que monitoriza continuamente tu cuenta en busca de actividad maliciosa.
* **Pregunta de examen típica:** "¿Qué servicio utiliza **Machine Learning** para detectar actividades no autorizadas o inusuales en las cuentas de AWS?". **Respuesta: Amazon GuardDuty.**

#### **3. AWS Security Hub**

* **Concepto:** Un lugar central para ver y gestionar todas tus alertas de seguridad y comprobar si cumples con las normas (compliance).
* **Pregunta de examen típica:** "¿Qué servicio proporciona una **vista centralizada** y consolidada de las alertas de seguridad de varios servicios de AWS?". **Respuesta: AWS Security Hub.**

#### **4. AWS Shield**

* **Concepto:** Protección gestionada contra ataques de denegación de servicio distribuido (**DDoS**).
* **Pregunta de examen típica:** "¿Qué servicio protege las aplicaciones contra ataques **DDoS**?". **Respuesta: AWS Shield.**

#### **5. AWS WAF (Web Application Firewall)**

* **Concepto:** Un cortafuegos que protege tus aplicaciones web de ataques comunes que intentan explotar vulnerabilidades en el código (Capa 7 del modelo OSI).
* **Pregunta de examen típica:** "¿Qué servicio utilizaría para bloquear direcciones IP específicas o ataques de inyección SQL que intentan acceder a su aplicación web?". **Respuesta: AWS WAF.**

#### **6. Amazon Macie**

* **Concepto:** Servicio de seguridad y privacidad de datos que utiliza **Machine Learning** para descubrir, clasificar y proteger datos sensibles almacenados en **Amazon S3**.
* **Pregunta de examen típica:** "¿Qué servicio le ayuda a identificar y proteger automáticamente la información de identificación personal (**PII**) almacenada en los cubos de **Amazon S3**?". **Respuesta: Amazon Macie.**

#### **Tabla Resumen**

| Si el examen dice / menciona... | El concepto o problema clave es... | La respuesta correcta es... |
| --- | --- | --- |
| **Vulnerabilidades / Parches / Software** | **Inspeccionar** internamente instancias EC2, imágenes de contenedor o funciones Lambda. | **Amazon Inspector** |
| **Detección de Amenazas / Actividad inusual** | **Vigilancia** inteligente con ML/IA (alguien mina criptos, IP maliciosas, cuenta comprometida). | **Amazon GuardDuty** |
| **Ataque DDoS / Tráfico Masivo** | **Protección** contra avalanchas de tráfico que buscan tumbar el servicio. | **AWS Shield** |
| **SQL Injection / XSS / Capa 7** | **Filtrar** tráfico web malicioso que intenta hackear el código de la página. | **AWS WAF** |
| **Datos Sensibles / DNI / PII / Tarjetas** | **Privacidad** y clasificación de datos personales dentro de **Amazon S3**. | **Amazon Macie** |
| **Vista Centralizada / Dashboard / Cumplimiento** | **Consolidar** hallazgos de todos los servicios de seguridad en un solo panel. | **AWS Security Hub** |

### **Diferencia Crítica para no fallar:**

* **Inspector** busca problemas **dentro** de tus servidores (vulnerabilidades).
* **GuardDuty** busca ataques **en tu cuenta** (actividad sospechosa/hackers).
* **WAF** filtra **peticiones web** malas (Capa 7).
* **Shield** detiene **avalanchas de tráfico** (DDoS).

**¿Dónde está el problema?**
* Si está **DENTRO** del servidor (software viejo): **Inspector**.
* Si está en los **DATOS** (S3): **Macie**.
* Si está en el **COMPORTAMIENTO** de la cuenta: **GuardDuty**.
  
**¿Qué tipo de ataque es?**
* Si es por **VOLUMEN** (DDoS): **Shield**.
* Si es por **CÓDIGO** (SQL/XSS): **WAF**.

------------------------------------------------------------

### **Pilares de Well-Architected**

| Pilar | ¿De qué trata realmente? | **Palabras Clave (Triggers del examen)** | **Escenario Típico de Pregunta** |
| --- | --- | --- | --- |
| **Excelencia Operativa (Operational Excellence)** | Ejecutar sistemas, monitorizar y **mejorar procesos**. | *Automatización, cambios pequeños y reversibles, "Infrastructure as Code" (IaC), documentar.* | "La empresa quiere automatizar sus despliegues y aprender de los fallos operativos..." |
| **Seguridad (Security)** | Proteger datos, sistemas y activos. | *Trazabilidad (logs), cifrado, incidentes, "mínimo privilegio", protección de datos.* | "¿Qué pilar se enfoca en asegurar que solo los usuarios autorizados accedan a los recursos?" |
| **Fiabilidad (Reliability)** | **Recuperarse** de fallos y mitigar interrupciones. | *Recuperación automática, probar fallos, escalar horizontalmente, disponibilidad.* | "Un sistema debe seguir funcionando incluso si un centro de datos entero falla..." |
| **Eficiencia del Rendimiento (Performance Efficiency)** | Usar los recursos **adecuados** para la carga. | *Selección de tipos de recursos, democratizar tecnologías avanzadas, ir global en minutos.* | "La empresa quiere usar Serverless (Lambda) para no gestionar servidores y mejorar la velocidad..." |
| **Optimización de Costos (Cost Optimization)** | Evitar gastos innecesarios. | *Modelo de consumo, medir eficiencia, servicios gestionados, dejar de gastar en centros de datos.* | "¿Qué pilar recomienda analizar el gasto para pagar solo por lo que realmente se necesita?" |
| **Sostenibilidad (Sustainability)** | Minimizar el **impacto ambiental**. | *Huella de carbono, maximizar utilización, reducir recursos desperdiciados.* | "¿Qué pilar se centra en la eficiencia energética y el impacto ambiental a largo plazo?" |

1. **¿Fiabilidad o Excelencia Operativa?**
* Si la pregunta habla de que el sistema **sobreviva a un fallo**: es **Fiabilidad**.
* Si la pregunta habla de **cómo el equipo humano gestiona** el sistema o automatiza el código: es **Excelencia Operativa**.


2. **¿Rendimiento o Costo?**
* Si te piden la solución **más barata**: es **Costo**.
* Si te piden la solución que **mejor aproveche la tecnología** (aunque sea más cara): es **Rendimiento**.


3. **¿Seguridad o Fiabilidad?**
* Si el sistema se cae por un **hacker**: es **Seguridad**.
* Si el sistema se cae por una **inundación o exceso de tráfico**: es **Fiabilidad**.

Ejemplos de servicio de AWS para cada pilar:

* **Excelencia Operativa:** AWS CloudFormation (IaC).
* **Seguridad:** AWS IAM / KMS.
* **Fiabilidad:** Amazon EC2 Auto Scaling.
* **Rendimiento:** Amazon CloudFront (baja latencia).
* **Costo:** AWS Cost Explorer / Budgets.
* **Sostenibilidad:** Customer Carbon Footprint Tool.

------------------------------------------------------------

### ¿Qué es el AWS CAF?

Es un marco que ayuda a las empresas a crear un plan de acción para su transformación digital. Divide el proceso en **6 Perspectivas** y se enfoca en obtener **4 Resultados de Negocio**.

### Los 4 Resultados de Negocio (El "Por qué")

* **Reducción del riesgo empresarial:** No se trata solo de seguridad, sino de **resiliencia**. La nube permite recuperarse de desastres y evitar caídas de servicio (fiabilidad), lo que protege la reputación y las finanzas.
* **Mejora del rendimiento ESG (Social, Ambiental y Gobernanza):** Aquí es donde entra la **Sostenibilidad**. Al usar la infraestructura eficiente de AWS, las empresas reducen su huella de carbono y mejoran su transparencia de datos.
* **Aumento de los ingresos:** Permite crear productos nuevos y lanzarlos al mercado más rápido (**Time-to-market**). Si puedes experimentar barato y rápido, generas más dinero.
* **Aumento de la eficiencia operativa:** Automatizar tareas repetitivas y reducir el costo de mantener centros de datos físicos. El personal de TI deja de "mover cajas" y empieza a innovar.

### Las 6 Perspectivas del CAF (El "Cómo")

#### A. Perspectivas de Capacidades Empresariales (Enfocadas en estrategia)

1. **Negocios (Business):** Se asegura de que la inversión en la nube se alinee con los objetivos de la empresa. (ROI, casos de negocio).
2. **Personas (People):** Se enfoca en el cambio de cultura. Formación, nuevas habilidades y cómo organizar los equipos.
3. **Gobernanza (Governance):** Se ocupa de gestionar los programas de TI para minimizar riesgos y maximizar beneficios. (Gestión de carteras, cumplimiento).

#### B. Perspectivas de Capacidades Técnicas (Enfocadas en la implementación)

4. **Plataforma (Platform):** Cómo diseñar y optimizar la arquitectura en la nube (la parte técnica pura).
5. **Seguridad (Security):** Cómo proteger los datos, las identidades y cumplir con las normativas.
6. **Operaciones (Operations):** Cómo gestionar el día a día en la nube (monitorización, salud del sistema, soporte).

### Tabla Resumen

| Si la pregunta dice... | La respuesta es Perspectiva... |
| --- | --- |
| "Alinear TI con beneficios financieros" | **Negocios (Business)** |
| "Capacitación de empleados o cultura" | **Personas (People)** |
| "Arquitectura, escalabilidad, computación" | **Plataforma (Platform)** |
| "Cumplimiento normativo y gestión de riesgos" | **Gobernanza (Governance)** |
| "Incidentes, parches, gestión de servicios" | **Operaciones (Operations)** |
| "Cifrado, IAM, protección de datos" | **Seguridad (Security)** |

> **Nota importante:** No confundir el **CAF** (estrategia de adopción) con el **Well-Architected Framework** (diseño técnico de una carga de trabajo). El CAF es para "toda la empresa", el Well-Architected es para "una aplicación específica".

------------------------------------------------------------

### Las 7 Rs: Estrategias de Migración

Estas son las rutas que puede tomar una aplicación. Van desde "no hacer nada" hasta "rehacerlo todo".

| Estrategia | ¿Qué es? | Cuándo usarla (Palabras clave) |
| --- | --- | --- |
| **Rehost** (Lift & Shift) | Mover la aplicación tal cual a una instancia EC2. | Migración rápida, poco tiempo para cambios, bajo costo inicial. |
| **Replatform** (Lift, Tinker & Shift) | Pequeñas optimizaciones sin cambiar el código central (ej. mover la DB a RDS). | Quieres beneficios de servicios gestionados sin reescribir la app. |
| **Refactor** (Re-architect) | Reescribir la app para que sea nativa de la nube (ej. usar Lambda o Microservicios). | Necesitas máxima escalabilidad, agilidad y rendimiento. Es la más cara/lenta. |
| **Relocate** | Mover cargas de trabajo de VMware a AWS sin cambiar nada. | Usas VMware en on-prem y quieres seguir usándolo en la nube. |
| **Repurchase** (Drop and Shop) | Abandonar el software actual y comprar una versión SaaS. | Pasar de un CRM antiguo a Salesforce o de Email propio a Office 365. |
| **Retain** | No hacer nada por ahora. Mantenerlo en on-premise. | Aplicaciones que no se pueden migrar por cumplimiento o latencia. |
| **Retire** | Eliminar la aplicación. | Aplicaciones que ya no se usan o son redundantes. |

### Herramientas de Movimiento de Datos

Cuando tienes terabytes de datos, el internet de tu oficina puede ser el cuello de botella. Aquí es donde entran los "camiones" de AWS.

#### Familia AWS Snow (Migración física)

Se usan cuando enviar datos por internet tardaría semanas o meses.

* **AWS Snowcone:** Pequeño, portátil (8 TB). Ideal para sitios con poco espacio.
* **AWS Snowball Edge:** El estándar (80 TB). Tiene capacidad de cómputo para procesar datos *in-situ*.
* **AWS Snowmobile:** Un camión de 13 metros para exabytes de datos.

#### AWS DataSync

* **Uso:** Automatiza la transferencia de datos entre on-premise y S3, EFS o FSx.
* **Clave:** Es por red (online), no físico. Usa aceleración para ir más rápido.

### Replicación y Migración de Bases de Datos

Migrar una base de datos es delicado porque no puedes permitir que los datos se pierdan mientras la gente los usa.

**AWS DMS (Database Migration Service):**
* Permite migrar bases de datos con **tiempo de inactividad mínimo**.
* **Replicación continua:** Mientras los datos se mueven, DMS sigue copiando los cambios que ocurren en la base de datos de origen.


**AWS SCT (Schema Conversion Tool):**
* Se usa **antes** de DMS si vas a cambiar el "motor" (ej. de Oracle a Amazon Aurora).
* Convierte el esquema de la DB para que sea compatible con el nuevo motor.

------------------------------------------------------------

### Costos Fijos vs. Costos Variables

* **Costos Fijos (CapEx):** Son las inversiones iniciales pesadas. Tienes que comprar el servidor, el rack y el edificio antes de encender la primera aplicación. Es poco flexible: si tu negocio baja, el servidor sigue ahí costando dinero.
* **Costos Variables (OpEx):** Pagas solo por lo que usas (modelo *Pay-as-you-go*). Si apagas el servicio, el costo desaparece.
* **Ventaja clave:** Puedes **cambiar gastos de capital por gastos variables**, lo que permite a las empresas probar ideas sin arriesgar millones en hardware.

### Costos de Entornos On-Premises (En las instalaciones)

**TCO** (Total Cost of Ownership). **Costos "Ocultos" del On-Premise:**

* **Infraestructura física:** Alquiler del espacio, racks, cableado.
* **Utilidades:** Electricidad (los servidores consumen mucho) y **refrigeración** (aire acondicionado 24/7).
* **Mantenimiento:** Personal técnico para cambiar discos rotos, actualizar firmware y limpiar el polvo.
* **Seguridad física:** Guardias, cámaras, control de acceso biométrico.

### Estrategias de Licencias

¿Qué pasa con el software caro (como Windows Server o SQL Server)?

* **Licencias Incluidas (LI):** AWS se encarga de todo. Pagas un poco más por hora en tu instancia de EC2, pero no tienes que comprar una licencia aparte. Es ideal para proyectos nuevos o temporales.
* **BYOL (Bring Your Own License):** Si ya compraste licencias para tus servidores físicos, puedes "traértelas" a AWS.
* **Tip de examen:** Normalmente se requiere el uso de **EC2 Dedicated Hosts** o **Dedicated Instances** para cumplir con las reglas de algunos fabricantes al usar BYOL.


### Dimensionamiento Correcto (Right-Sizing)

Es el proceso de **ajustar el tipo y tamaño de los recursos** a tus necesidades reales de rendimiento al menor costo posible.

* **El error común:** En on-premise, compramos servidores gigantes "por si acaso" crecemos.
* **La solución en la nube:** Si una instancia usa solo el 10% de su CPU, el *Right-Sizing* dicta que debes moverla a una instancia más pequeña y barata.
* **Cuándo hacerlo:** Debe ser un proceso continuo, no algo que se hace una sola vez.

| Concepto | Lo que el examen quiere oír |
| --- | --- |
| **CapEx a OpEx** | Dejar de invertir en hardware físico y pagar solo por uso. |
| **TCO** | El costo total incluye luz, espacio, refrigeración y personal. |
| **BYOL** | Reutilizar licencias propias para ahorrar dinero. |
| **Right-Sizing** | No pagar por capacidad que no estás usando. |
  
## Seguridad y conformidad (30 % del contenido con puntaje)

- reconocer los componentes del modelo de responsabilidad compartida de AWS
- describir las responsabilidades del cliente en AWS
- describir las responsabilidades de AWS
- describir las responsabilidades que comparten el cliente y AWS
- Describir cómo pueden cambiar las responsabilidades de AWS y las del cliente según el servicio utilizado (por ejemplo, Amazon RDS, AWS Lambda o Amazon Elastic Compute Cloud)
- identificar dónde encontrar la información de conformidad de AWS (por ejemplo, AWS Artifact)
- comprender las necesidades de conformidad entre ubicaciones geográficas o sectores (por ejemplo, conformidad de AWS)
- describir cómo los clientes protegen los recursos en AWS (por ejemplo, Amazon Inspector, AWS Security Hub, Amazon GuardDuty, AWS Shield)
- identificar opciones de cifrado (por ejemplo, cifrado en tránsito, cifrado en reposo)
- reconocer los servicios que ayudan a la gobernanza y la conformidad (por ejemplo, la supervisión con Amazon CloudWatch; la auditoría con AWS CloudTrail, AWS Audit Manager y AWS Config; la generación de informes con informes de acceso)
- reconocer los requisitos de conformidad que varían entre los servicios de AWS
- comprender las claves de acceso, las políticas de contraseñas y el almacenamiento de credenciales (por ejemplo, AWS Secrets Manager, AWS Systems Manager)
- identificar los métodos de autenticación en AWS (por ejemplo, autenticación multifactor [MFA], IAM Identity Center, roles de IAM entre cuentas)
- definir grupos, usuarios, políticas personalizadas y políticas administradas en conformidad con el principio de mínimo privilegio
- identificar las tareas que solo el usuario raíz de la cuenta puede realizar
- comprender qué métodos pueden lograr la protección del usuario raíz
- comprender los tipos de administración de identidades (por ejemplo, federada)
- AWS IAM Identity Center (AWS Single Sign-On)
- describir las características y los servicios de seguridad de AWS (por ejemplo, AWS WAF, AWS Firewall Manager, AWS Shield, Amazon GuardDuty)
- comprender que los productos de seguridad de terceros están disponibles en AWS Marketplace
- identificar dónde está disponible la información de seguridad de AWS (por ejemplo, AWS Knowledge Center, AWS Security Center, Blog de seguridad
de AWS)
- comprender el uso de los servicios de AWS para identificar problemas de seguridad (por ejemplo, AWS Trusted Advisor)

## Tecnología y servicios en la nube (34 % del contenido con puntaje)

- decidir entre opciones como el acceso programático (por ejemplo, las API, los SDK, la CLI), la consola de administración de AWS y la  infraestructura como código (IaC)
- evaluar los requisitos para determinar si se deben utilizar operaciones únicas o procesos repetibles
- identificar modelos de implementación (por ejemplo, en la nube, híbridos, en las instalaciones)
"""
* **Regiones:** Ubicaciones físicas en el mundo con múltiples AZs.
* *Para qué sirven:* Elegir una región cercana al usuario para **bajar la latencia** o cumplir con **leyes de datos** locales (Soberanía de datos).
* **Zonas de Disponibilidad (AZs):** Uno o más centros de datos aislados dentro de una Región.
* *Para qué sirven:* Si una AZ falla (por un incendio o inundación), tu aplicación sigue viva en otra. Esto es **Tolerancia a Fallos**.
* **Puntos de Presencia (Edge Locations):** Centros de datos pequeños repartidos por cientos de ciudades.
* *Para qué sirven:* **Velocidad de implementación**. Usan servicios como **Amazon CloudFront** para entregar contenido (vídeos, imágenes) con la mínima latencia.
"""

- describir cómo lograr una alta disponibilidad mediante el uso de varias zonas de disponibilidad
- reconocer que las zonas de disponibilidad no comparten puntos únicos de error
- describir cuándo utilizar varias regiones (por ejemplo, recuperación de desastres, continuidad de actividades, baja latencia para los usuarios finales, soberanía de datos)
- reconocer el uso adecuado de varios tipos de instancia de EC2 (por ejemplo, optimizadas para computación, optimizadas para almacenamiento)
- reconocer el uso adecuado de varias opciones de contenedores (por ejemplo, Amazon ECS, Amazon EKS)
- reconocer el uso adecuado de varias opciones de computación sin servidor (por ejemplo, AWS Fargate, Lambda)
- reconocer que el escalado automático proporciona elasticidad
- identificar los propósitos de los balanceadores de carga
- decidir cuándo utilizar las bases de datos alojadas en Elastic Compute Cloud o las bases de datos administradas por AWS
- identificar bases de datos relacionales (por ejemplo, Amazon RDS, Amazon Aurora)
- identificar bases de datos NoSQL (por ejemplo, DynamoDB)
- identificar bases de datos basadas en memoria (por ejemplo, Amazon ElastiCache)
- identificar herramientas de migración de bases de datos (por ejemplo, AWS Database Migration Service [AWS DMS], Herramienta de conversión de esquemas de AWS [AWS SCT])
- identificar los componentes de una VPC (por ejemplo, subredes, puertas de enlace)
- describir la seguridad en una VPC (por ejemplo, ACL de red, grupos de seguridad, Amazon Inspector)
- comprender el propósito de Amazon Route 53
- identificar las opciones de conectividad de red con AWS (por ejemplo, AWS VPN, AWS Direct Connect)
- identificar los usos del almacenamiento de objetos
- reconocer las diferencias en las clases de almacenamiento de Amazon S3
- identificar soluciones de almacenamiento en bloques (por ejemplo, Amazon Elastic Block Store [Amazon EBS], almacén de instancias)
- identificar servicios de archivos (por ejemplo, Amazon Elastic File System [Amazon EFS], Amazon FSx)
- identificar los sistemas de archivos en caché (por ejemplo, AWS Storage Gateway)
- comprender los casos de uso de las políticas de ciclo de vida
- describir los casos de uso de AWS Backup
- comprender los servicios de IA/ML y las tareas que realizan (por ejemplo, IA de Amazon SageMaker, Amazon Lex, Amazon Kendra)
- identificar los servicios de análisis de datos (por ejemplo, Amazon Athena, Amazon Kinesis, AWS Glue, Amazon QuickSight)
- servicios de integración de aplicaciones de Amazon EventBridge, Amazon Simple Notification Service (Amazon SNS) y Amazon Simple Queue Service (Amazon SQS)
- servicios de aplicaciones empresariales de Amazon Connect y Amazon Simple Email Service (Amazon SES)
- servicios de habilitación para clientes (por ejemplo, AWS Support)
- servicios y capacidades de herramientas para desarrolladores (por ejemplo, AWS CodeBuild, AWS CodePipeline y AWS X-Ray)
- servicios de cómputo para usuarios finales de Amazon AppStream 2.0, Amazon WorkSpaces y Amazon WorkSpaces Secure Browser
- servicios web y móviles de frontend de AWS Amplify y AWS AppSync
- servicios de IoT (por ejemplo, AWS IoT Core)

## Facturación, precios y soporte (12 % del contenido con punta

- opciones de compra de computación (por ejemplo, instancias bajo demanda, instancias reservadas, instancias de spot, Savings Plans, hosts dedicados, instancias dedicadas, reservas de capacidad)
- opciones y niveles de almacenamiento
- comprender los usos y las capacidades adecuados de AWS Budgets y el explorador de costos de AWS
- comprender los usos y las capacidades adecuados de la calculadora de precios de AWS
- comprender la facturación unificada de AWS Organizations y la asignación de costos
- comprender los distintos tipos de etiquetas de asignación de costos y su relación con los informes de facturación (por ejemplo, Informe de costo y uso de AWS)
- localizar documentos técnicos, blogs y documentación de AWS en los sitios web oficiales de AWS
- identificar y localizar los recursos técnicos de AWS (por ejemplo, recomendaciones de AWS, AWS Knowledge Center o AWS re:Post)
- identificar las opciones de AWS Support para los clientes de AWS (por ejemplo, comunidades y servicio al cliente, AWS Developer Support, AWS Business Support, AWS Enterprise On-Ramp Support, AWS Enterprise
Support)
- identificar el rol de Trusted Advisor, el Panel de AWS Health y la API de AWS Health para ayudar a administrar y supervisar los entornos para la optimización de costos
- identificar el rol del centro de confianza y seguridad de AWS para denunciar el abuso de los recursos de AWS
- comprender el rol de los socios de AWS (por ejemplo, AWS Marketplace, proveedores de software independientes, integradores de sistemas)
- identificar los beneficios de ser socio de AWS (por ejemplo, formación y certificación para socios, eventos para socios, descuentos por volumen para socios)
- identificar los servicios clave que ofrece AWS Marketplace (por ejemplo, administración de costos, gobernanza y derechos)
- identificar las opciones de asistencia técnica disponibles en AWS (por ejemplo, AWS Professional Services, arquitectos de soluciones de AWS)


### Servicios y características de AWS

Análisis:
- Amazon Athena
- Amazon EMR
- AWS Glue
- Amazon Kinesis
- Amazon OpenSearch Service
- Amazon QuickSight
- Amazon Redshift

Integración de aplicaciones:
- Amazon EventBridge
- Amazon Simple Notification Service (Amazon SNS)
- Amazon Simple Queue Service (Amazon SQS)
- AWS Step Functions

Aplicaciones empresariales:
- Amazon Connect
- Amazon Simple Email Service (Amazon SES)

Administración financiera en la nube:
- AWS Budgets
- Informes de costo y uso de AWS
- Explorador de costos de AWS
- AWS MarketplaceComputación
- AWS Batch
- Amazon Elastic Compute Cloud
- AWS Elastic Beanstalk
- Amazon Lightsail
- AWS Outposts

Contenedores:
- Amazon Elastic Container Registry (Amazon ECR)
- Amazon Elastic Container Service (Amazon ECS)
- Amazon Elastic Kubernetes Service (Amazon EKS)

Habilitación para clientes:
- AWS Support

Base de datos:
- Amazon Aurora
- Amazon DocumentDB
- Amazon DynamoDB
- Amazon ElastiCache
- Amazon Neptune
- Amazon RDS

Herramientas para desarrolladores:
- AWS CLI
- AWS CodeBuild
- AWS CodePipeline
- AWS X-Ray

AWS End User Computing:
- Amazon AppStream 2.0
- Amazon WorkSpaces
- Amazon WorkSpaces Secure Browser

Frontend web y móvil:
- AWS Amplify
- AWS AppSync

Internet de las cosas (IoT):
- AWS IoT Core

Machine learning:
- Amazon Comprehend
- Amazon Kendra
- Amazon Lex
- Amazon Polly
- Amazon Q
- Amazon Rekognition
- IA de Amazon SageMaker
- Amazon Textract
- Amazon Transcribe
- Amazon Translate

Administración y gobernanza:
- AWS Auto Scaling
- AWS CloudFormation
- AWS CloudTrail
- Amazon CloudWatch
- AWS Compute Optimizer
- AWS Config
- AWS Control Tower
- Panel de AWS Health
- AWS License Manager
- Consola de administración de AWS
- AWS Organizations
- AWS Service Catalog
- Service Quotas
- AWS Systems Manager
- AWS Trusted Advisor
- Herramienta de AWS Well-Architected

Migración y transferencia:
- AWS Application Discovery Service
- AWS Application Migration Service
- AWS Database Migration Service (AWS DMS)
- Migration Evaluator
- AWS Migration Hub
- Herramienta de conversión de esquemas de AWS (AWS SCT)
- AWS Snow Family

Redes y entrega de contenido:
- Amazon API Gateway
- Amazon CloudFront
- AWS Direct Connect
- AWS Global Accelerator
- AWS PrivateLink
- Amazon Route 53
- AWS Transit Gateway
- Amazon VPC
- AWS VPN
- AWS Site-to-Site VPN
- AWS Client VPN

Seguridad, identidad y conformidad:
- AWS Artifact
- AWS Audit Manager
- AWS Certificate Manager (ACM)
- AWS CloudHSM
- Amazon Cognito
- Amazon Detective
- AWS Directory Service
- AWS Firewall Manager
- Amazon GuardDuty
- AWS Identity and Access Management (AWS IAM)
- AWS IAM Identity Center
- Amazon Inspector
- AWS Key Management Service (AWS KMS)
- Amazon Macie
- AWS Resource Access Manager (AWS RAM)
- AWS Secrets Manager
- AWS Security Hub
- AWS Shield
- AWS WAF

Sin servidor:
- AWS Fargate
- AWS Lambda

Almacenamiento:
- AWS Backup
- Amazon Elastic Block Store (Amazon EBS)
- Amazon Elastic File System (Amazon EFS)
- Recuperación de desastres elástica de AWS
- Amazon FSx
- Amazon S3
- Amazon S3 Glacier
- AWS Storage Gateway

Herramientas para desarrolladores (fuera de alcance):
- AWS Application Composer
- AWS CodeArtifact
- AWS CodeDeploy
- Amazon CodeGuru
- AWS CloudShell
- AWS Device Farm

--------------------------------

## Fundamentos de Cloud Computing

La **computación en la nube** consiste en ofrecer recursos informáticos (cómputo, almacenamiento, bases de datos, etc.) *bajo demanda* a través de Internet, siguiendo un modelo de pago por uso. Esto elimina la necesidad de comprar y gestionar hardware propio, y permite a las organizaciones escalar con rapidez según la demanda. Entre las ventajas clave destacan la **agilidad** (aprovisionar recursos en minutos), la **elasticidad** (escalar automáticamente) y el **ahorro de costes**, al pagar solo por lo consumido.

<img width="708" height="461" alt="image" src="https://github.com/user-attachments/assets/321729dd-bf99-4b9c-a86f-53d7f198514b" />


En la nube, el gasto se transforma de **CAPEX** (inversiones en infraestructuras fijas, como servidores y licencias) a **OPEX** (costes operativos variables, según el uso). Esto reduce el *Costo Total de Propiedad* (TCO), ya que minimiza el CAPEX inicial y ajusta el gasto al consumo real. Por ejemplo, en un entorno propio (on-premises) se asumen grandes CAPEX y costes de mantenimiento, mientras que en la nube el coste es más predecible y flexible.

## Modelos de servicio y de despliegue

- **IaaS, PaaS y SaaS:** Son modelos de servicio en la nube que definen el nivel de control del usuario.
  - En **IaaS (Infraestructura como Servicio)**, el proveedor gestiona el hardware y la virtualización, mientras que el cliente controla el sistema operativo, el middleware y las aplicaciones.
  - En **PaaS (Plataforma)**, el proveedor también gestiona el sistema operativo y el runtime, lo que permite al usuario centrarse en las aplicaciones.
  - En **SaaS (Software)**, el proveedor gestiona todo y el usuario solo utiliza la aplicación final. La siguiente tabla compara quién controla cada componente en IaaS, PaaS y SaaS:

<img width="778" height="727" alt="image" src="https://github.com/user-attachments/assets/2da8eebd-a7db-4e39-9222-15e450cdd1e2" />

Cada modelo tiene casos de uso. Por ejemplo, IaaS (EC2, EBS) es ideal si necesitas control total del entorno; PaaS (AWS Elastic Beanstalk, RDS) acelera el desarrollo sin gestionar infraestructura; y SaaS (Gmail, Salesforce) ofrece aplicaciones listas para usar. 

**Nubes públicas, privadas, híbridas y multicloud:**

- **Nube pública:** Infraestructura compartida, proporcionada por terceros (p. ej., AWS, Azure, GCP) y utilizada *por muchos clientes*. Ofrece alta escalabilidad y costes bajos gracias al pago por uso, pero un menor control sobre la infraestructura.
- **Nube privada:** Infraestructura dedicada a una sola organización, ya sea en sus propias instalaciones o en un centro del proveedor. Ofrece mayor control, seguridad y cumplimiento, pero requiere una inversión elevada (mayor CAPEX) y gestión propia.
- **Nube híbrida:** Combina nube pública y privada. Permite, por ejemplo, mantener datos sensibles en la nube privada y procesarlos en la pública cuando la demanda aumenta, conectando ambos entornos y compartiendo datos. Es útil para combinar escalabilidad y seguridad.
- **Multicloud:** Uso de servicios de *varios* proveedores públicos a la vez. Reduce la dependencia de un solo proveedor y permite aprovechar las fortalezas de cada nube, pero exige gestionar la compatibilidad y la integración.

Cada tipo responde a necesidades distintas. Por ejemplo, una empresa puede usar AWS (pública) para cargas generales y mantener su propio centro (privada) para datos críticos, o usar AWS + Azure simultáneamente (multicloud) para evitar vendor lock-in.

## Principales proveedores de la nube

Los líderes del mercado de servicios cloud son **Amazon Web Services (AWS)**, **Microsoft Azure** y **Google Cloud Platform (GCP)**. Ofrecen conjuntos de servicios globales similares. AWS es el proveedor más maduro y con mayor amplitud de servicios, seguido por Azure (fuerte en entornos empresariales) y GCP (con foco en datos y ML). También existen otros proveedores relevantes, como IBM Cloud, Oracle Cloud y Alibaba Cloud, entre otros. En general, AWS destaca por su catálogo muy extenso y su presencia global, lo que lo convierte en una buena opción para empezar en la nube.

## Servicios principales de AWS

<img width="1537" height="739" alt="image" src="https://github.com/user-attachments/assets/38038130-6d3e-46cd-a2de-36a1a6b5dbcf" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fba67e26-f523-4b24-8cd5-22d4ef3ba15c" />

<img width="1215" height="912" alt="image" src="https://github.com/user-attachments/assets/fcfe20bd-7a20-4cef-9cbb-10a003739b1a" />

<img width="1618" height="860" alt="image" src="https://github.com/user-attachments/assets/40a57f65-6315-48c9-8ccb-e7d8414caf31" />

<img width="1745" height="534" alt="image" src="https://github.com/user-attachments/assets/0a5c3991-74a8-431a-a0b3-7f61a6882224" />

<img width="1850" height="1080" alt="image" src="https://github.com/user-attachments/assets/9309e35e-7153-4c4b-91e2-8cde8b4a2bcd" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f9236ed9-7523-4c95-b9c1-f4e92a977836" />

<img width="1335" height="948" alt="image" src="https://github.com/user-attachments/assets/c4d216c8-e064-4ff9-886a-cffe77ed0380" />

<img width="916" height="955" alt="image" src="https://github.com/user-attachments/assets/5eb7412c-2e54-4df2-9b74-2fda8ce9643e" />

<img width="1408" height="768" alt="image" src="https://github.com/user-attachments/assets/29e3610b-31c0-4dd0-a8a9-a5a02f4a75ac" />

<img width="1919" height="1080" alt="image" src="https://github.com/user-attachments/assets/e53232b8-9bff-44af-a0f9-aef9f6bef7ee" />


**Cómputo (Compute):**

- **Amazon EC2:** Máquinas virtuales configurables en la nube. Permite elegir sistema operativo, CPU, memoria y almacenamiento. Se paga por segundo u hora de uso. Incluye instancias on-demand (sin compromiso, pago por uso) y opciones de ahorro, como instancias reservadas o Savings Plans, además de Spot (capacidad ociosa con hasta ~90% de descuento).

<img width="1681" height="876" alt="image" src="https://github.com/user-attachments/assets/96943499-a954-4caa-933b-b514f1bba01b" />

- **AWS Auto Scaling / EC2 Auto Scaling** es un servicio que ajusta automáticamente la capacidad de sus recursos (como instancias EC2, ECS o DynamoDB) para mantener un rendimiento óptimo y alta disponibilidad, aumentando o disminuyendo la capacidad según la demanda en tiempo real. Esto optimiza costos al eliminar recursos innecesarios.
- **Amazon WorkSpaces** es un servicio gestionado de escritorio como servicio (DaaS) en la nube que permite aprovisionar escritorios virtuales seguros y persistentes o no persistentes con Windows, Linux o Ubuntu. Los usuarios acceden a sus aplicaciones y recursos desde cualquier dispositivo, facilitando el trabajo remoto sin necesidad de gestionar hardware o infraestructura compleja.
- **AWS Lambda:** Computación serverless que ejecuta código ante eventos (HTTP, mensajes o cambios en datos). Escala automáticamente y se cobra por milisegundos de ejecución y memoria utilizada. Es ideal para tareas puntuales sin administrar servidores.
- **AWS Glue** es un servicio de integración de datos serverless (sin servidor) y totalmente administrado que facilita la detección, preparación, transformación y carga (ETL) de grandes volúmenes de datos para análisis, aprendizaje automático y desarrollo de aplicaciones. Automatiza tareas complejas mediante un Data Catalog centralizado, compatible con Apache Spark y herramientas visuales como Glue Studio.
- **AWS Elastic Beanstalk** es un servicio "Plataforma como Servicio" (PaaS) de Amazon Web Services que facilita la implementación y escalado rápido de aplicaciones web y servicios (desarrollados en Java, .NET, PHP, Node.js, Python, Ruby, Go y Docker) sin gestionar la infraestructura subyacente. Solo necesitas subir tu código y el servicio gestiona automáticamente el aprovisionamiento, balanceo de carga, escalado y monitoreo.
- **AWS Software Development Kit (SDK)** es un conjunto de herramientas, bibliotecas y documentación que permite a los desarrolladores crear aplicaciones fácilmente en la plataforma Amazon Web Services (AWS). Simplifica el acceso a servicios de AWS (como S3, DynamoDB) mediante código, soportando lenguajes como Python, JavaScript, Java, PHP, Ruby, Go y .NET

**Contenedores (Containers):**

- **Amazon ECS/EKS/Fargate:** Servicios para ejecutar contenedores Docker. **ECS** es el orquestador propio de AWS. **EKS** es Kubernetes gestionado. **Fargate** permite lanzar contenedores sin gestionar servidores subyacentes. Estos servicios facilitan el despliegue de microservicios y aplicaciones en contenedores.
- **Amazon Elastic Container Registry (ECR)** es un servicio de registro de contenedores (Docker y OCI) totalmente gestionado y seguro que permite almacenar, administrar y desplegar imágenes de contenedores. Destaca por su alta disponibilidad, integración nativa con AWS (ECS, EKS, Lambda) y funciones de seguridad como el escaneo de vulnerabilidades.
- **Amazon Elastic Kubernetes Service (Amazon EKS)** es un servicio administrado de Kubernetes que facilita la ejecución de aplicaciones en contenedores en la nube de AWS o en centros de datos propios. Automatiza la gestión, escalado y alta disponibilidad del plano de control y nodos, eliminando la necesidad de instalar o configurar Kubernetes manualmente

**Almacenamiento:**
- **Amazon S3:** Almacenamiento de objetos en la nube (archivos, imágenes y copias de seguridad). Es altamente escalable y redundante. Soporta distintos *niveles de almacenamiento* (Standard, Infrequent Access, Glacier, etc.) según la frecuencia de acceso. Es ideal para datos estáticos con control de versiones o copias de seguridad. Bucket (contenedor lógico de objetos S3, debe ser nombre único en todo el mundo).
  - **Amazon AWS Access Analyzer for S3** es una funcionalidad integrada en la consola de S3 que utiliza razonamiento automatizado para identificar qué buckets de S3 son accesibles públicamente o desde otras cuentas de AWS. Ayuda a los administradores a supervisar políticas, detectar riesgos de seguridad y prevenir fugas de datos no deseadas
  - **S3 Standard**: Ideal para datos de acceso frecuente, alto rendimiento y baja latencia.
  - **S3 Intelligent-Tiering**: Mueve automáticamente los datos entre dos niveles de acceso (frecuente e infrecuente) cuando cambian los patrones de acceso, sin impacto en el rendimiento.
  - **S3 Standard-Infrequent Access (S3 Standard-IA)**: Diseñado para datos a los que se accede con menos frecuencia pero que requieren un acceso rápido (milisegundos) cuando es necesario.
  - **S3 One Zone-Infrequent Access (S3 One Zone-IA)**: Similar a Standard-IA, pero almacena los datos en una sola zona de disponibilidad, lo que reduce costos, siendo ideal para datos reproducibles.
  - **S3 Glacier Instant Retrieval**: Nivel de archivo que ofrece recuperación en milisegundos para datos a los que se accede raramente.
  - **S3 Glacier Flexible Retrieval**: (Antes Glacier) Almacenamiento de bajo costo para copias de seguridad con tiempos de recuperación desde minutos a horas.
  - **S3 Glacier Deep Archive**: La opción de almacenamiento más económica para datos a largo plazo (cumplimiento normativo) a los que se accede una o dos veces al año.
  - **S3 Express One Zone**: Almacenamiento de mayor rendimiento, diseñado para ofrecer acceso a datos en milisegundos de un solo dígito
- **Amazon EBS:** Volúmenes de disco en bloque para usar con instancias EC2 (similar a discos duros en la nube).
- **Amazon Elastic File System (EFS)** es un servicio de almacenamiento de archivos en la nube, gestionado, escalable y compartido, diseñado para AWS y recursos locales. Utiliza el protocolo NFS (Network File System), permitiendo que múltiples instancias EC2, contenedores o servidores accedan simultáneamente a los mismos datos en diferentes zonas de disponibilidad.
- **AWS Storage Gateway** es un servicio de almacenamiento híbrido que conecta entornos locales (on-premise) con la nube de Amazon Web Services (AWS). Proporciona acceso ilimitado a almacenamiento en la nube (S3, Glacier, EBS) sin cambiar aplicaciones existentes, utilizando protocolos estándar (NFS, SMB, iSCSI) y caché local para baja latencia
- **AWS Backup** es un servicio de gestión de copias de seguridad totalmente administrado y centralizado que automatiza la protección de datos en la nube de AWS y entornos híbridos. Permite configurar políticas, programar respaldos y gestionar retenciones para servicios como Amazon EC2, RDS, EBS, S3 y DynamoDB, facilitando el cumplimiento normativo.
- **AWS Lake Formation** es un servicio administrado que simplifica la creación, gestión y protección de data lakes (lagos de datos) en Amazon S3 en cuestión de días, no meses. Centraliza la gobernanza, permitiendo definir políticas de seguridad detalladas a nivel de columna, fila o tabla para controlar el acceso a la información.
- **AWS Instance Store** es un almacenamiento temporal de alto rendimiento a nivel de bloque, físicamente conectado al host de una instancia EC2. Es ideal para datos efímeros como cachés, buffers y datos temporales que no necesitan persistencia. Los datos se pierden si la instancia se detiene o falla

<img width="1728" height="910" alt="image" src="https://github.com/user-attachments/assets/5d5819d8-5769-4244-9f27-f6b83d5b0d76" />

<img width="728" height="880" alt="image" src="https://github.com/user-attachments/assets/7ed5671b-03fe-44f9-a812-e28a84634906" />

**Bases de datos:**

<img width="1624" height="1000" alt="image" src="https://github.com/user-attachments/assets/17aed05f-740f-48cd-961c-a086755a3169" />

- **Amazon RDS (Relation Database Service):** Bases de datos relacionales gestionadas (MySQL, PostgreSQL, SQL Server, Oracle y Aurora). AWS se encarga de aplicar parches, replicar y hacer copias de seguridad. Soporta **Multi-AZ** para alta disponibilidad (réplicas en distintas AZs).

<img width="1244" height="587" alt="image" src="https://github.com/user-attachments/assets/cddbd8c6-fe66-4573-802d-74779ecbfda3" />

- **Amazon Aurora**: Base de datos relacional de alto rendimiento compatible con MySQL/PostgreSQL.
- **Amazon DynamoDB:** es un servicio de base de datos NoSQL de clave-valor y documentos, totalmente administrado y sin servidor (serverless) de Amazon Web Services (AWS), que ofrece un rendimiento rápido y predecible (en milisegundos) con escalabilidad automática. Es ideal para aplicaciones modernas, móviles, web, IoT y juegos que requieren alta disponibilidad y manejo de gran volumen de datos.
- **Amazon Redshift** es un servicio de almacenamiento de datos (data warehouse) en la nube, totalmente gestionado y a escala de petabytes, diseñado para analítica de alto rendimiento. Utiliza almacenamiento columnar y procesamiento paralelo masivo (MPP) para consultas rápidas, permitiendo analizar grandes volúmenes de datos usando SQL y herramientas de BI convencionales a bajo costo.

<img width="1579" height="940" alt="image" src="https://github.com/user-attachments/assets/59c58a55-9c92-4a91-8bf7-923a2abba29a" />

- **Amazon Neptune**: Base de datos orientada a grafos.
- **DocumentDB** (compatible con MongoDB)
- **Amazon ElastiCache:** Servicio de caché en memoria compatible con Redis o Memcached para mejorar el rendimiento de aplicaciones.

<img width="1577" height="945" alt="image" src="https://github.com/user-attachments/assets/2255e526-d3a3-4779-88c5-811ab01a230e" />

**Redes y entrega de contenido (Networking & Content Delivery)**

- **Amazon VPC:** Red virtual privada en AWS donde se definen subredes, tablas de enrutamiento y gateways. Cada cuenta de AWS inicia con una VPC por región. Dentro de la VPC se crean *subredes* (públicas o privadas) y recursos (EC2, RDS, etc.). Se conecta al exterior mediante una **Puerta de Enlace a Internet (Internet Gateway)** y se pueden usar **NAT Gateways** para el tráfico saliente de subredes privadas. VPC actúa como una red tradicional propia en la nube.

<img width="1786" height="751" alt="image" src="https://github.com/user-attachments/assets/9537aa49-102e-4fd3-9623-b341b1cc3dd8" />

<img width="1649" height="762" alt="image" src="https://github.com/user-attachments/assets/66371141-a3be-4c27-b34e-a1d28e1f1e9c" />

- **Grupos de seguridad:** Firewalls a nivel de instancia EC2. Controlan qué tráfico entra o sale de cada servidor (por ejemplo, permitir SSH solo desde ciertas IPs). Son *stateful*: permiten respuestas automáticamente cuando una instancia origina tráfico.
- **Listas de control de acceso (Network ACL -> NACL):** Firewalls a nivel de subred, que evalúan el tráfico de entrada y salida por reglas (stateless).
- **Amazon Route 53:** Servicio DNS escalable y de alta disponibilidad. Traduce nombres de dominio a IPs y permite enrutar tráfico de forma inteligente (geolocalización y latencia). También soporta balanceo de carga simple a Load Balancers o puntos finales.
- **Elastic Load Balancing (ELB):** Distribuye automáticamente el tráfico entre múltiples instancias en una o más zonas de disponibilidad. Aumenta la disponibilidad y la tolerancia a fallos. Soporta distintos tipos (Application Load Balancer para HTTP/HTTPS, Network Load Balancer de baja latencia y Gateway Load Balancer para tráfico L4).
- **Amazon CloudFront:** Red de entrega de contenido (CDN) global para distribuir contenido (contenidos web estáticos y dinámicos, como HTML, CSS, JavaScript e imágenes, así como vídeos) con baja latencia.

<img width="1852" height="794" alt="image" src="https://github.com/user-attachments/assets/e33c0ad9-b1e7-4516-9f4f-6135c684fb11" />

<img width="1834" height="933" alt="image" src="https://github.com/user-attachments/assets/7dc0e166-02b5-45c9-8da1-e96a26db6d62" />

- **AWS Global Accelerator** es un servicio de red que mejora la disponibilidad y el rendimiento (hasta un 60% más rápido) de las aplicaciones web y de Internet al dirigir el tráfico de usuarios a través de la infraestructura de red global de Amazon, en lugar de la red pública de Internet. Utiliza direcciones IP estáticas con Anycast para enrutar el tráfico al punto de enlace más cercano.


**Seguridad e IAM:**

- **AWS Identity and Access Management (IAM):** Permite crear usuarios, grupos y roles con permisos específicos. Un **usuario IAM** representa a una persona o aplicación que interactúa con AWS. Se recomienda aplicar el **principio de privilegio mínimo**, dando a cada usuario solo los permisos necesarios. La *cuenta root* (creador de la cuenta) tiene todos los permisos. Se aconseja protegerla con **MFA** (autenticación de dos factores) y usarla solo cuando sea imprescindible. AWS permite habilitar MFA para cualquier usuario IAM, requiriendo un código adicional generado en un dispositivo, lo que mejora la seguridad.
  - **AWS IAM User (Usuario)** es una identidad específica dentro de tu cuenta de AWS que representa a una persona física o a una aplicación/servicio que interactúa con AWS. Se utiliza para el acceso directo y continuo. Un usuario tiene credenciales a largo plazo (nombre de usuario/contraseña para la consola o claves de acceso para la CLI/API). Ejemplo: Un desarrollador llamado "Juan" o una aplicación de backend que necesita leer datos de S3.
  - **AWS IAM Group (Grupo)** es Una colección de usuarios de IAM. Sirve para gestionar permisos a escala. En lugar de asignar políticas (permisos) a cada usuario individualmente, creas un grupo, le asignas permisos y añades usuarios a ese grupo. Todos los miembros heredan los permisos del grupo. Ejemplo: Un grupo llamado "Administradores" o "Desarrolladores" que agrupa a varias personas. 
  - **AWS IAM Role (Rol)** es una identidad de IAM que puedes crear en tu cuenta pero que no tiene credenciales estáticas (contraseñas o claves de acceso) asociadas. Está diseñado para ser asumido temporalmente por usuarios, aplicaciones o servicios de AWS (como EC2 o Lambda) que necesitan permisos específicos solo durante un tiempo limitado. Ejemplo: Darle a una instancia EC2 (servidor) un rol para acceder a una base de datos sin guardar contraseñas dentro del servidor
**Mínimo privilegio:** Otorgar solo los permisos estrictamente necesarios a usuarios y roles (evitando permisos administrativos innecesarios) es una práctica esencial de seguridad. Además, activar **MFA** (autenticación multifactor) en todas las cuentas de IAM refuerza la protección.

<img width="1231" height="752" alt="image" src="https://github.com/user-attachments/assets/0bbb6e8e-477a-4c86-95aa-84bd387cd295" />

- **Políticas de IAM:** Documentos en JSON que definen permisos (qué acciones puede realizar un usuario o rol sobre qué recursos). Se adjuntan a usuarios, grupos o roles para controlar el acceso.

<img width="956" height="733" alt="image" src="https://github.com/user-attachments/assets/b3897885-dff2-407f-85d4-560d3b985a69" />
<img width="1638" height="761" alt="image" src="https://github.com/user-attachments/assets/01afeb5c-b3e3-4bf5-b41f-d516754e5527" />
<img width="1638" height="761" alt="image" src="https://github.com/user-attachments/assets/ebac3c56-ee47-4d46-92b8-bb75eb766b9d" />
<img width="1186" height="712" alt="image" src="https://github.com/user-attachments/assets/ba672110-7fd9-409b-8195-05eab527533e" />

- **Amazon Macie** es un servicio de seguridad y privacidad de datos totalmente gestionado que utiliza machine learning y coincidencia de patrones para descubrir, clasificar y proteger automáticamente información sensible (como datos personales o financieros) almacenada en Amazon S3.
- **Amazon Inspector** es un servicio de gestión de vulnerabilidades automatizado de Amazon Web Services (AWS) que analiza continuamente cargas de trabajo (instancias EC2, contenedores ECR y funciones Lambda) para detectar fallos de seguridad, software desactualizado y exposiciones de red no deseadas. Proporciona hallazgos detallados con recomendaciones de corrección, mejorando la postura de seguridad y el cumplimiento normativo.
- **Amazon Network ACLs** (Listas de Control de Acceso a la Red) son una capa de seguridad esencial en AWS que actúa como un firewall sin estado (stateless) a nivel de subred. Controlan el tráfico entrante y saliente, permitiendo o denegando reglas específicas para proteger los recursos dentro de una VPC.
- **Amazon Cognito** es un servicio de Amazon Web Services (AWS) que gestiona el registro, inicio de sesión y control de acceso de usuarios en aplicaciones web y móviles.

<img width="1717" height="775" alt="image" src="https://github.com/user-attachments/assets/eb3da604-02d6-4642-8e9c-a57a50a75056" />

- **Amazon GuardDuty** es un servicio de detección de amenazas inteligente y administrado que monitorea continuamente las cuentas, cargas de trabajo (como EC2, EKS, Lambda) y datos de almacenamiento (S3) de AWS en busca de actividades maliciosas, comportamientos inusuales y malware. Utiliza inteligencia artificial, aprendizaje automático y fuentes de datos de seguridad para proporcionar alertas detalladas, facilitando la remediación rápida.
- **AWS Artifact** es un servicio centralizado y bajo demanda que proporciona acceso a los informes de seguridad y cumplimiento de AWS, incluyendo certificaciones ISO, PCI e informes SOC. Es fundamental para auditorías, permitiendo a los usuarios descargar documentos de cumplimiento y gestionar acuerdos (aceptar términos) con AWS.
- **AWS WAF (Web Application Firewall)** es un servicio de seguridad en la nube de Amazon Web Services que protege aplicaciones web y APIs contra exploits comunes, bots y tráfico malicioso. Permite crear reglas personalizadas para bloquear o permitir solicitudes HTTP/HTTPS basadas en IP, cabeceras o contenido, protegiendo recursos como CloudFront, Application Load Balancer y API Gateway.
- **AWS Shield** es un servicio gestionado de protección contra ataques de denegación de servicio distribuido (DDoS) que salvaguarda aplicaciones web en Amazon Web Services (AWS). Ofrece dos niveles: Standard, que es gratuito y automático para ataques comunes en capas 3/4, y Advanced, que ofrece mitigación, visibilidad y soporte especializado para ataques sofisticados.
- **Otros servicios de seguridad:** AWS ofrece servicios específicos como AWS KMS (gestión de claves)

**Gestión y Gobernanza (Management)**

- **Amazon CloudWatch** es un servicio de monitoreo y observabilidad nativo de AWS que recopila datos en tiempo real (métricas, logs y eventos) de recursos como EC2, RDS y Lambda. Permite visualizar el rendimiento, configurar alarmas, automatizar acciones y optimizar recursos, ofreciendo una vista unificada del estado operativo.
- **AWS CloudTrail** es un servicio de gobernanza y auditoría de Amazon Web Services (AWS) que registra automáticamente las acciones de los usuarios y las llamadas a la API en su infraestructura. Permite identificar quién hizo qué, cuándo y desde dónde, facilitando la seguridad, el cumplimiento normativo y la resolución de problemas.
- **Amazon QuickSight** es un servicio de Business Intelligence (BI) rápido, basado en la nube y nativo de AWS, que permite crear y compartir paneles interactivos (dashboards), visualizaciones de datos y análisis sin necesidad de gestionar servidores. Funciona bajo un modelo "serverless", es escalable y utiliza el motor en memoria SPICE para obtener un rendimiento rápido.
- **AWS Config** es un servicio de gobernanza que monitorea, registra y evalúa continuamente las configuraciones de los recursos de AWS. Permite auditar cambios históricos, evaluar el cumplimiento de políticas de seguridad y automatizar la remediación de configuraciones incorrectas. Es clave para la seguridad, el cumplimiento normativo y el control de costos.
- **AWS Trusted Advisor:** Herramienta que analiza el entorno de AWS y ofrece recomendaciones basadas en buenas prácticas extraídas de miles de clientes. Trusted Advisor sugiere acciones para *ahorrar dinero*, *mejorar la disponibilidad y el rendimiento* o *cerrar huecos de seguridad*. Con soporte básico se accede a algunas verificaciones. Con planes Business o Enterprise se tiene acceso completo a todos los checks. Por ejemplo, puede identificar instancias EC2 infrautilizadas para apagarlas y ahorrar costes.

**Mensajería y otros**

- **Amazon Simple Queue Service (SQS)** es un servicio de colas de mensajes totalmente gestionado por AWS que permite desacoplar y escalar microservicios, sistemas distribuidos y aplicaciones sin servidor. Facilita el envío, almacenamiento y recepción de mensajes entre componentes de software a cualquier volumen, garantizando la entrega y eliminando la necesidad de gestionar middleware complejo
- **Amazon AWS Marketplace** es una tienda digital curada por Amazon que permite a los clientes encontrar, comprar, implementar y gestionar rápidamente software, servicios y datos de terceros compatibles con la nube de Amazon Web Services (AWS). Ofrece miles de soluciones de proveedores independientes, incluyendo SaaS, máquinas virtuales (AMI) y herramientas de seguridad, simplificando la adquisición y facturación bajo una misma cuenta.
- **SNS (Simple Notification Service)**: Envía notificaciones a muchos suscriptores (Pub/Sub, emails, SMS).

## Facturación y gestión de costes

AWS ofrece herramientas para controlar los gastos y entender los costes:

- **Modelos de precios:** AWS cobra mayoritariamente por consumo. En EC2, por ejemplo, existen instancias **bajo demanda** (pago por hora o segundo, sin compromiso previo), instancias **reservadas** o **Savings Plans** (compromiso por 1 a 3 años con descuento) y **Spot** (capacidad no usada, hasta ~90% más barato). Los servicios de almacenamiento y datos también se cobran según el uso y el nivel. Es clave conocer estas opciones para optimizar costes.
  - **Amazon Spot Instances** son máquinas virtuales de Amazon EC2 que permiten utilizar la capacidad de cómputo sobrante de AWS con descuentos de hasta el 90% respecto a los precios bajo demanda. Son ideales para cargas de trabajo flexibles, sin estado y tolerantes a interrupciones, ya que AWS puede recuperar la instancia con un aviso de 2 minutos.
  - **AWS Reserved Instances (RI)** modelo de precios de Amazon Web Services que permite reservar capacidad de cómputo (instancias EC2) o bases de datos (RDS) por un periodo de 1 a 3 años, ofreciendo descuentos de hasta el 72% respecto a los precios bajo demanda. Son ideales para cargas de trabajo estables y predecibles
  - **AWS On-Demand (bajo demanda)** máquinas virtuales de Amazon EC2 que permiten pagar por la capacidad de cómputo por segundo o por hora, sin compromisos a largo plazo ni pagos iniciales. Son ideales para cargas de trabajo a corto plazo, impredecibles o que no se pueden interrumpir.
  - **AWS Dedicated Host** es un servidor físico de Amazon EC2 totalmente dedicado a una sola cuenta de cliente. Permite utilizar licencias de software propias (como Windows o SQL Server) vinculadas a sockets o núcleos físicos, cumpliendo con estrictos requisitos de conformidad. Ofrece visibilidad y control sobre la ubicación de las instancias
- **Facturación consolidada de Amazon AWS** es una funcionalidad de AWS Organizations que agrupa los cargos de múltiples cuentas de AWS en una sola factura, permitiendo una gestión financiera centralizada. Sus principales ventajas son la simplificación contable, una única fecha de pago, y descuentos por volumen acumulados de todas las cuentas. Ventajas clave:
  - Una sola factura: Simplifica la administración al consolidar los cargos de todas las cuentas vinculadas, reduciendo el papeleo.
  - Descuentos por volumen (Pricing Volume Discounts): Permite combinar el uso de servicios de todas las cuentas para alcanzar niveles de precios más bajos (descuentos por volumen) en servicios como S3, EC2 y Savings Plans, lo que reduce los costos generales.
  - Gestión eficiente y visibilidad: La cuenta principal ("master account") puede visualizar y desglosar los costos y el uso de cada cuenta miembro, facilitando la auditoría y control de costos.
  - Pagos simplificados: Estandariza los ciclos de facturación, lo que mejora la gestión del flujo de caja al tener fechas de vencimiento unificadas.
  - Independencia de cuentas: Aunque la facturación está centralizada, todas las cuentas miembros siguen siendo independientes en términos de recursos y seguridad
 
Basic: Gratis. Solo consultas de facturación.

Developer: Soporte en horario comercial por email. (A partir de aquí hay soporte técnico).

Business: 24/7 por teléfono/chat. Casos ilimitados.

Enterprise: Incluye TAM (Technical Account Manager) y soporte consultivo.

- **Etiquetado y reportes:** Se recomienda usar **tags (etiquetas)** en recursos para atribuir costes a proyectos o equipos. AWS Cost and Usage Reports y Cost Explorer permiten analizar el consumo histórico y las tendencias.
- **AWS Budgets:** Herramienta para establecer presupuestos y alertas. Permite definir alertas (por ejemplo, enviar un correo o disparar una acción cuando se supere el 80% del presupuesto mensual). Se pueden crear presupuestos de coste total, de uso de recursos o de cobertura (RI/Savings Plans) y recibir notificaciones vía email o SNS.
- **AWS Cost Explorer:** Interfaz para visualizar y analizar los costes y el uso históricos. Permite crear informes personalizados, ver tendencias de gasto de los últimos 13 meses y pronosticar hasta 18 meses. También ofrece recomendaciones de instancias reservadas óptimas.
- **AWS Compute Optimizer** es un servicio de machine learning que analiza el uso histórico de tus recursos en la nube (instancias EC2, volúmenes EBS, funciones Lambda, ECS en Fargate) para recomendar configuraciones óptimas. Ayuda a reducir costos y mejorar el rendimiento, evitando el sobreaprovisionamiento o infrautilización
- **AWS Pricing Calculator** es una herramienta web gratuita de Amazon Web Services que permite modelar, estimar y planificar los costos de arquitectura en la nube antes de implementarlos. Ayuda a usuarios nuevos y avanzados a proyectar gastos mensuales de servicios como EC2, S3 o RDS, facilitando la toma de decisiones financieras y presupuestarias
- **Amazon Reserved Instances (RI)** son un modelo de precios de AWS que ofrece descuentos significativos (hasta un 72% menos que bajo demanda) a cambio de un compromiso de uso constante durante 1 o 3 años. Garantizan capacidad de reserva en una zona específica, ideal para cargas de trabajo estables y predecibles.

Un **ejemplo práctico**: una empresa puede crear en AWS Budgets un presupuesto mensual fijo y configurar una alerta por correo si el coste real alcanza el 80% del presupuesto. Así, se controlan los gastos de forma proactiva y se pueden tomar medidas (p. ej., apagar recursos no críticos) antes de exceder el límite. Para migraciones de datos, se puede usar **AWS Snowball** (un dispositivo físico seguro) para trasladar petabytes de información a AWS sin depender de la red pública. El dispositivo se envía al cliente, se copian los datos y luego se devuelve a AWS, lo que acelera migraciones masivas.

Es importante crear una alarma de costes, es decir, poner limites desde el banco a la tarjeta bancaria, ya que no se puede limitar el gasto mensual desde el cloud.

## Soporte técnico (AWS Support)

Todos los clientes de AWS disponen de soporte *Básico* gratuito, que incluye acceso 24/7 a documentación, foros (AWS) y un número limitado de **Trusted Advisor Checks** (analiza tu entorno de AWS y ofrece recomendaciones en tiempo real basadas en las mejores prácticas de AWS) básicos para límites de servicio. Para soporte técnico con tiempos de respuesta garantizados, se usan planes de pago: **Developer**, **Business** y **Enterprise**. Estos ofrecen asistencia 24/7 (teléfono, chat y email) y recursos especializados:

- Developer: soporte básico para una sola persona, con atención en horario comercial.
- Business: ideal para cargas de producción, incluye atención 24/7 con tiempos de respuesta desde 1 hora (p. ej., 12 a 24 h para soporte general).
- Enterprise: para negocios críticos, e incluye además un TAM (Técnico de Cuenta Designado) y revisiones proactivas de arquitecturas.

En resumen, los planes de pago proporcionan **soporte técnico 24/7** y **recomendaciones ilimitadas** de Trusted Advisor. Por ejemplo, los planes Business y Enterprise permiten crear casos ilimitados y acceder a asesoramiento experto en arquitectura.

- **AWS Cloud Adoption Framework (AWS CAF)** es un marco estructurado de Amazon Web Services (AWS) que proporciona mejores prácticas y orientación para acelerar la transformación digital y la adopción de la nube. Ayuda a alinear las estrategias empresariales con la tecnología, cubriendo áreas como seguridad, personas y operaciones para minimizar riesgos. Perspectivas clave de AWS CAF (3.0):
  - Comercial (Business): Asegura que las inversiones en la nube estén alineadas con los objetivos de negocio y contribuyan a acelerar la transformación digital.
  - Personas (People): Se enfoca en preparar y motivar al personal para el cambio, promoviendo una cultura de aprendizaje continuo y adaptabilidad.
  - Gobernanza (Governance): Facilita la coordinación y supervisión de iniciativas en la nube, ayudando a gestionar riesgos y prioridades organizativas.
  - Plataforma (Platform): Proporciona orientación para diseñar y escalar una arquitectura técnica sólida y flexible en la nube.
  - Seguridad (Security): Garantiza que los datos, aplicaciones y sistemas estén protegidos y cumplan con los requisitos de seguridad y conformidad.
  - Operaciones (Operations): Se asegura de que los servicios en la nube funcionen de manera fiable y eficiente, satisfaciendo las necesidades del negocio.

## Buenas prácticas en AWS

- **Responsabilidad Compartida:** AWS se encarga de la seguridad *de* la nube (infraestructura física, redes y centros de datos), mientras que el cliente es responsable de la seguridad *en* la nube (sistema operativo, aplicaciones, datos y configuraciones). Por ejemplo, AWS asegura la integridad del hardware y la virtualización, pero el usuario debe mantener los datos cifrados y los permisos de IAM bien configurados.

<img width="1818" height="784" alt="image" src="https://github.com/user-attachments/assets/d92afcb5-e11c-4d42-bad9-5c77a4e1354a" />

- **AWS Well-Architected Framework** es un conjunto de mejores prácticas, principios de diseño y guías de Amazon Web Services (AWS) para ayudar a arquitectos de la nube a construir infraestructura segura, de alto rendimiento, resiliente y eficiente. Se basa en seis pilares fundamentales, evaluando cargas de trabajo para optimizar costos y sostenibilidad. 
  - Excelencia operativa (Operational Excellence): Ejecutar y monitorear sistemas, mejorando procesos continuamente. -> Monitor, improve processes, automation
  - Seguridad (Security): Proteger información, sistemas y activos. -> Protect, data, encryption, identity
  - Fiabilidad (Reliability): Capacidad de recuperarse de fallos y escalar recursos. -> Recover, failure, fault tolerance, high availability, resilience
  - Eficiencia de rendimiento (Performance): Usar recursos computacionales de manera eficiente. -> Efficiency	Efficient use of resources, latency, scaling, performance
  - Optimización de costes (Cost Optimization): Evitar costos innecesarios y maximizar el retorno de inversión. -> Reduce cost, avoid waste, rightsizing
  - Sostenibilidad (Sustainability): Minimizar el impacto ambiental de la carga de trabajo. -> Environmental impact, energy

1️⃣ ¿Habla de fallos o recuperación? → Reliability

2️⃣ ¿Habla de velocidad o eficiencia? → Performance

3️⃣ ¿Habla de proteger datos? → Security

4️⃣ ¿Habla de ahorrar dinero? → Cost Optimization

5️⃣ ¿Habla de monitoreo y mejora continua? → Operational Excellence

## Redes básicas de AWS

Cada cuenta de AWS dispone de una **VPC (Virtual Private Cloud)** por región. En la VPC se definen subredes (públicas o privadas), rutas y gateways. Por ejemplo, una subred pública se conecta a Internet mediante una **Puerta de Internet (IGW)**, mientras que una subred privada usa una **NAT Gateway** para el tráfico saliente. Los **Security Groups** actúan como cortafuegos virtuales a nivel de instancia. AWS organiza sus centros de datos en **Regiones** (ubicaciones geográficas) y **Zonas de Disponibilidad** (centros independientes dentro de cada región), lo que permite diseñar aplicaciones multi-AZ para alta disponibilidad.

- Región: Área geográfica física (ej. París, Tokyo). Contiene 2 o más AZs.
- Zona de Disponibilidad (AZ): Uno o más centros de datos discretos con energía y red redundantes.
- Ubicaciones de Borde (Edge Locations): Puntos finales de la red CDN (CloudFront) para caché de baja latencia. Hay muchas más Edge Locations que Regiones.

<img width="977" height="320" alt="image" src="https://github.com/user-attachments/assets/47edb4d5-1d53-4b72-b339-16a0a6350552" />

A la hora de legir una región se debe tener en cuenta: requisitos legales, proximidad con clientes, servicios disponibles y precios.

**Route 53** es el servicio DNS de AWS. Traduce nombres de dominio a direcciones IP y se integra con balanceadores de carga. 

**Elastic Load Balancer** (ELB) reparte automáticamente tráfico de aplicaciones entre varias instancias en múltiples zonas, y solo envía tráfico a instancias “saludables”. Esto mejora la escalabilidad y la tolerancia a fallos.

<img width="1259" height="893" alt="image" src="https://github.com/user-attachments/assets/31e473bc-1598-4c65-8962-ff7f9fe1b60c" />

### Conceptos Básicos de Nombres de Dominio

<img width="1859" height="941" alt="image" src="https://github.com/user-attachments/assets/04105b96-60e8-402b-8c1d-53c04201878d" />

- **Top Level Domains (TLD)**: La última parte del dominio (.com, .net, .org)
- **Dominio desnudo (naked domain)**: El nombre más el TLD (ejemplo: [example.com](http://example.com))
- **Subdominio**: El dominio desnudo más algo delante de él ([www.example.com](http://www.example.com), [mail.example.com](http://mail.example.com), [app.example.com](http://app.example.com))
- **Importante**: [www.example.com](http://www.example.com) y [example.com](http://example.com) son dos dominios completamente diferentes - pueden tener sitios web distintos
- Por conveniencia, típicamente se redirige [www.example.com](http://www.example.com) a [example.com](http://example.com), pero no son lo mismo
- **FQDN (Fully Qualified Domain Name)**: Nombre de dominio descrito con el máximo detalle posible ([Server1.US-EAST.prod.example.com](http://Server1.US-EAST.prod.example.com))

<img width="1363" height="869" alt="image" src="https://github.com/user-attachments/assets/a2eff7ab-0962-4fbc-be1c-a32cfcf9c1d7" />

### Funcionamiento del DNS

- **Propósito del DNS**: Convertir nombres de dominio (que los humanos recuerdan fácilmente) en direcciones IP (que las computadoras necesitan)
- **Componentes clave del sistema DNS**:
    - Resolver: Inicia el proceso de resolución
    - Root DNS: Contiene información sobre servidores TLD (aproximadamente 13 clusters de servidores)
    - TLD DNS: Gestiona información sobre dominios desnudos dentro de cada TLD
    - Authoritative DNS: Mantiene información sobre todos los subdominios de un dominio desnudo específico

<img width="1752" height="1010" alt="image" src="https://github.com/user-attachments/assets/99810aee-22d6-4b25-96be-f723cb0243e7" />

### Flujo de Resolución DNS

- El resolver pregunta al Root DNS por la IP del dominio
- Root DNS responde con la IP de los servidores TLD apropiados
- El resolver pregunta al TLD DNS, que responde con la IP del servidor authoritative
- El resolver pregunta al authoritative DNS, que finalmente proporciona la IP del dominio
- Todo este proceso ocurre en fracciones de segundo cada vez que se busca un sitio web
- **Caché**: Una vez obtenida la IP, se guarda en caché local para evitar repetir el proceso
- **TTL (Time to Live)**: Determina cuánto tiempo permanece la IP en caché

### AWS Route 53

- **Función principal**: Actúa como DNS authoritative para nombres de dominio
- Route 53 responde preguntas sobre dominios y devuelve direcciones IP
- **Importante**: Route 53 NO enruta el tráfico - solo proporciona la IP al usuario, quien luego establece la conexión directamente
- Los usuarios pueden agregar dominios a Route 53 sin necesidad de registrarlos allí (pueden registrarse en GoDaddy u otros registradores)
- Se integra con otros servicios de AWS

<img width="1863" height="930" alt="image" src="https://github.com/user-attachments/assets/733246ff-a8e1-4614-bbc4-4450e00b9ffc" />

### Tipos de Registros DNS

- **A Record**: Apunta a una dirección IP (ejemplo: [example.com](http://example.com) → 52.16.9.3)
- **NS Record**: Dirección IP de los servidores de nombres
- **CNAME o Alias Record**: Un nombre de dominio apunta a otro ([www.example.com](http://www.example.com) → [example.com](http://example.com))
- **MX Records**: Para servidores de correo
- **SOA (Start of Authority)**: Establece la autoridad para el DNS - siempre presente por defecto
- **TXT Records**: Para validación adicional, como verificar propiedad del dominio

<img width="1773" height="927" alt="image" src="https://github.com/user-attachments/assets/75b84bfa-940d-4436-8926-0b5d0173d5f1" />

<img width="1846" height="1011" alt="image" src="https://github.com/user-attachments/assets/37a09a4e-b65a-4f74-97ad-eb52a814cca3" />

<img width="1839" height="1011" alt="image" src="https://github.com/user-attachments/assets/0131aaa3-f04c-44eb-a9de-d4b567b62f7a" />

<img width="1834" height="1017" alt="image" src="https://github.com/user-attachments/assets/e11f7f88-5407-4a81-ae16-8dc7e364aa7e" />

<img width="1773" height="1003" alt="image" src="https://github.com/user-attachments/assets/7c7949ac-78a9-475a-b78b-c43966e412b4" />

<img width="1599" height="994" alt="image" src="https://github.com/user-attachments/assets/d0870b32-08fc-4e7c-bf13-b451c76106c0" />

### Políticas de Enrutamiento en Route 53

- **Simple Routing Policy**:
    - Enrutamiento básico de un dominio a una dirección IP
- **Latency-Based Routing (LBR)**:
    - Enruta usuarios según la latencia entre su ubicación y las regiones disponibles
    - Route 53 conoce la latencia entre ubicaciones de usuarios y diferentes regiones de AWS
    - Devuelve la IP de la región con menor latencia
    - Requiere contenido idéntico en todas las regiones
- **Weighted Routing Policy**:
    - Distribuye consultas según porcentajes configurados
    - **Importante**: NO es balanceo de carga de tráfico - solo distribuye respuestas DNS
- **Geolocation Routing Policy**:
    - Enruta usuarios según su ubicación geográfica
    - Similar a cómo YouTube muestra contenido diferente según el país
    - Permite contenido específico por región o país
    - Opciones disponibles: por continente o por país
    - Para Estados Unidos, permite enrutamiento a nivel de estado
    - La ubicación se determina por el bloque de IP, no por GPS
- **Failover Routing Policy**:
    - Configuración primario/secundario (activo/standby)
    - Route 53 siempre devuelve la IP del primario
    - Cambia al secundario solo si el primario falla según health checks
    - El secundario puede ser un entorno completo o una página estática en S3 con mensaje de mantenimiento

### Políticas de Tráfico

- Permite combinar múltiples políticas de enrutamiento
- Ejemplo: Política de failover en el nivel superior, con weighted routing dentro del primario
- Crea configuraciones complejas para gestión de tráfico avanzada

### Hosted Zones

- Donde se agregan dominios a Route 53
- Pueden ser públicas (para internet) o privadas (solo dentro de VPC)
- Al crear una hosted zone, se generan automáticamente dos registros: NS y SOA
- Los name servers de Route 53 deben configurarse en el registrador del dominio

<img width="1408" height="768" alt="image" src="https://github.com/user-attachments/assets/d2e54c3a-7fd7-4f3a-8bb5-52a7355b9379" />

## Contenedores y orquestación

Un **contenedor** encapsula una aplicación con sus dependencias en un entorno portátil y ligero (p. ej., Docker). En AWS, los contenedores se pueden ejecutar mediante **Amazon ECS** o **EKS**. *Kubernetes* (open-source) es un sistema de orquestación que automatiza el despliegue, el escalado y la gestión de aplicaciones en contenedores. AWS ofrece **EKS** como servicio gestionado de Kubernetes y **Fargate** para ejecutar contenedores sin administrar servidores. Por ejemplo, una aplicación web puede desplegarse en un clúster ECS con varios contenedores que se escalan según la demanda.

## DevOps e Infraestructura como Código

La cultura **DevOps** fomenta la colaboración entre desarrollo y operaciones para entregar software con frecuencia y calidad, mediante automatización y CI/CD. En AWS, servicios como **CodeCommit** (repositorio Git), **CodeBuild** (compilación) y **CodeDeploy/CodePipeline** (entrega continua) ayudan a implementar DevOps. Por ejemplo, un cambio en el código puede activar automáticamente una pipeline que ejecute pruebas y despliegue en AWS. La **Infraestructura como Código (IaC)** permite definir recursos (redes, servidores y bases) en archivos (JSON o YAML). 

**AWS CloudFormation** es un servicio de IaC que modela y aprovisiona recursos de AWS de forma automática a partir de plantillas.

**AWS CodeStar** es un servicio unificado en la nube que facilita la creación, gestión y trabajo en proyectos de desarrollo de software en Amazon Web Services (AWS). Permite configurar rápidamente cadenas de herramientas CI/CD (integración y entrega continuas), incluyendo código fuente, compilación y despliegue, además de integrar gestión de tareas (Jira) y paneles de control del equipo.

**Amazon Lightsail** es el servicio de servidor privado virtual (VPS) de AWS diseñado para ser sencillo, rápido y económico. Incluye todo lo necesario para lanzar un proyecto web (instancias, almacenamiento, bases de datos, redes, IP estática) con precios fijos mensuales, siendo ideal para sitios web, aplicaciones pequeñas, blogs (WordPress) y entornos de desarrollo

## Interoperabilidad y portabilidad

En la nube, **interoperabilidad** significa que distintos sistemas o nubes pueden comunicarse e intercambiar datos usando estándares comunes. La **portabilidad** es la capacidad de trasladar cargas de trabajo (aplicaciones y datos) entre proveedores o entre entornos local y nube con cambios mínimos. Por ejemplo, almacenar datos en formatos abiertos o usar contenedores puede facilitar mover una aplicación de AWS a Azure sin dependencias propietarias. Estos conceptos son clave para evitar el *vendor lock-in* y aprovechar múltiples nubes o centros locales según convenga.

## Ejemplos prácticos de uso y migración

- **Migración de datos grandes:** Usar AWS Snowball para copiar petabytes de información desde un centro de datos local a S3 (dispositivo físico seguro que se envía al cliente, se carga con datos y se devuelve).
- **Amazon S3 File Gateway** es un servicio de almacenamiento híbrido que permite a las aplicaciones locales (on-premises) acceder a datos en la nube de Amazon S3 utilizando protocolos estándar de archivos como NFS o SMB. Facilita la migración, copia de seguridad y almacenamiento en la nube al funcionar como un puente entre servidores locales y S3, ofreciendo almacenamiento casi ilimitado y caché local para baja latencia.
- **AWS Application Discovery Service (ADS)** es un servicio de Amazon Web Services diseñado para ayudar a las empresas a planificar su migración a la nube. Recopila automáticamente datos detallados de configuración, rendimiento y dependencia (conexiones TCP) de servidores locales y bases de datos, integrándose con AWS Migration Hub para facilitar la migración
- **AWS Migration Evaluator (anteriormente TSO Logic)** es un servicio gratuito de Amazon Web Services (AWS) que ayuda a las empresas a crear casos de negocio basados en datos para planificar la migración a la nube. Recopila información sobre la infraestructura local (servidores, bases de datos) para recomendar opciones de implementación rentables, acelerando la toma de decisiones y reduciendo costos. 
- **Estrategia de migración (7 R’s):** Al planear la migración de aplicaciones a la nube, existen varias estrategias: 

  - **Rehost (Lift & Shift)**: trasladar la aplicación a la nube *sin cambiar* su código ni arquitectura. Es la forma más rápida: simplemente se mueve (p.ej. máquinas virtuales) tal cual, obteniendo beneficios de la nube (reducción de costos de datacenter) sin reescribir nada.
  - **Repurchase (Drop & Shop)**: se reemplaza la solución existente por una alternativa SaaS o un servicio gestionado equivalente. Por ejemplo, sustituir un software comprado por una versión en la nube o un servicio PaaS específico. Se “dejade migrar” el software anterior y se adquiere otro licenciado para la nube.
  - **Replatform (Lift & Reshape)**: similar a rehost, pero con *algunas optimizaciones menores*. Se transfieren las aplicaciones a la nube realizando cambios limitados (p.ej. actualizar versión de SO, reconfigurar parámetros, usar bases de datos gestionadas) para aprovechar mejor características cloud, sin reescribir la app.
  - **Refactor (Re-architect)**: re-diseñar la aplicación para que sea *nativa de la nube*. Esto implica re-implementar partes significativas (p.ej. convertir monolitos en microservicios o usar funciones serverless). La app se replantea aprovechando al máximo escalabilidad, resiliencia y otros servicios cloud.
  - **Retire (Retirar)**: identificar aplicaciones obsoletas o no críticas y **darlas de baja**. A menudo las migraciones revelan software que ya no se usa; en lugar de moverlo, simplemente se elimina.
  - **Retain (Conservar)**: mantener la aplicación *donde está*, al menos por ahora. Puede aplazarse su migración o decidir que no es adecuada para el cloud.
  - (A veces se agrega **Relocate**: mover cargas virtualizadas sin cambios, p.ej. VMs con VMware hacia la nube, sin modificar la app).

<img width="1002" height="664" alt="image" src="https://github.com/user-attachments/assets/37db5792-9a40-484a-b0b1-12c46a6ecbda" />

- **Optimización de costes:** Por ejemplo, una startup puede lanzar una aplicación en EC2 bajo demanda y, cuando se estabilice, reservar capacidad para reducir gastos. También puede habilitar Auto Scaling para reducir servidores en horas valle.
- **Presupuestos y alertas:** Crear presupuestos mensuales en AWS Budgets y configurar notificaciones (SNS o email) cuando se aproxime el límite. Como práctica, se puede fijar una alerta al 80% del presupuesto para revisar el gasto.
- **Seguridad:** Implementar políticas de IAM estrictas y habilitar MFA. Por ejemplo, exigir que solo personal con permisos adecuados pueda lanzar instancias EC2 de producción, mientras que en desarrollo se usan permisos más limitados.
- **Alta disponibilidad:** Desplegar instancias en múltiples AZ dentro de una región. Por ejemplo, configurar una base de datos RDS con Multi-AZ para replicar datos en otra zona y soportar fallos.
- **Contenedores y Serverless:** Para una app web con picos de tráfico, se puede ejecutar el backend en contenedores (ECS o EKS) y usar funciones Lambda para tareas puntuales (procesar imágenes o enviar emails), aprovechando el escalado automático.
- **AWS DataSync** es un servicio de transferencia de datos en línea, seguro y gestionado que automatiza y acelera el movimiento de grandes volúmenes de datos entre sistemas de almacenamiento locales (on-premises), otras nubes (como Azure o Google Cloud) y los servicios de almacenamiento de AWS (S3, EFS, FSx). Facilita migraciones, réplicas y archivado, gestionando automáticamente la infraestructura, el cifrado y la validación de la integridad

## Glosario de términos clave

- **CAPEX (Capital Expenditure):** Gastos de capital. Inversiones iniciales en activos duraderos (servidores, hardware y licencias perpetuas). En la nube, el CAPEX se minimiza.
- **OPEX (Operational Expenditure):** Gastos operativos. Costes recurrentes de operación (consumo de recursos, suscripciones y licencias anuales). En la nube, la mayoría de costes son OPEX (pago por uso).
- **TCO (Total Cost of Ownership):** Costo total de propiedad. Suma de todos los gastos de un sistema en un período (CAPEX + OPEX + mantenimiento + actualizaciones).
  
<img width="784" height="568" alt="image" src="https://github.com/user-attachments/assets/ed52668c-0f19-40d4-a44b-fc03a75608c1" />

- **IaaS/PaaS/SaaS:** Modelos de servicio en la nube. IaaS (Infraestructura como Servicio) entrega recursos básicos (máquinas virtuales y almacenamiento), PaaS (Plataforma) ofrece entornos listos para desarrollar (bases de datos gestionadas y frameworks) y SaaS (Software) entrega aplicaciones completas por Internet.
- **Contenedor:** Entorno ligero y portátil que encapsula una aplicación y sus dependencias (por ejemplo, Docker), aislando procesos sobre un kernel compartido.
- **Kubernetes:** Plataforma open source para **orquestar contenedores**. Automatiza el despliegue, el escalado y la administración de aplicaciones en contenedores.
- **DevOps:** Metodología y cultura de desarrollo y operaciones orientada a entregar software de forma continua mediante automatización y colaboración.
- **Interoperabilidad:** Capacidad de sistemas o nubes diferentes para comunicarse e intercambiar datos usando estándares comunes.
- **Portabilidad:** Facilidad para trasladar datos, aplicaciones o cargas de trabajo entre entornos de nube o entre nube y local, minimizando dependencias de proveedor.
- **Región y Zona de Disponibilidad (AZ):** AWS organiza su infraestructura en **regiones** (localidades geográficas grandes) y cada región tiene varias **AZ** (centros de datos aislados). Desplegar en múltiples AZ mejora la disponibilidad.
- **Máquina virtual (EC2):** Servidor virtual en la nube que ejecuta un sistema operativo completo. Se cobra por tiempo de uso.
- **Instancia Spot:** Tipo de pago de muy bajo coste para computación que aprovecha capacidad no usada. AWS puede interrumpirla con 2 minutos de aviso.
- **Elasticidad:** Capacidad de escalar recursos (subir o bajar) dinámicamente según la demanda.
- **Auto Scaling:** Servicio que ajusta automáticamente el número de instancias EC2 según métricas (uso de CPU, tráfico, etc.).
- **ELB (Elastic Load Balancer):** Servicio que reparte el tráfico de red entre múltiples instancias (mejora la escalabilidad y la tolerancia a fallos).
- **Route 53:** Servicio DNS de AWS para traducir dominios a IPs y balancear tráfico globalmente.
- **VPC (Virtual Private Cloud):** Red virtual aislada en AWS donde se despliegan recursos. Funciona como una red propia en la nube.
- **Grupo de Seguridad:** Firewall virtual a nivel de instancia EC2. Controla qué tráfico entra y sale de la instancia.
- **MFA (Autenticación Multifactor):** Seguridad adicional que exige, además de la contraseña, un código temporal (p. ej., de una app móvil) para iniciar sesión.
- **Trusted Advisor:** Servicio que realiza comprobaciones automáticas de buenas prácticas (costes, rendimiento y seguridad) y sugiere mejoras.
- **AWS Budgets / Cost Explorer:** Herramientas para gestionar costes. Budgets crea alertas de gasto. Cost Explorer visualiza y analiza el uso pasado y ofrece predicciones.
- **Snowball:** Dispositivo físico de AWS para migrar grandes volúmenes de datos a la nube (petabytes) de forma segura.

**Referencias:** Documentación oficial de AWS y guías de estudio sobre conceptos de computación en la nube, así como recursos educativos proporcionados por AWS. Cada sección incluye enlaces a la documentación oficial para profundizar en los servicios relevantes.

[Amazon EC2 - Capacidad de computación segura y de tamaño ajustable - AWS](https://aws.amazon.com/es/ec2/pricing/)

[¿Qué es Amazon VPC? - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html)

[Controlar el tráfico hacia los recursos de AWS mediante grupos de seguridad - Amazon Virtual Private Cloud](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html)

[¿Qué es Elastic Load Balancing? - Elastic Load Balancing](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)

[Usuarios de IAM - AWS Identity and Access Management](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html)

[Gestione sus costes con AWS presupuestos - AWS Gestión de costes](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html)

[Análisis de los costes y el uso con AWS Cost Explorer - AWS Gestión de costes](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html)

[AWS Snowball | Secure Edge Computing and Offline Data Transfer | Amazon Web Services](https://aws.amazon.com/snowball/)

[Comparación de planes de AWS Support — Características de AWS Support — AWS](https://aws.amazon.com/es/premiumsupport/plans/)

[Modelo de responsabilidad compartida. Amazon Web Services (AWS)](https://aws.amazon.com/es/compliance/shared-responsibility-model/)

[AWS Well-Architected: Desarrolle aplicaciones seguras y eficaces en la nube](https://aws.amazon.com/es/architecture/well-architected/)

[AWS Trusted Advisor - AWS Support](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html)

[Aprovisionamiento de infraestructura como código - AWS CloudFormation - AWS](https://aws.amazon.com/es/cloudformation/)

https://youtu.be/8OKfNHciBNg
