# Guía de Estudio AWS Certified Cloud Practitioner (CLF-C02)

## Cobertura oficial del examen

| Dominio | Peso | Lo que se debe dominar |
| --- | --- | --- |
| **Conceptos de la nube** | **24 %** | propuesta de valor de AWS, Well-Architected, migración, CAF y economía cloud |
| **Seguridad y cumplimiento** | **30 %** | responsabilidad compartida, IAM, cifrado, auditoría, cumplimiento y servicios de seguridad |
| **Tecnología y servicios en la nube** | **34 %** | métodos de acceso y despliegue, infraestructura global, cómputo, bases de datos, redes, almacenamiento, analítica, IA/ML y otras categorías |
| **Facturación, precios y soporte** | **12 %** | modelos de compra, herramientas de costos, soporte de AWS, recursos técnicos, socios y Marketplace |

---

## Dominio 1. Conceptos de la nube

### Beneficios de la nube

| Concepto | Qué es | Cómo recordarlo | Cómo se suele preguntar |
| --- | --- | --- | --- |
| **Agilidad** | capacidad de probar, desplegar y cambiar con rapidez | reduce el tiempo entre idea y puesta en producción | "experimentar rápido", "lanzar en minutos", "innovar con baja fricción" |
| **Elasticidad** | ajuste dinámico de capacidad según la demanda, tanto al alza como a la baja | la capacidad acompaña la demanda y luego vuelve a su nivel normal | picos de tráfico, campañas, cierres mensuales, demanda variable |
| **Escalabilidad** | capacidad de soportar mayor carga añadiendo o ampliando recursos | la arquitectura puede crecer sin rediseñarse por completo | "crecer con el negocio", "más usuarios", "más transacciones" |
| **Alta disponibilidad** | diseño para mantener el servicio operativo pese a fallos parciales | se evita que un único fallo detenga el servicio | despliegue en varias AZ, redundancia, continuidad |
| **Alcance global** | posibilidad de desplegar cerca de usuarios y datos en distintas ubicaciones | AWS ya dispone de presencia global preparada para usar | baja latencia global, usuarios distribuidos, expansión internacional |
| **Economías de escala** | ahorro derivado del volumen masivo de AWS | AWS compra y opera a gran escala y traslada parte del ahorro | "¿por qué AWS reduce precios?" |
| **Pago por uso** | modelo en el que se paga por consumo real y no por capacidad comprada por adelantado | el costo acompaña al uso del servicio | CapEx a OpEx, eliminar inversión inicial, flexibilidad financiera |

- Rapidez para experimentar y lanzar ✅ **agilidad** ❌ elasticidad
- Subir y bajar capacidad según demanda ✅ **elasticidad** ❌ alta disponibilidad
- Tolerar el fallo de una zona ✅ **alta disponibilidad** ❌ alcance global
- Acercar contenido a usuarios internacionales ✅ **alcance global** ❌ solamente alta disponibilidad
- Reducción de inversión inicial ✅ **pago por uso / OpEx** ❌ economías de escala

> La escalabilidad es la capacidad o acción de crecer para soportar una mayor carga de trabajo de forma vertical u horizontal; la elasticidad es la capacidad de aprovisionar y liberar recursos automáticamente y en tiempo real según la demanda actual. Escalabilidad = potencial de crecimiento; Elasticidad = adaptación dinámica.

### Well-Architected Framework

**Qué es**

Es el marco de referencia para evaluar la calidad arquitectónica de una carga de trabajo en AWS. En el examen se suele preguntar por el pilar correcto o por la diferencia entre dos pilares cercanos.

| Pilar | Qué prioriza | Palabras clave | Típica pregunta |
| --- | --- | --- | --- |
| **Excelencia operativa (Operational Excellence)** | operaciones, automatización, cambios pequeños y reversibles, aprendizaje continuo | despliegues automatizados, runbooks, IaC, mejora operativa, documentación | "La empresa quiere automatizar sus despliegues y aprender de los fallos operativos..." |
| **Seguridad (Security)** | protección de datos, identidades, trazabilidad, controles | mínimo privilegio, cifrado, auditoría, detección | "¿Qué pilar se enfoca en asegurar que solo los usuarios autorizados accedan a los recursos?" |
| **Fiabilidad (Reliability)** | recuperación ante fallos, continuidad, capacidad de adaptarse | multi-AZ, recuperación automática, resiliencia | "Un sistema debe seguir funcionando incluso si un centro de datos entero falla..." |
| **Eficiencia del rendimiento (Performance Efficiency)** | elección correcta de recursos y tecnologías para la carga | selección de recursos de cómputo, serverless, globalización, elasticidad | "La empresa quiere usar Serverless (Lambda) para no gestionar servidores y mejorar la velocidad..." |
| **Optimización de costos (Cost Optimization)** | eliminar gasto innecesario y ajustar al uso real | right-sizing, apagado de recursos, precios adecuados, servicios gestionados, dejar de gastar en centros de datos | "¿Qué pilar recomienda analizar el gasto para pagar solo por lo que realmente se necesita?" |
| **Sostenibilidad (Sustainability)** | reducir impacto ambiental y uso ineficiente de recursos | mejor utilización, menos sobreaprovisionamiento, huella de carbono | "¿Qué pilar se centra en la eficiencia energética y el impacto ambiental a largo plazo?" |

¿Fiabilidad o Excelencia Operativa?

- Si la pregunta habla de que el sistema sobreviva a un fallo: es Fiabilidad.
- Si la pregunta habla de cómo el equipo humano gestiona el sistema o automatiza el código: es Excelencia Operativa.

¿Rendimiento o Costo?
- Si se pide la solución más barata: es Costo.
- Si se pide la solución que mejor aproveche la tecnología (aunque sea más cara): es Rendimiento.

¿Seguridad o Fiabilidad?
- Si el sistema se cae por un hacker: es Seguridad.
- Si el sistema se cae por una inundación o exceso de tráfico: es Fiabilidad.

Ejemplos de servicio de AWS para cada pilar:
- Excelencia Operativa: AWS CloudFormation (IaC -> Infrastructure as Code).
- Seguridad: AWS IAM / KMS.
- Fiabilidad: Amazon EC2 Auto Scaling.
- Rendimiento: Amazon CloudFront (baja latencia).
- Costo: AWS Cost Explorer / Budgets.
- Sostenibilidad: Customer Carbon Footprint Tool.

### AWS Cloud Adoption Framework (AWS CAF)

**Qué es**

Es un marco para planificar la adopción de la nube a nivel organizativo, es decir, un marco que ayuda a las empresas a crear un plan de acción para su transformación digital. No debe confundirse con una checklist de arquitectura.

#### Resultados de negocio que AWS CAF busca acelerar

* **Reducción del riesgo empresarial:** No se trata solo de seguridad, sino de **resiliencia**. La nube permite recuperarse de desastres y evitar caídas de servicio (fiabilidad), lo que protege la reputación y las finanzas.
* **Mejora del rendimiento ESG (Social, Ambiental y Gobernanza):** Aquí es donde entra la **Sostenibilidad**. Al usar la infraestructura eficiente de AWS, las empresas reducen su huella de carbono y mejoran su transparencia de datos.
* **Aumento de los ingresos:** Permite crear productos nuevos y lanzarlos al mercado más rápido (**Time-to-market**). Si puedes experimentar barato y rápido, generas más dinero.
* **Aumento de la eficiencia operativa:** Automatizar tareas repetitivas y reducir el costo de mantener centros de datos físicos para que el equipo dedique más tiempo a actividades de mayor valor.


#### Las 6 perspectivas del AWS CAF

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a466ce4b-0f90-49dd-88d9-63711c20f02a" />

Fuente: https://medium.com/@vasanthabalaji/aws-cloud-adoption-framework-ad11d3623150

#### A. Perspectivas de Capacidades Empresariales (Enfocadas en estrategia)

1. **Negocios (Business):** Se centra en asegurar que las inversiones en la nube aceleren la transformación digital y se traduzcan en resultados de negocio medibles.
2. **Personas (People):** Actúa como puente entre negocio y tecnología para impulsar cultura, liderazgo, estructura organizativa, formación y desarrollo de capacidades.
3. **Gobernanza (Governance):** Ayuda a orquestar las iniciativas cloud maximizando los beneficios y minimizando los riesgos mediante políticas, cumplimiento, control financiero y mecanismos de decisión.

#### B. Perspectivas de Capacidades Técnicas (Enfocadas en la implementación)

4. **Plataforma (Platform):** Se enfoca en construir una plataforma cloud escalable, híbrida y de nivel empresarial para modernizar cargas existentes e implantar nuevas soluciones cloud-native.
5. **Seguridad (Security):** Busca garantizar la confidencialidad, integridad y disponibilidad de los datos y de las cargas de trabajo mediante controles de identidad, cifrado, detección y cumplimiento.
6. **Operaciones (Operations):** Garantiza que los servicios cloud se entreguen y operen con el nivel de servicio que necesita el negocio a través de monitorización, automatización, respuesta a incidentes y mejora continua.

| Perspectiva | Qué se debe recordar | Ejemplo profesional |
| --- | --- | --- |
| **Negocios (Business)** | Alinea la inversión cloud con objetivos estratégicos y resultados de negocio. | Justificar la migración de una plataforma de atención al cliente porque reduce el tiempo de lanzamiento y mejora el margen operativo. |
| **Personas (People)** | Prepara a la organización para trabajar en cloud con nuevos roles, capacidades y cultura. | Definir un plan de formación y rediseñar roles para desarrollo, operaciones y seguridad en un modelo cloud. |
| **Gobernanza (Governance)** | Establece reglas, controles y métricas para dirigir la adopción cloud. | Implantar políticas de etiquetado, presupuestos, revisiones de cumplimiento y criterios de aprobación para nuevas cuentas. |
| **Plataforma (Platform)** | Diseña la base técnica sobre la que se desplegarán y operarán las cargas. | Construir una landing zone con redes, identidad federada, automatización e infraestructura como código. |
| **Seguridad (Security)** | Protege identidades, datos y cargas de trabajo con controles consistentes. | Aplicar IAM, cifrado, registro de actividad, detección de amenazas y evidencias de cumplimiento en un entorno regulado. |
| **Operaciones (Operations)** | Opera y mantiene los servicios cloud al nivel que requiere el negocio. | Gestionar monitorización, parches, incidentes, automatización operativa y objetivos de disponibilidad de una aplicación crítica. |

| Si la pregunta dice... | La respuesta es Perspectiva... |
| --- | --- |
| "Alinear la inversión cloud con objetivos estratégicos o resultados financieros" | **Negocios (Business)** |
| "Capacitación, cambio cultural, liderazgo o reorganización de equipos" | **Personas (People)** |
| "Políticas, cumplimiento, control de costes, riesgos o gobierno de iniciativas" | **Gobernanza (Governance)** |
| "Landing zone, arquitectura cloud, modernización, escalabilidad o base técnica" | **Plataforma (Platform)** |
| "Cifrado, IAM, protección de datos, auditoría o detección de amenazas" | **Seguridad (Security)** |
| "Incidentes, monitorización, parches, operación diaria o niveles de servicio" | **Operaciones (Operations)** |

> **Nota importante:** No confundir el **CAF** (estrategia de adopción, ayuda a una organización a adoptar la nube) con el **Well-Architected Framework** (diseño técnico de una carga concreta de trabajo). El CAF es para "toda la empresa", el Well-Architected es para "una aplicación específica".

### Migración a la nube

#### Las 7 Rs

| Estrategia | ¿Qué es? | Cuándo usarla (Palabras clave) |
| --- | --- | --- |
| **Rehost** (Lift & Shift) | Mover la aplicación sin cambios a una instancia EC2. | Migración rápida, poco tiempo para cambios, bajo costo inicial. |
| **Replatform** (Lift, Tinker & Shift) | Pequeñas optimizaciones sin cambiar el código central (ej. mover la DB a RDS). | Quieres beneficios de servicios gestionados sin reescribir la app. |
| **Refactor** (Re-architect) | Reescribir la app para que sea nativa de la nube (ej. usar Lambda o Microservicios). | Necesitas máxima escalabilidad, agilidad y rendimiento. Es la más cara/lenta. |
| **Relocate** | Mover cargas de trabajo de VMware a AWS sin cambiar nada. | Usas VMware en on-prem y quieres seguir usándolo en la nube. |
| **Repurchase** (Drop and Shop) | Abandonar el software actual y comprar una versión SaaS. | Pasar de un CRM antiguo a Salesforce o de Email propio a Office 365. |
| **Retain** | No hacer nada por ahora. Mantenerlo en on-premise. | Aplicaciones que no se pueden migrar por cumplimiento o latencia. |
| **Retire** | Eliminar la aplicación. | Aplicaciones que ya no se usan o son redundantes. |

#### Herramientas y recursos de migración

| Recurso o servicio | Qué es | Cómo suele caer | Aspectos relevantes |
| --- | --- | --- | --- |
| **AWS Application Discovery Service** | Servicio de descubrimiento que recopila información sobre servidores, uso, dependencias y características del entorno actual. | descubrimiento previo a migración | se usa para entender qué existe antes de migrar; no mueve servidores ni datos por sí solo |
| **Migration Evaluator** | Herramienta para construir el caso financiero de la migración comparando costos actuales con costos estimados en AWS. | justificar negocio y costos | se enfoca en TCO, ahorro y planificación económica; no ejecuta la migración |
| **AWS Migration Hub** | Consola central para seguir el estado y progreso de varias migraciones desde un único lugar. | panel de seguimiento | coordina y visualiza migraciones de distintas herramientas, pero no migra cargas directamente |
| **AWS Application Migration Service** | Servicio orientado a rehost que replica servidores hacia AWS para migrarlos con cambios mínimos. | mover servidores con cambios mínimos | útil para lift and shift; está pensado para servidores y aplicaciones, no para migración lógica de bases de datos |
| **AWS DataSync** | Servicio de transferencia de datos por red entre entornos on-premises y servicios de almacenamiento de AWS. | mover datos por red de forma acelerada y gestionada | sirve para transferir datos a **S3**, **EFS** o **FSx**; automatiza, acelera y programa transferencias, y no requiere mover dispositivos físicos |
| **AWS Snow Family** | Familia de dispositivos físicos para trasladar grandes volúmenes de datos cuando la red no es suficiente o no resulta práctica. | poco ancho de banda o gran volumen | se usa cuando la transferencia online tardaría demasiado; no es una transferencia por red como DataSync |
| **AWS DMS (Database Migration Service)** | Servicio para migrar y replicar datos de bases de datos con una interrupción mínima. | mover datos entre motores o entornos | puede mantener replicación continua durante la migración; mueve los datos, pero no convierte el esquema |
| **AWS SCT (Schema Conversion Tool)** | Herramienta para convertir esquemas, código de base de datos y ciertos objetos cuando se cambia de motor. | Oracle a Aurora, SQL Server a PostgreSQL, etc. | se usa antes o junto con DMS cuando hay heterogeneidad de motores; convierte estructura, no datos |

#### Detalle útil de AWS Snow Family

| Servicio | Cuándo merece recordarlo | Idea rápida |
| --- | --- | --- |
| **AWS Snowcone** | cuando se necesita un dispositivo físico pequeño y portátil para ubicaciones con espacio o conectividad limitados | opción compacta de la familia Snow |
| **AWS Snowball Edge** | cuando se deben mover grandes volúmenes de datos y puede ser útil cierto procesamiento local | dispositivo físico de uso general dentro de Snow Family |
| **AWS Snowmobile** | cuando el volumen es extremadamente grande y la transferencia por red no es realista | opción para volúmenes masivos de datos |

### Economía de la nube

| Concepto | Qué es | Cómo suele caer | Importante |
| --- | --- | --- | --- |
| **CapEx** | inversión inicial en activos | compra de hardware, edificio, equipamiento | es poco flexible: si tu negocio baja, el servidor sigue costando el mismo dinero |
| **OpEx** | gasto variable por uso | pago por uso, mayor flexibilidad financiera | no implica automáticamente menor costo total |
| **TCO (Total Cost of Ownership)** | costo total de propiedad | energía, espacio, refrigeración, personal, mantenimiento | no es solo precio del servidor |
| **BYOL (Bring Your Own License)** | reutilizar licencias propias | necesidades de licenciamiento ya existentes | suele asociarse a Dedicated Hosts |
| **License Included** | la licencia va integrada en el precio del servicio o instancia | simplicidad de operación | AWS se encarga de todo |
| **Right-Sizing** | ajustar recursos al uso real | reducir sobredimensionamiento | no es auto scaling |
| **Automatización** | sustituir tareas manuales repetitivas por procesos consistentes | menos errores, más velocidad, más repetibilidad | no es solo ahorro; también mejora control |
| **Economías de escala** | ventaja de AWS por operar a gran volumen | reducción de precios y eficiencias operativas | no es un modelo de compra |

---

## Dominio 2. Seguridad y cumplimiento

### Modelo de responsabilidad compartida

<img width="1818" height="784" alt="image" src="https://github.com/user-attachments/assets/d92afcb5-e11c-4d42-bad9-5c77a4e1354a" />

AWS protege la infraestructura de la nube; el cliente protege aquello que despliega, configura y consume en la nube. Cuanto más gestionado es el servicio, más responsabilidades operativas asume AWS.

Se suele olvidar que, incluso en servicios gestionados, el cliente sigue siendo responsable de datos, permisos y configuración.

**AWS (Responsabilidad DE la nube):** AWS protege la infraestructura global:

* Hardware (servidores, discos).
* Seguridad física de los Centros de Datos (guardias, cámaras).
* Software de virtualización (Hipervisor).
* Regiones, Zonas de Disponibilidad y Edge Locations.

**Cliente (Responsabilidad EN la nube):** El cliente es el dueño de lo que pone dentro:

* Datos del cliente: Cifrado y copias de seguridad.
* Gestión de identidades (IAM): Quién entra y quién no.
* Configuración de red: Grupos de seguridad (firewalls) y ACLs.
* Sistemas Operativos: Parchear Windows/Linux (en EC2).

| Servicio | AWS gestiona | El cliente gestiona |
| --- | --- | --- |
| **Amazon EC2** | hardware, red física, hipervisor | sistema operativo, parches, aplicaciones, datos, seguridad de red de instancia |
| **Amazon RDS** | motor y sistema operativo subyacente, parches del servicio, infraestructura | datos, cuentas de base de datos, esquemas, configuración funcional, acceso |
| **AWS Lambda** | infraestructura, sistema operativo y runtime administrado | código, dependencias, permisos, datos |
| **Amazon S3 / DynamoDB** | servicio administrado por completo | clasificación de datos, cifrado elegido, políticas, accesos, retención |

> **Nota de examen:** En servicios como **S3** o **DynamoDB**, la responsabilidad del cliente se centra sobre todo en los datos, el acceso, la clasificación y las políticas de protección. AWS se encarga de la infraestructura subyacente del servicio.

### IAM: Identity and Access Management

IAM es gratuito y es un servicio **Global** (no se configura por región). Se rige por el **Principio de Mínimo Privilegio**: dar solo los permisos necesarios para realizar una tarea y nada más.

#### Pilares de IAM

1. **Usuarios:** Identidades persistentes para personas o aplicaciones. (Ej: "Juan" o "App_Ventas").
2. **Grupos:** Colecciones de usuarios. Es mejor dar permiso a un grupo "Administradores" que a cada usuario por separado.
3. **Roles:** Identidades **temporales**. No tienen contraseña ni llaves fijas. Se usan para que un servicio (como EC2) hable con otro (como S3) de forma segura.
4. **Políticas:** Documentos en formato **JSON** que definen qué se puede hacer.
   
    * *Efecto:* Allow (Permitir) o Deny (Denegar).
    * *Acción:* Qué quieres hacer (ej: `s3:ListBucket`).
    * *Recurso:* Sobre qué (ej: un cubo específico).

| Elemento | Qué es | Cómo recordarlo | Cómo suele caer |
| --- | --- | --- | --- |
| **Root user** | identidad inicial de la cuenta con privilegio total | solo para tareas excepcionales de cuenta | MFA obligatorio, no uso diario, tareas exclusivas de cuenta (tareas de facturación o cerrar la cuenta) |
| **IAM user** | identidad persistente dentro de una cuenta | persona o aplicación concreta | acceso a consola o acceso programático |
| **IAM group** | conjunto de usuarios con permisos comunes | simplifica la asignación de permisos | "mismos permisos para varios usuarios" |
| **IAM role** | identidad temporal asumible por usuarios, servicios o cuentas | permisos temporales sin credenciales fijas | acceso entre cuentas, EC2 a S3, Lambda a DynamoDB |
| **MFA** | segundo factor de autenticación | imprescindible para root y recomendable para usuarios | protección de acceso |
| **Access keys** | credenciales para acceso programático | se usan con SDK, CLI y API | claves para automatización o aplicaciones |
| **IAM Identity Center** | acceso centralizado y SSO (Single Sign-On, un solo usuario) para varias cuentas y aplicaciones | identidad central corporativa en AWS | múltiples cuentas, acceso federado, portal único |
| **Federación** | autenticación mediante proveedor externo | la identidad vive fuera de AWS | Active Directory, IdP corporativo, SSO |
| **Amazon Cognito** | autenticación y gestión de identidades para aplicaciones | identidad de usuario final de una app | apps web o móviles con registro y login |
| **AWS Directory Service** | integración con directorios como Microsoft Active Directory | directorio corporativo administrado o integrado | Windows, autenticación corporativa, AD |
| **AWS RAM** | compartir recursos entre cuentas | compartir sin duplicar | compartir subredes u otros recursos compatibles |
| **AWS Secrets Manager** | almacenamiento y rotación de contraseñas (bases de datos, llaves de API y secretos) | contraseñas y tokens con rotación automática | credenciales sensibles, sobre todo de bases de datos |
| **AWS Systems Manager Parameter Store** | almacenamiento de configuración y secretos con integración operativa | parámetros y configuración centralizada | configuración de aplicaciones y secretos sencillos |

#### Capacidades de acceso que conviene reconocer

| Capacidad | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **AWS Security Token Service (STS)** | Emite credenciales temporales para usuarios federados, sesiones y roles asumidos. | "credenciales temporales", "assume role", "acceso temporal" | Se usa junto con roles y federación. No sustituye a IAM; ayuda a conceder acceso temporal sin credenciales permanentes. |
| **IAM Access Analyzer** | Analiza políticas y accesos para identificar recursos compartidos fuera de la zona de confianza y apoyar la revisión de permisos. | "acceso externo no deseado", "revisión de políticas", "validar acceso compartido" | Complementa IAM y el principio de mínimo privilegio. No registra actividad como CloudTrail ni detecta amenazas como GuardDuty. |

### Cifrado, cumplimiento y auditoría

| Servicio o concepto | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Cifrado en reposo** | Protege datos almacenados en discos, objetos, snapshots o bases de datos para que no queden legibles si alguien accede al soporte físico o lógico. | "proteger datos almacenados", "S3 cifrado", "EBS/RDS cifrados" | Se aplica a datos guardados. No protege el tráfico mientras viaja por la red. |
| **Cifrado en tránsito** | Protege los datos mientras se mueven entre cliente y servicio, o entre servicios, normalmente mediante protocolos como **TLS/SSL**. | "HTTPS", "conexión segura", "datos en tránsito" | Se relaciona con certificados y sesiones seguras. No sustituye al cifrado en reposo. |
| **AWS KMS** | Servicio administrado para **crear, controlar y usar llaves criptográficas** con las que otros servicios de AWS cifran y firman datos. | "llaves para cifrar S3, EBS, RDS", "gestión centralizada de llaves", "control de acceso a llaves" | Es la opción habitual cuando se pide cifrado integrado con servicios de AWS. No sirve para guardar contraseñas de aplicaciones. |
| **AWS CloudHSM** | Servicio basado en **hardware security modules** dedicados que ofrece control más directo sobre llaves y operaciones criptográficas. | "requisitos criptográficos estrictos", "más control sobre HSM", "single-tenant" | Ofrece más control y más responsabilidad operativa que KMS. Si la pregunta destaca control criptográfico muy estricto, suele acercarse a CloudHSM. |
| **AWS Certificate Manager (ACM)** | Aprovisiona, gestiona e integra certificados **TLS/SSL** para proteger dominios, sitios web y aplicaciones. | "certificados HTTPS", "gestión y renovación de certificados" | Se usa para identidad y cifrado en tránsito. No gestiona cifrado en reposo ni llaves de aplicación como KMS. |
| **AWS CloudTrail** | Registra la actividad de la cuenta y las llamadas a la API realizadas desde consola, CLI, SDK u otros servicios. | "quién hizo qué", "auditoría", "actividad de cuenta" | Es el servicio clave para saber **qué acción se hizo, cuándo y sobre qué recurso**. No está pensado para métricas ni para salud del sistema. |
| **Amazon CloudWatch** | Servicio de observabilidad y monitorización que trabaja con **métricas, logs, alarmas, paneles y eventos** para conocer el estado operativo de aplicaciones y recursos. | "CPU alta", "alarmas", "logs", "monitorización", "salud operativa" | Es la respuesta cuando la pregunta busca visibilidad operativa. No responde a "quién cambió esto", porque eso es CloudTrail o Config según el caso. |
| **AWS Config** | Mantiene inventario, historial y evaluación del estado de configuración de los recursos de AWS a lo largo del tiempo. | "cómo cambió la configuración", "cumplimiento técnico", "estado pasado del recurso" | Sirve para saber **qué cambió** en un recurso y si cumple ciertas reglas. No es un registro de llamadas a la API como CloudTrail. |
| **AWS Artifact** | Portal de autoservicio para descargar documentación, informes y acuerdos de cumplimiento de **AWS**. | "ISO", "SOC", "PCI", "descargar informes de AWS", "documentación de cumplimiento" | Aquí se descargan los documentos de cumplimiento **de AWS**. No genera evidencias propias del cliente. |
| **AWS Audit Manager** | Automatiza la recopilación de evidencias para auditorías y ayuda a evaluar controles frente a marcos regulatorios o internos. | "recopilar evidencias", "preparar auditoría", "evaluar controles" | Es la respuesta cuando la empresa necesita demostrar su propio cumplimiento con evidencias de su entorno. No sustituye al criterio de auditoría ni al asesor legal. |
| **Informes de acceso de IAM / último acceso** | Informes que muestran cuándo un usuario, grupo, rol o política intentó acceder por última vez a servicios o acciones de AWS. | "último acceso", "qué permisos se usan realmente", "revisar permisos sobrantes" | Se usan para refinar permisos y revisar uso real de accesos. No sustituyen a CloudTrail, porque no son un historial completo de eventos. |

> En **AWS Artifact** se descargan informes y acuerdos emitidos por **AWS**. En **AWS Audit Manager** se recopilan evidencias del **entorno del cliente** para preparar auditorías o revisiones de cumplimiento.

**Qué conviene recordar de CloudWatch**

* **Alarmas (Alarms):** evalúan una métrica frente a un umbral y pueden notificar o activar automatizaciones.
* **Eventos y automatización (Events):** CloudWatch puede trabajar con **Amazon EventBridge** para reaccionar automáticamente a cambios de estado o eventos del sistema disparando acciones de forma automática.

### Servicios de seguridad

| Servicio | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon GuardDuty** | Servicio de detección de amenazas que analiza fuentes como logs y actividad de la cuenta para identificar comportamiento inesperado, potencialmente no autorizado o malicioso. | "actividad sospechosa", "minería de criptomonedas", "uso anómalo de la cuenta", "IP o dominios maliciosos" | Detecta amenazas y genera hallazgos. No escanea vulnerabilidades del software como Inspector. |
| **Amazon Inspector** | Servicio de gestión de vulnerabilidades que descubre cargas y las analiza continuamente para detectar **vulnerabilidades de software** y **exposición de red no deseada**. | "vulnerabilidades", "fallos de software", "contenedores o EC2 expuestos" | Se centra en la postura de vulnerabilidad de las cargas. No investiga comportamiento sospechoso de la cuenta. |
| **AWS Security Hub** | Consolida y organiza hallazgos de seguridad y postura de seguridad desde varios servicios y cuentas en un punto central. | "panel central", "vista unificada", "priorizar hallazgos" | No detecta por sí solo el problema original como GuardDuty o Inspector; centraliza y ayuda a priorizar. |
| **Amazon Macie** | Servicio de seguridad de datos que descubre y clasifica datos sensibles en **Amazon S3**, además de señalar riesgos de seguridad o privacidad relacionados con esos datos. | "PII en S3", "datos sensibles", "privacidad de datos" | Está centrado en **datos sensibles en S3**. No sirve para detectar DDoS, vulnerabilidades ni actividad sospechosa general. |
| **AWS Shield** | Protección administrada frente a ataques **DDoS**. | "DDoS", "saturación por volumen", "ataques de red o transporte" | **Shield Standard** está incluido para todos los clientes; **Shield Advanced** añade protección avanzada y capacidades adicionales. |
| **AWS WAF (Web Application Firewall)** | Firewall de aplicaciones web que inspecciona solicitudes **HTTP/HTTPS** y permite permitir, bloquear o contar tráfico según reglas. | "SQL injection", "XSS", "filtrado por IP", "reglas de capa 7" | Protege a nivel de aplicación web. No es la respuesta principal para DDoS volumétrico, donde suele aparecer Shield. |
| **AWS Firewall Manager** | Servicio para configurar y administrar de forma centralizada protecciones como WAF, Shield Advanced y controles de red en múltiples cuentas y recursos. | "muchas cuentas", "aplicar reglas a escala", "gestión centralizada" | La idea clave es **gobernanza central** de protecciones, no análisis del hallazgo en sí. |
| **Amazon Detective** | Ayuda a analizar, investigar y encontrar la causa raíz de hallazgos o actividades sospechosas utilizando datos agregados, análisis y visualizaciones. | "investigar un hallazgo", "análisis posterior", "causa raíz" | Suele entrar después de que otro servicio ya detectó el problema. |
| **AWS Trusted Advisor** | Revisa el entorno y ofrece recomendaciones sobre buenas prácticas de costo, seguridad, rendimiento, tolerancia a fallos y límites de servicio. | "recomendaciones", "mejores prácticas", "optimización general" | No es un servicio de detección de amenazas. Su función es orientar y señalar oportunidades o riesgos generales. |

#### Cómo no confundir los servicios de protección de recursos

| Si el problema está en... | El servicio más probable es... | Por qué |
| --- | --- | --- |
| **El software o la exposición de la carga** | **Amazon Inspector** | Busca vulnerabilidades y exposición no deseada en cargas como EC2 o contenedores compatibles. |
| **El comportamiento de la cuenta o la actividad sospechosa** | **Amazon GuardDuty** | Detecta amenazas y comportamientos anómalos en la cuenta y en las fuentes que analiza. |
| **Los datos sensibles almacenados en S3** | **Amazon Macie** | Descubre y clasifica información sensible o PII en buckets de Amazon S3. |
| **El tráfico masivo de tipo DDoS** | **AWS Shield** | Protege frente a ataques de denegación de servicio distribuido. |
| **Las peticiones web maliciosas a nivel HTTP/HTTPS** | **AWS WAF** | Filtra solicitudes de capa 7, como SQL injection o XSS. |
| **La necesidad de ver hallazgos en un panel central** | **AWS Security Hub** | Consolida y organiza hallazgos de varios servicios de seguridad. |
| **La necesidad de aplicar políticas de protección a escala en muchas cuentas** | **AWS Firewall Manager** | Administra protecciones de forma centralizada en varios recursos y cuentas. |
| **La investigación de un hallazgo ya detectado** | **Amazon Detective** | Ayuda a analizar y encontrar la causa raíz una vez existe un hallazgo. |

### Información de seguridad y cumplimiento

| Recurso | Para qué se usa |
| --- | --- |
| **AWS Artifact** | descargar documentación formal, informes de cumplimiento y acuerdos de AWS |
| **AWS Knowledge Center** | consultar artículos técnicos oficiales para dudas frecuentes y resolución de problemas |
| **AWS Security Center / recursos de seguridad de AWS** | localizar documentación, referencias y material oficial relacionado con seguridad en AWS |
| **AWS Security Blog** | revisar novedades, guías, patrones y prácticas recomendadas de seguridad |
| **AWS re:Post** | consultar preguntas y respuestas técnicas sobre casos concretos y problemas reales |
| **AWS Marketplace** | localizar productos de terceros, incluidos productos de seguridad, disponibles para ejecutarse o integrarse en AWS |

### Resumen

| Si la pregunta menciona... | El servicio o concepto es... | Diferenciador clave |
| --- | --- | --- |
| **¿Quién hizo qué?** (consola, CLI, SDK, API) | **AWS CloudTrail** | Registra actividad y eventos de cuenta para auditoría. |
| **Métricas**, **logs**, **alarmas**, paneles o salud operativa | **Amazon CloudWatch** | Sirve para observar y alertar sobre el estado del sistema. |
| **¿Cómo cambió esto?** o si el recurso cumple una configuración esperada | **AWS Config** | Mantiene historial de configuración y evalúa cumplimiento técnico. |
| **Datos almacenados** protegidos | **Cifrado en reposo** | Se refiere a proteger datos guardados. |
| **Conexión segura**, **HTTPS**, **TLS/SSL** | **Cifrado en tránsito** / **ACM** | Se refiere a proteger el tráfico mientras viaja. |
| **Llaves** para cifrar datos en servicios de AWS | **AWS KMS** | Gestiona llaves criptográficas integradas con muchos servicios de AWS. |
| **Control criptográfico muy estricto** o HSM dedicado | **AWS CloudHSM** | Más control y más responsabilidad operativa que KMS. |
| **Certificados SSL/TLS** | **AWS Certificate Manager (ACM)** | Gestiona certificados, no secretos ni llaves de aplicación. |
| **Informes de AWS** (ISO, SOC, PCI) o acuerdos de AWS | **AWS Artifact** | Descargas documentación emitida por AWS. |
| **Evidencias propias** para auditorías o controles | **AWS Audit Manager** | Automatiza la recopilación de evidencias del entorno del cliente. |
| **Último acceso** o revisión de permisos usados realmente | **Informes de acceso de IAM** | Ayudan a refinar permisos, no sustituyen a CloudTrail. |
| **Actividad maliciosa**, uso anómalo, minería de criptomonedas | **Amazon GuardDuty** | Detecta amenazas y comportamiento sospechoso. |
| **Vulnerabilidades** y exposición de cargas | **Amazon Inspector** | Detecta fallos de software y exposición de red. |
| **Datos personales o sensibles en S3** | **Amazon Macie** | Descubre y clasifica datos sensibles en buckets S3. |
| **Ataques web** (SQLi, XSS, IPs malas) | **AWS WAF** | Protege a nivel de aplicación web, capa 7. |
| **Ataque DDoS** | **AWS Shield** | Protección específica frente a DDoS; Standard y Advanced. |
| **Panel central de hallazgos** | **AWS Security Hub** | Consolida y prioriza hallazgos de varios servicios. |
| Gestión de reglas en **muchas cuentas** | **AWS Firewall Manager** | Aplica políticas de protección de forma centralizada. |
| **Investigar** un hallazgo o encontrar la causa raíz | **Amazon Detective** | Sirve para análisis e investigación posterior. |
| **Parchear**, ejecutar comandos o administrar muchos nodos | **AWS Systems Manager (SSM)** | Gestión operativa centralizada a escala. |
| **Rotación** de contraseñas o secretos de aplicaciones | **AWS Secrets Manager** | Guarda y rota secretos durante su ciclo de vida. |
| Recomendaciones generales de **seguridad**, **coste** o **límites** | **AWS Trusted Advisor** | Detecta oportunidades de mejora y riesgos generales. |

---

## Dominio 3. Tecnología y servicios en la nube

### Métodos de acceso y funcionamiento

En este apartado debemos distinguir **cuándo conviene una acción manual**, **cuándo se necesita acceso programático** y **cuándo la infraestructura debe definirse de forma repetible**.

[Interacting with AWS Services: Console, CLI, and SDK](https://medium.com/@savinduamalka/interacting-with-aws-services-console-cli-and-sdk-db371a768b4d)

| Opción | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **AWS Management Console** | Interfaz web para crear, modificar y revisar recursos manualmente desde el navegador. | "hacer una tarea puntual", "gestión manual", "administración visual" | Es adecuada para operaciones únicas o para explorar servicios. No es la mejor respuesta si se busca repetibilidad o estandarización. |
| **API / SDK (Software Development Kit)** | Acceso programático a AWS desde una aplicación mediante llamadas a la API y bibliotecas cliente. | "acceso programático", "integración desde código", "la aplicación debe interactuar con AWS" | El SDK es la forma habitual de usar la API desde código. No debe confundirse con la CLI, que es una herramienta de terminal. |
| **AWS CLI** | Herramienta de línea de comandos para interactuar con los servicios de AWS. | "automatizar con scripts", "ejecutar comandos", "operación técnica desde terminal" | Es útil para automatización operativa ligera. |
| **Infrastructure as Code (IaC)** | Forma de definir infraestructura mediante plantillas o código para desplegarla siempre de forma consistente. | "entorno repetible", "versionable", "auditable", "mismo despliegue en varios entornos" | Si el examen destaca repetibilidad y control de cambios, suele apuntar a **AWS CloudFormation**. |

#### Regla de examen

* Si la necesidad es **una operación puntual**, la consola puede ser válida.
* Si la necesidad es **repetible, auditable o masiva**, conviene pensar en **CLI**, **SDK/API** o **IaC** según el caso.
* Si la necesidad es **consistencia de despliegue**, la respuesta suele acercarse a **AWS CloudFormation**.

**Nota práctica: AWS CloudShell**

AWS CloudShell ofrece una shell basada en navegador, ya autenticada desde la consola, con la `AWS CLI` y herramientas comunes preinstaladas. Resulta útil para practicar, ejecutar comandos puntuales o trabajar desde un equipo donde no se quiere instalar la CLI localmente. Es un recurso práctico de operación y aprendizaje, no un sustituto de IaC.

### Modelos de despliegue

| Modelo | Qué significa realmente | Aspectos relevantes |
| --- | --- | --- |
| **Cloud** | La carga de trabajo se ejecuta íntegramente en la nube de AWS. | No implica necesariamente serverless; solo describe dónde se ejecuta la carga. |
| **On-premises** | La carga sigue desplegada en la infraestructura propia de la organización.  | No debe confundirse con Outposts, que sigue siendo infraestructura y experiencia AWS. |
| **Hybrid** | Parte de la solución se ejecuta en AWS y otra parte permanece en las instalaciones o en otro entorno conectado. | Híbrido no significa multi-cloud. La idea clave es mezclar AWS con entorno local. |
| **AWS Outposts** | Infraestructura de AWS desplegada físicamente en las instalaciones del cliente para operar con experiencia AWS en las propias instalaciones. | Se elige cuando se necesita usar servicios y herramientas de AWS, pero con infraestructura ubicada en el centro del cliente. |

### Infraestructura global de AWS

La infraestructura se divide en tres niveles jerárquicos:

* **Regiones (Regions):** Ubicaciones físicas en el mundo que contienen múltiples AZ. 
    * **Criterios de elección:** 
        - **Cumplimiento legal** (cumplir con leyes de datos locales, ej. datos que no pueden salir de España)
        - **Proximidad/Latencia** (estar cerca del usuario)
        - **Coste** (unas regiones son más baratas que otras).
* **Zonas de Disponibilidad (Availability Zones - AZ):** Uno o más centros de datos discretos con energía y conectividad redundantes dentro de una Región. 
    * **Clave:** Se usan para **Alta Disponibilidad**. Si una AZ falla, la carga puede seguir operativa en otra dentro de la misma región. Esto es **tolerancia a fallos**.
* **Puntos de Presencia (Edge Locations):** Centros de datos pequeños repartidos por todo el mundo en cientos de ciudades para el servicio **Amazon CloudFront**.
    * **Clave:** No sirven para "lanzar servidores", sirven para **caché** de contenido (vídeos, imágenes) cerca del usuario final para reducir la latencia.

| Elemento | Qué es | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Region** | Ubicación geográfica independiente donde AWS ofrece una colección de servicios y varias zonas de disponibilidad. | latencia, coste, cumplimiento, residencia de datos, recuperación ante desastres | La elección de región suele responder a criterios de negocio, normativa, proximidad al usuario y disponibilidad de servicios. |
| **Availability Zone (AZ)** | Conjunto de uno o más centros de datos físicamente separados dentro de una región. | alta disponibilidad, tolerancia a fallos, despliegue multi-AZ | Si la pregunta habla de resistencia a fallos dentro de la misma región, suele apuntar a múltiples AZ. |
| **Edge Location** | Punto de presencia cercano al usuario final para entregar contenido o acelerar el acceso global. | CloudFront, baja latencia global, entrega de contenido | No se usa para lanzar EC2. Se asocia a entrega de contenido y presencia cercana al usuario. |

#### Cuándo pensar en varias regiones

| Necesidad | Qué se busca realmente | Idea de examen |
| --- | --- | --- |
| **Recuperación ante desastres y continuidad de negocio** | resistir la caída de una región completa | si el fallo que se quiere cubrir es regional, multi-AZ no basta |
| **Baja latencia para usuarios de distintas zonas geográficas** | acercar la carga a usuarios finales en varios mercados | se eligen regiones cercanas al usuario o se combina con servicios globales |
| **Soberanía o residencia de datos** | mantener datos en una jurisdicción concreta | la región se elige por requisitos legales o regulatorios |
| **Separación geográfica del riesgo** | no depender de una sola región para cargas críticas | multi-región responde a un problema distinto de alta disponibilidad dentro de una región |

### Servicios de cómputo

| Servicio o concepto | Qué hace realmente |Aspectos relevantes |
| --- | --- | --- |
| **Amazon EC2** | Proporciona capacidad de cómputo bajo demanda mediante máquinas virtuales configurables. | Es la respuesta cuando se necesita control más granular sobre el entorno. |
| **AWS Auto Scaling** | Ajusta automáticamente la capacidad para responder a cambios en la demanda. | Su misión es adaptar capacidad. No reparte tráfico como ELB. |
| **Elastic Load Balancing** | Distribuye el tráfico entrante entre múltiples destinos para mejorar disponibilidad y escalado horizontal. | Balancea tráfico, pero no añade capacidad por sí solo. |
| **AWS Lambda** | Ejecuta código sin aprovisionar ni administrar servidores. | Se paga por uso y escala automáticamente. No es la opción si se necesita control continuo del sistema operativo. Se asocia a un modelo **serverless**. |
| **AWS Fargate** | Ejecuta contenedores para ECS o EKS sin administrar instancias subyacentes. | No es una función como Lambda; sigue siendo un modelo basado en contenedores. Puede recordarse como **serverless para contenedores**. |
| **Amazon ECS** | Servicio de orquestación de contenedores nativo de AWS. | Si la pregunta no exige Kubernetes, ECS suele ser candidato natural. |
| **Amazon EKS** | Servicio administrado para ejecutar Kubernetes en AWS. | La palabra disparadora suele ser **Kubernetes**. |
| **Amazon ECR** | Registro administrado para almacenar y distribuir imágenes de contenedor. | Almacena imágenes; no ejecuta contenedores. Su función principal es servir de registro para imágenes. |
| **AWS Elastic Beanstalk** | Automatiza buena parte del despliegue y operación de aplicaciones. | Simplifica la plataforma de aplicación, pero no sustituye a IaC completa. |
| **Amazon Lightsail** | Servicio simplificado para sitios web, VPS y cargas pequeñas o previsibles. | Más simple que EC2, pero menos flexible para arquitecturas complejas. |
| **AWS Batch** | Orquesta y ejecuta trabajos por lotes a escala. | No es balanceo ni ejecución interactiva de aplicaciones web. |
| **AWS Outposts** | Extiende servicios de cómputo y otros servicios de AWS a las instalaciones del cliente. | Aparece cuando se necesita experiencia AWS con infraestructura física en las instalaciones de la organización. |

#### Familias EC2 que conviene reconocer

| Familia | Uso habitual | Clave de examen |
| --- | --- | --- |
| **General Purpose** | equilibrio entre CPU y memoria | aplicaciones estándar y cargas generales |
| **Compute Optimized** | procesamiento intensivo | cómputo alto, cálculo intensivo |
| **Memory Optimized** | grandes volúmenes en memoria | bases de datos en memoria, cachés, analítica en memoria |
| **Storage Optimized** | acceso intensivo a almacenamiento | IOPS alto, throughput elevado, datos locales rápidos |
| **Accelerated Computing** | GPU, inferencia o gráficos | ML especializado, gráficos, aceleración hardware |

#### AMI y EBS Snapshots

| Concepto | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon Machine Image (AMI)** | Plantilla que contiene el sistema operativo, la configuración base y, según el caso, software necesario para lanzar instancias EC2 consistentes. | "crear varias instancias iguales", "imagen base", "clonar configuración" | Se usa para lanzar instancias con la misma configuración y es específica de una región. No es una instancia ejecutándose. |
| **EBS Snapshot** | Copia point-in-time de un volumen EBS que sirve para respaldo, recuperación o creación de nuevos volúmenes. | "backup de un disco EC2", "restaurar volumen", "copia de volumen" | El primer snapshot es completo y los siguientes son incrementales. Un snapshot no es una AMI completa, aunque una AMI basada en EBS puede usar snapshots. |

#### Balanceadores de carga

| Tipo | Qué hace realmente | Cuándo pensar en él |
| --- | --- | --- |
| **ALB (Application Load Balancer)** | Balancea tráfico HTTP/HTTPS en capa 7 y permite reglas por ruta o por host. | aplicaciones web, microservicios, routing inteligente |
| **NLB (Network Load Balancer)** | Balancea tráfico TCP/UDP en capa 4 con alto rendimiento y baja latencia. | tráfico de red de alto rendimiento, IP estática, cargas muy exigentes |

### Servicios de bases de datos

| Servicio o concepto | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Base de datos en EC2** | La organización instala y administra la base de datos sobre una instancia EC2. | "control total", "software específico", "gestionar el sistema operativo y la base de datos" | El cliente se encarga de parches, backups, alta disponibilidad y operación. |
| **Amazon RDS** | Servicio administrado para bases de datos relacionales que simplifica aprovisionamiento, operación, backups y escalado. | "menos administración", "relacional", "backups automáticos", "parches gestionados" | La idea clave es **relacional administrada**. |
| **Amazon Aurora** | Base de datos relacional administrada y optimizada para AWS, compatible con MySQL o PostgreSQL. | "alto rendimiento relacional", "compatible con MySQL/PostgreSQL", "Aurora" | Suele aparecer cuando el examen quiere relacional administrada con foco en rendimiento y disponibilidad. |
| **Amazon DynamoDB** | Base de datos NoSQL administrada y serverless para modelos key-value y documento. | "NoSQL", "alta escala", "baja latencia", "serverless" | No es relacional y no requiere administrar servidores. |
| **Amazon ElastiCache** | Servicio de caché en memoria administrado para acelerar aplicaciones y descargar la base de datos principal. | "caché", "reducir latencia", "mejorar rendimiento de lectura" | Complementa una base de datos; no la sustituye como sistema principal de registro. |
| **Amazon DocumentDB** | Base documental administrada compatible con cargas tipo MongoDB. | "documentos JSON", "compatibilidad tipo MongoDB" | No debe confundirse con DynamoDB: ambos son NoSQL, pero resuelven patrones distintos. |
| **Amazon Neptune** | Base de datos de grafos administrada para modelar relaciones complejas entre entidades. | "grafos", "relaciones complejas", "redes, fraude, recomendaciones" | Si la clave es relación entre nodos, pensar en Neptune. |
| **AWS DMS** | Mueve y replica datos entre bases de datos con una interrupción mínima. | "mínima parada", "migración de datos", "replicación continua" | Mueve datos, pero no convierte el esquema cuando cambia el motor. |
| **AWS SCT** | Convierte esquemas y cierto código de base de datos al migrar entre motores diferentes. | "cambio de motor", "Oracle a Aurora", "SQL Server a PostgreSQL" | Convierte estructura, no datos. Suele acompañar a DMS. |

#### Regla de examen: base de datos en EC2 o administrada

* Si la pregunta pide **menos administración**, **parches automáticos**, **backups gestionados** o **alta disponibilidad simplificada**, la respuesta suele ser **RDS o Aurora**.
* Si la pregunta pide **control total del sistema operativo o del motor instalado**, la respuesta puede ser **base de datos en EC2**.

#### Multi-AZ frente a Read Replica

[VPN de software](https://docs.aws.amazon.com/es_es/whitepapers/latest/aws-vpc-connectivity-options/software-vpn-1.html)

[Automating AWS Transit Gateway](https://aws.amazon.com/es/blogs/networking-and-content-delivery/automating-aws-transit-gateway-attachments-to-a-transit-gateway-in-a-central-account/)


| Opción | Qué resuelve principalmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Multi-AZ (RDS DB instance deployment)** | Alta disponibilidad y failover ante la caída de la instancia primaria o de una AZ. | "continuidad", "producción crítica", "failover automático" | En el enfoque clásico de examen, el standby existe para disponibilidad y no para descargar lecturas. |
| **Read Replica** | Escalado de lectura y descarga de consultas sobre la base principal. | "muchas lecturas", "reporting", "analítica sobre datos operativos" | No es la respuesta principal cuando el requisito central es alta disponibilidad. Si el enunciado pide más capacidad de lectura, suele apuntar a read replicas. |

> **Nota de precisión:** AWS ofrece modalidades Multi-AZ más avanzadas, pero en `CLF-C02` la distinción que más ayuda a responder bien suele ser **alta disponibilidad/failover** frente a **escalado de lectura**.

### Servicios de red y conectividad

#### Componentes de VPC

<img width="611" height="481" alt="image" src="https://github.com/user-attachments/assets/d4594105-f492-49e4-93ca-6ff8e29457fb" />

Fuente: https://docs.aws.amazon.com/vpc/latest/userguide/create-a-vpc-with-private-subnets-and-nat-gateways-using-aws-cli.html 

| Componente | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon VPC** | Red virtual aislada lógicamente en la que se despliegan recursos de AWS. | "aislamiento de red", "diseño de red", "entorno privado" | Es el contenedor lógico de red, no una subred concreta. |
| **Subnet** | Segmento de red dentro de una VPC asociado a una zona de disponibilidad. | "subred pública o privada", "segmentación de recursos" | Lo importante es la ruta y la exposición del tráfico, no solo el nombre pública o privada. |
| **Internet Gateway (IGW)** | Permite comunicación entre la VPC e internet para recursos públicos. | "salida directa a internet", "recursos públicos" | Si el recurso debe ser accesible desde internet, suele intervenir un IGW. |
| **NAT Gateway** | Permite que recursos en subredes privadas salgan a internet sin aceptar conexiones entrantes iniciadas desde internet. | "instancias privadas que descargan actualizaciones", "salida desde subred privada" | La idea clave es **salida**, no entrada pública. |
| **Virtual Private Gateway (VGW)** | Punto de terminación del lado de AWS para conexiones VPN hacia una VPC. | "Site-to-Site VPN", "conectar una VPC con on-premises" | Se asocia a VPN. No es el hub para muchas VPC y muchas redes. |
| **AWS Transit Gateway** | Hub central para conectar múltiples VPC y redes on-premises. | "muchas VPC", "conectividad centralizada", "hub-and-spoke" | Si hay muchas redes que conectar, pensar en Transit Gateway. |
| **Route Table** | Define hacia dónde se dirige el tráfico de la subred o del gateway. | "rutas a IGW, NAT, VGW o TGW" | Decide caminos; no filtra tráfico como SG o NACL. |
| **Security Group** | Firewall stateful a nivel de instancia o interfaz de red. | "seguridad del recurso", "permitir acceso a una instancia" | Si una conexión entra permitida, la respuesta de vuelta se permite automáticamente. |
| **Network ACL** | Firewall stateless a nivel de subred. | "capa adicional en la subred", "allow y deny" | Evalúa entrada y salida por separado. |
| **AWS PrivateLink** | Permite acceder a servicios de forma privada sin exponer el tráfico a internet pública. | "endpoint privado", "consumir un servicio de forma privada" | Se relaciona con acceso privado a servicios, no con VPN tradicional. |

* **Subredes (Subnets)**:
    * **Pública**: acceso directo a internet a través de **Internet Gateway (IGW)**.
    * **Privada**: sin acceso directo a internet (se necesita un NAT Gateway).

#### Seguridad en VPC

| Comparativa | Security Group | Network ACL |
| --- | --- | --- |
| **Nivel** | instancia o interfaz de red | subred |
| **Estado** | stateful | stateless |
| **Reglas** | solo allow | allow y deny |

#### Conectividad y entrega de contenido

* Falta VPC Peering

| Servicio | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **AWS VPN** | Familia de conexiones VPN cifradas entre AWS, usuarios o redes externas. | "conectividad cifrada sobre internet" | Es el concepto general; luego el examen suele concretar Site-to-Site o Client VPN. |
| **AWS Site-to-Site VPN** | Conecta una red on-premises con AWS a través de internet pública mediante túneles VPN. | "conectar datacenter", "usar internet", "implementación rápida" | Suele compararse con Direct Connect. |
| **AWS Client VPN** | Proporciona acceso remoto seguro para usuarios finales a AWS o redes conectadas. | "acceso remoto de usuarios", "VPN para empleados" | No es la conexión red a red típica de Site-to-Site. |
| **AWS Direct Connect** | Establece un enlace de red dedicado entre la red interna del cliente y AWS. | "ancho de banda predecible", "no usar internet pública", "conectividad dedicada" | Se elige cuando se busca conectividad más consistente o privada que una VPN sobre internet. |
| **Amazon Route 53** | Servicio DNS escalable y altamente disponible que dirige consultas al recurso correcto. | "DNS", "resolución de nombres", "routing" | Dice **dónde** está el recurso; no entrega contenido como CloudFront. |
| **Amazon CloudFront** | CDN que cachea y entrega contenido cerca del usuario final. | "caché global", "latencia baja", "edge locations" | Entrega contenido; no reemplaza a Route 53. |
| **AWS Global Accelerator** | Mejora disponibilidad y rendimiento global dirigiendo tráfico a los endpoints óptimos sobre la red global de AWS. | "IP estática global", "usuarios globales", "TCP/UDP" | Suele aparecer cuando se busca mejor ruta global hacia aplicaciones, no caché. |
| **Amazon API Gateway** | Servicio administrado para crear, publicar, proteger y monitorizar APIs. | "publicar API", "front door de APIs", "gestión de endpoints" | No es un balanceador genérico ni un CDN. |

* **AWS VPN**: Conexión cifrada a través de la **internet pública**.
* **AWS Direct Connect**: **línea física dedicada** (fibra óptica) desde la oficina a AWS. No pasa por internet.

| Si la pregunta dice... | La respuesta es... |
| :--- | :--- |
| "Aislar recursos lógicamente" | **VPC** |
| "Conectar el datacenter físico por internet" | **Site-to-Site VPN** |
| "Línea física privada para baja latencia" | **Direct Connect** |
| "Capa 7 / HTTP / Microservicios" | **ALB** |
| "Capa 4 / Rendimiento extremo / IP estática" | **NLB** |
| "Seguridad sin estado (Stateless) para subred" | **NACL** |
| "Salida a internet para subredes privadas" | **NAT Gateway** |

### Servicios de almacenamiento

| Servicio o concepto | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon S3** | Servicio de almacenamiento de objetos para guardar y proteger cualquier volumen de datos. | "archivos", "backups", "logs", "data lake", "contenido estático" | La palabra disparadora suele ser **objeto** o **datos no estructurados**. |
| **Clases de S3** | Niveles de almacenamiento con distintos costos y patrones de acceso. | "frecuente", "infrecuente", "archivo", "optimizar costes" | La clase correcta depende de frecuencia de acceso, latencia y coste. |
| **Lifecycle Policies** | Reglas automáticas para mover u expirar objetos según su edad o retención. | "mover a Glacier", "eliminar datos antiguos", "automatizar ciclo de vida" | Son políticas de ciclo de vida, no un servicio de backup. |
| **Amazon EBS** | Almacenamiento en bloque persistente para instancias EC2. | "disco para EC2", "volumen persistente", "block storage" | Se asocia normalmente a una instancia dentro de la misma AZ. |
| **Instance Store** | Almacenamiento efímero físicamente asociado al host de la instancia. | "datos temporales", "muy alto rendimiento local", "no persistente" | No debe elegirse para datos que deban sobrevivir a la instancia. |
| **Amazon EFS** | Sistema de archivos administrado y compartido para cargas Linux. | "compartir archivos entre varias EC2", "NFS", "file system compartido" | Si varias instancias Linux necesitan ver los mismos archivos, pensar en EFS. |
| **Amazon FSx** | Familias de sistemas de archivos administrados para casos especializados como Windows o alto rendimiento. | "Windows File Server", "Lustre", "file system especializado" | Se usa cuando el requisito apunta a un sistema de archivos específico, no a uno generalista como EFS. |
| **AWS Storage Gateway** | Integra almacenamiento on-premises con AWS usando caché local y backend en la nube. | "híbrido", "caché local", "extender almacenamiento a AWS" | No es migración física como Snow Family. |
| **AWS Backup** | Centraliza políticas, programación y retención de backups para múltiples servicios de AWS. | "backups centralizados", "políticas de backup", "retención" | Su foco es protección y gobierno de backups, no recuperación operativa completa de cargas. |
| **AWS Elastic Disaster Recovery** | Servicio orientado a recuperación ante desastres de servidores y cargas completas. | "DR", "failover", "recuperar entorno tras desastre" | No debe confundirse con backup clásico; busca recuperación operativa. |
| **Amazon S3 Glacier** | Familia de almacenamiento orientada a archivado de bajo costo y acceso menos inmediato. | "archivo a largo plazo", "retención", "recuperación lenta" | No es la mejor opción si el acceso debe ser frecuente o inmediato. |

> **S3** tiene una función nativa para alojar sitios web estáticos de forma extremadamente económica y escalable.

#### Funciones de S3 que suelen caer en examen

| Función o concepto | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Bucket policy** | Política basada en recurso que controla quién puede acceder al bucket y a los objetos que pertenecen al propietario del bucket. | "dar o denegar acceso a un bucket", "acceso entre cuentas", "control a nivel de bucket" | No es lo mismo que una política IAM adjunta a un usuario o rol. En S3, ambas pueden participar en la autorización. |
| **Versioning** | Conserva múltiples versiones de un mismo objeto para facilitar recuperación ante sobrescrituras o borrados accidentales. | "recuperar un archivo borrado", "mantener historial de versiones" | Ayuda a recuperar errores humanos. Cada versión almacenada consume almacenamiento. |
| **Replication** | Copia automáticamente objetos a otro bucket, normalmente en otra región o en la misma región según la configuración. | "replicar datos entre buckets", "DR", "cumplimiento", "latencia geográfica" | Suele requerir versioning habilitado. No sustituye por sí sola a una estrategia completa de backup o archivado. |
| **Static website hosting** | Permite servir contenido web estático directamente desde un bucket S3. | "sitio estático", "HTML/CSS/JS sin servidor web tradicional" | Es válido para contenido estático. No ejecuta lógica de backend ni aplicaciones dinámicas por sí mismo. |
| **S3 Object Lock** | Impide borrar o sobrescribir versiones durante un periodo definido o indefinidamente bajo un modelo WORM. | "retención legal", "inmutabilidad", "cumplimiento" | Se usa cuando el requisito central es evitar cambios o borrados durante un plazo de retención. No equivale simplemente a activar versioning. |

Clases de almacenamiento (según acceso)

* **Standard** → acceso frecuente
* **IA (Infrequent Access)** → acceso ocasional (más barato)
* **One Zone-IA** → más barato, menor resiliencia
* **Glacier / Deep Archive** → archivo (muy barato, acceso lento)

| Servicio            | ¿Para qué sirve?      | Cómo diferenciarlo rápido |
| ------------------- | --------------------- | ------------------------- |
| **S3**              | Archivos, backups     | Clases + lifecycle        |
| **EBS**             | Disco persistente para EC2       | 1 instancia               |
| **EFS**             | Sistema de archivos compartido Linux            | Multi-EC2                 |
| **FSx**             | Sistema de archivos especializado, por ejemplo Windows         | Windows / HPC             |
| **Storage Gateway** | On-prem + AWS         | Integración híbrida con caché local                     |

### Servicios de analítica

| Servicio | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon Athena** | Permite consultar datos en S3 con SQL sin administrar infraestructura propia. | "consultar datos en S3", "SQL sin servidores" | La clave es análisis ad hoc sobre datos ya almacenados en S3. |
| **Amazon EMR** | Plataforma administrada para ejecutar frameworks de big data como Hadoop o Spark. | "big data", "clústeres", "procesamiento distribuido" | Se elige cuando la pregunta habla de frameworks de procesamiento a gran escala. |
| **AWS Glue** | Servicio administrado de integración y preparación de datos, especialmente para procesos ETL. | "ETL", "catalogar datos", "preparar datos" | No es visualización como QuickSight ni data warehouse como Redshift. |
| **Amazon Kinesis** | Conjunto de servicios para recopilar y procesar datos en streaming en tiempo real. | "streaming", "telemetría", "eventos continuos" | La idea clave es **flujo continuo**, no cola tradicional. |
| **Amazon OpenSearch Service** | Servicio administrado para búsqueda, análisis y observabilidad. | "logs", "búsqueda", "analítica de texto", "observabilidad" | No es un data warehouse analítico relacional como Redshift. |
| **Amazon QuickSight** | Servicio de business intelligence para análisis visual, paneles e informes. | "dashboards", "visualización", "BI" | Se usa para presentar datos, no para almacenarlos como Redshift. |
| **Amazon Redshift** | Data warehouse administrado para analítica SQL a gran escala. | "data warehouse", "analítica", "consultas sobre grandes volúmenes" | Si el enfoque es BI y consultas analíticas estructuradas, suele aparecer Redshift. |

### Servicios de IA y machine learning

| Servicio | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon SageMaker AI** | Plataforma para crear, entrenar y desplegar modelos propios de machine learning. | "crear un modelo propio", "entrenar", "desplegar modelos" | Si el examen habla de construir el modelo, pensar en SageMaker AI. |
| **Amazon Rekognition** | Analiza imágenes y vídeo para detectar objetos, texto, escenas o rostros. | "analizar imágenes o vídeo" | Es un servicio de IA preentrenado. |
| **Amazon Lex** | Permite crear interfaces conversacionales con voz o texto. | "chatbot", "asistente conversacional" | Se relaciona con bots e interacción conversacional. |
| **Amazon Polly** | Convierte texto en voz natural. | "texto a voz" | No entiende intención conversacional como Lex. |
| **Amazon Transcribe** | Convierte voz en texto. | "voz a texto" | Suele aparecer en escenarios de audio y transcripción. |
| **Amazon Translate** | Traduce texto entre idiomas. | "traducción automática" | No analiza significado o sentimiento como Comprehend. |
| **Amazon Textract** | Extrae texto y datos estructurados de documentos escaneados o formularios. | "extraer datos de documentos", "OCR avanzado" | La clave es entender documentos, no solo almacenarlos. |
| **Amazon Comprehend** | Analiza lenguaje natural para detectar entidades, temas o sentimiento. | "NLP", "sentimiento", "entidades" | No traduce texto; lo interpreta. |
| **Amazon Kendra** | Servicio de búsqueda inteligente empresarial. | "búsqueda interna avanzada", "knowledge search" | Se usa cuando el foco es encontrar información empresarial. |
| **Amazon Q** | Asistente generativo para productividad y ayuda contextual en entornos empresariales. | "asistencia generativa", "productividad", "ayuda contextual" | No sustituye a servicios especializados de ML tradicional. |

#### Regla de examen

* Si la pregunta pide **construir un modelo propio**, se piensa en **Amazon SageMaker AI**.
* Si la pregunta pide **una capacidad ya resuelta**, se piensa en un servicio de IA preentrenado como **Rekognition**, **Lex**, **Polly**, **Textract** o **Translate**.

### Integración de aplicaciones

| Servicio | Qué hace realmente | Cómo suele caer en examen | Aspectos relevantes |
| --- | --- | --- | --- |
| **Amazon SQS** | Cola de mensajes que desacopla componentes y conserva mensajes hasta que se procesan. | "desacoplar", "cola", "absorber picos", "mensaje que espera" | Es pull y orientado a colas. No es notificación masiva a múltiples destinos como SNS. |
| **Amazon SNS** | Servicio pub/sub para enviar notificaciones a múltiples suscriptores o endpoints. | "notificar a muchos destinos", "push", "fan-out", "emails o SMS" | La idea clave es publicación a múltiples suscriptores, no almacenamiento en cola como SQS. |
| **Amazon EventBridge** | Bus de eventos que conecta eventos de AWS, SaaS o aplicaciones propias con acciones y destinos. | "reaccionar a eventos", "arquitectura orientada a eventos" | No coordina estados complejos como Step Functions. |
| **AWS Step Functions** | Orquesta flujos de trabajo y coordina pasos, reintentos y transiciones entre tareas. | "workflow", "pasos secuenciales", "orquestación" | Si la pregunta describe un proceso con estados y varios pasos, suele apuntar a Step Functions. |

#### Cómo no confundir SQS y SNS

| Si la necesidad es... | La respuesta suele ser... | Por qué |
| --- | --- | --- |
| **aguantar mensajes hasta que el consumidor pueda procesarlos** | **Amazon SQS** | funciona como cola y desacopla componentes para que un fallo o saturación del receptor no implique perder el mensaje |
| **avisar a varios sistemas o suscriptores al mismo tiempo** | **Amazon SNS** | publica el mismo evento a múltiples destinos en modelo push |

### Servicios adicionales in-scope

Estos servicios suelen entrar como preguntas directas de reconocimiento más que como escenarios largos. Conviene saber **qué categoría cubren** y **cuál es su función principal**.

| Categoría | Servicio | Qué hace realmente |
| --- | --- | --- |
| **Aplicaciones empresariales** | **Amazon Connect** | servicio de centro de contacto en la nube |
| **Aplicaciones empresariales** | **Amazon SES** | envío de correo electrónico transaccional o masivo |
| **Habilitación para clientes** | **AWS Support** | servicio de soporte técnico y habilitación para clientes |
| **Herramientas para desarrolladores** | **AWS CLI** | operación de AWS desde línea de comandos |
| **Herramientas para desarrolladores** | **AWS CodeBuild** | compilación y pruebas dentro de procesos CI/CD |
| **Herramientas para desarrolladores** | **AWS CodePipeline** | orquestación de etapas de integración y entrega continua |
| **Herramientas para desarrolladores** | **AWS X-Ray** | trazabilidad y análisis de aplicaciones distribuidas |
| **End User Computing** | **Amazon AppStream 2.0** | streaming de aplicaciones al usuario final |
| **End User Computing** | **Amazon WorkSpaces** | escritorios virtuales administrados |
| **End User Computing** | **Amazon WorkSpaces Secure Browser** | navegador remoto y aislado para acceso seguro |
| **Frontend web y móvil** | **AWS Amplify** | desarrollo y despliegue de aplicaciones frontend y full stack |
| **Frontend web y móvil** | **AWS AppSync** | APIs GraphQL administradas y sincronización de datos |
| **Internet de las cosas** | **AWS IoT Core** | conexión y gestión de dispositivos IoT |
| **Administración y gobernanza** | **AWS CloudFormation** | infraestructura como código |
| **Administración y gobernanza** | **AWS Organizations** | gestión multi-cuenta y facturación consolidada |
| **Administración y gobernanza** | **AWS Control Tower** | configuración inicial multi-cuenta con buenas prácticas |
| **Administración y gobernanza** | **AWS Health Dashboard** | visibilidad sobre eventos o incidencias que afectan a servicios o cuenta |
| **Administración y gobernanza** | **AWS Compute Optimizer** | recomendaciones de dimensionamiento de recursos |
| **Administración y gobernanza** | **AWS License Manager** | gestión de licencias |
| **Administración y gobernanza** | **AWS Service Catalog** | catálogo controlado de productos autorizados |
| **Administración y gobernanza** | **Service Quotas** | consulta y gestión de cuotas de servicio |
| **Administración y gobernanza** | **AWS Systems Manager** | administración operativa centralizada de instancias y nodos |
| **Administración y gobernanza** | **AWS Well-Architected Tool** | evaluación guiada de cargas frente a buenas prácticas |
| **Migración y transferencia** | **AWS Application Discovery Service** | descubrimiento del entorno actual |
| **Migración y transferencia** | **AWS Application Migration Service** | migración de servidores con enfoque rehost |
| **Migración y transferencia** | **AWS DataSync** | transferencia de datos por red hacia servicios de almacenamiento de AWS |
| **Migración y transferencia** | **AWS Database Migration Service** | migración de datos entre bases de datos |
| **Migración y transferencia** | **Migration Evaluator** | análisis económico y TCO de la migración |
| **Migración y transferencia** | **AWS Migration Hub** | seguimiento central de migraciones |
| **Migración y transferencia** | **AWS Schema Conversion Tool** | conversión de esquemas de base de datos |
| **Migración y transferencia** | **AWS Snow Family** | traslado físico de grandes volúmenes de datos |


### 12. Chuleta del Dominio 3

| Si la pregunta menciona... | El servicio o concepto es... | Diferenciador clave |
| --- | --- | --- |
| operación manual puntual | **AWS Management Console** | interfaz web para acciones manuales |
| acceso programático desde una aplicación | **API / SDK** | integración desde código |
| scripts u operación técnica desde terminal | **AWS CLI** | comandos, no plantillas |
| despliegue repetible y versionable | **IaC / AWS CloudFormation** | infraestructura declarativa y consistente |
| combinación de AWS y datacenter propio | **modelo híbrido** | no implica multi-cloud |
| AWS en las instalaciones del cliente | **AWS Outposts** | experiencia AWS on-premises |
| resiliencia dentro de una región | **múltiples AZ** | alta disponibilidad regional |
| resiliencia geográfica, DR o soberanía de datos | **múltiples regiones** | nivel superior a multi-AZ |
| control granular del servidor | **Amazon EC2** | máquina virtual administrada por el cliente |
| ejecutar código sin servidores | **AWS Lambda** | serverless por evento |
| contenedores sin administrar instancias | **AWS Fargate** | serverless para ECS/EKS |
| Kubernetes administrado | **Amazon EKS** | palabra disparadora: Kubernetes |
| contenedores en AWS sin Kubernetes | **Amazon ECS** | orquestación nativa de AWS |
| almacenar imágenes de contenedor | **Amazon ECR** | registro, no ejecución |
| elasticidad automática | **AWS Auto Scaling** | ajusta capacidad |
| repartir tráfico entre varios destinos | **Elastic Load Balancing** | distribuye tráfico, no añade capacidad |
| relacional administrada | **Amazon RDS** | backups y parches gestionados |
| relacional administrada optimizada para AWS | **Amazon Aurora** | compatible con MySQL/PostgreSQL |
| NoSQL serverless | **Amazon DynamoDB** | key-value y documento |
| caché en memoria | **Amazon ElastiCache** | acelera, no sustituye la base principal |
| grafos | **Amazon Neptune** | relaciones complejas |
| salida a internet desde subred privada | **NAT Gateway** | salida, no entrada |
| conectividad VPN de una VPC | **Virtual Private Gateway** | extremo AWS para Site-to-Site VPN |
| muchas VPC y conectividad centralizada | **AWS Transit Gateway** | hub central |
| firewall stateful a nivel de instancia | **Security Group** | recuerda la conexión |
| firewall stateless a nivel de subred | **Network ACL** | evalúa entrada y salida por separado |
| DNS | **Amazon Route 53** | resuelve nombres |
| caché y entrega global de contenido | **Amazon CloudFront** | usa edge locations |
| mejor ruta global sin centrarse en caché | **AWS Global Accelerator** | acelera tráfico de aplicaciones |
| almacenamiento de objetos | **Amazon S3** | archivos y datos no estructurados |
| disco persistente para EC2 | **Amazon EBS** | almacenamiento en bloque |
| sistema de archivos compartido Linux | **Amazon EFS** | file system compartido |
| sistema de archivos especializado | **Amazon FSx** | Windows, Lustre y otros |
| almacenamiento híbrido con caché local | **AWS Storage Gateway** | integración on-premises + AWS |
| backups centralizados | **AWS Backup** | políticas, retención y orquestación |
| recuperación ante desastre de servidores | **AWS Elastic Disaster Recovery** | DR operativo, no backup clásico |
| SQL sobre datos en S3 | **Amazon Athena** | análisis sin infraestructura propia |
| ETL y catálogo de datos | **AWS Glue** | preparar e integrar datos |
| streaming en tiempo real | **Amazon Kinesis** | flujo continuo de datos |
| dashboards y BI | **Amazon QuickSight** | visualización |
| data warehouse analítico | **Amazon Redshift** | analítica SQL a gran escala |
| construir un modelo propio de ML | **Amazon SageMaker AI** | crear, entrenar y desplegar |
| chatbot | **Amazon Lex** | interfaz conversacional |
| texto a voz | **Amazon Polly** | síntesis de voz |
| voz a texto | **Amazon Transcribe** | transcripción |
| documentos con extracción de datos | **Amazon Textract** | OCR y análisis documental |
| desacoplar con cola | **Amazon SQS** | mensajes que esperan consumo |
| notificar a múltiples suscriptores | **Amazon SNS** | pub/sub |
| reaccionar a eventos | **Amazon EventBridge** | bus de eventos |
| coordinar pasos y estados | **AWS Step Functions** | orquestación de workflow |

---

## Dominio 4. Facturación, precios y soporte

### Opciones de compra de cómputo

| Opción | Qué es | Cuándo suele encajar | Con qué se confunde |
| --- | --- | --- | --- |
| **On-Demand** | pago sin compromiso a largo plazo | cargas nuevas, impredecibles o temporales | es la opción más flexible, pero no suele ser la más barata para uso estable |
| **Reserved Instances (RI)** | compromiso para capacidad de EC2 o bases compatibles con descuento | uso estable y predecible | no son Savings Plans, aunque persiguen ahorro similar; suelen asociarse a compromisos de 1 o 3 años |
| **Savings Plans** | compromiso de gasto por uso de cómputo | flexibilidad mayor que muchas RI | ofrecen ahorro a cambio de compromiso de 1 o 3 años; no reservan un tipo exacto como algunas RI |
| **Spot Instances** | uso de capacidad sobrante con gran descuento | trabajos tolerantes a interrupción | pueden interrumpirse con aviso; no sirven para cargas que no admiten corte |
| **Dedicated Instances** | instancias en hardware dedicado para un solo cliente | aislamiento físico a nivel de hardware dedicado compartido por cuenta | no dan visibilidad de host como Dedicated Hosts |
| **Dedicated Hosts** | servidor físico dedicado al cliente | cumplimiento y BYOL con mayor control | no son On-Demand normales |
| **Capacity Reservations** | reserva de capacidad en una AZ específica | necesidad de garantizar capacidad disponible | no son descuento por compromiso |

#### Qué conviene recordar sobre RI y Organizations

* Las **Reserved Instances** y otros compromisos suelen aparecer asociadas a **uso estable**.
* En preguntas de examen, **AWS Organizations** puede influir en cómo se aprovechan beneficios y facturación de compromisos a nivel agregado.
* Si la pregunta destaca **flexibilidad de cómputo**, con frecuencia conviene pensar en **Savings Plans** antes que en RI clásicas.
* En **EC2 Spot Instances**, AWS puede interrumpir la capacidad cuando la necesita de vuelta; la referencia típica de examen es el **aviso de 2 minutos**.

### Costos de almacenamiento y transferencia

| Concepto | Qué se debe recordar |
| --- | --- |
| **Almacenamiento** | cuanto más frío o menos frecuente sea el acceso, menor suele ser el costo por GB y mayor la latencia de recuperación |
| **Transferencia de datos entrante** | suele ser más barata o incluso sin costo según el caso; lo importante es revisar el patrón específico |
| **Transferencia de datos saliente** | suele ser el concepto que más conviene vigilar |
| **Entre regiones** | puede implicar cargos; no asumir que todo tráfico interno es gratuito |

### Herramientas de facturación y costo

| Herramienta | Qué es | Cómo suele caer | Con qué se confunde |
| --- | --- | --- | --- |
| **AWS Budgets** | alertas y seguimiento contra objetivos de costo o uso | presupuesto, umbral, aviso futuro | no es análisis histórico profundo |
| **AWS Cost Explorer** | análisis visual de gasto histórico y tendencias | identificar qué servicio gastó más o cómo evolucionó el costo | no es presupuesto |
| **AWS Cost and Usage Report (CUR)** | detalle exhaustivo de costos y uso | informes detallados para análisis fino o exportación | no es la calculadora |
| **AWS Pricing Calculator** | estimación previa de costos | prever cuánto costará una arquitectura antes de desplegar | no usa datos reales de una cuenta |
| **AWS Marketplace** | compra de software de terceros y gestión de derechos asociada | licencias y soluciones de terceros en AWS | no es Artifact |

#### Cómo no confundir las herramientas de coste

| Si la necesidad es... | La respuesta suele ser... | Por qué |
| --- | --- | --- |
| **recibir alertas si el gasto real o previsto supera un límite** | **AWS Budgets** | está orientado a presupuestos, umbrales y seguimiento frente a objetivos |
| **analizar en qué se gastó el dinero y ver tendencias históricas** | **AWS Cost Explorer** | trabaja sobre datos de coste ya existentes en la cuenta |
| **estimar cuánto costará una arquitectura antes de desplegarla** | **AWS Pricing Calculator** | se usa antes de crear recursos, no sobre gasto real ya consumido |

### Etiquetas de asignación de costos

| Concepto | Qué se debe recordar |
| --- | --- |
| **AWS-generated cost allocation tags** | etiquetas generadas por AWS, por ejemplo relacionadas con cuenta o servicio |
| **User-defined cost allocation tags** | etiquetas definidas por el cliente, por ejemplo `Proyecto`, `CentroCoste`, `Entorno` |
| **Relación con CUR** | las etiquetas activadas pueden reflejarse en informes de facturación y en el Cost and Usage Report |
| **Idea de examen** | las etiquetas no reducen el costo por sí solas; ayudan a asignarlo y analizarlo |

### AWS Organizations, soporte y recursos técnicos

| Recurso o servicio | Qué es | Cómo suele caer | Con qué se confunde |
| --- | --- | --- | --- |
| **AWS Organizations** | gestión multi-cuenta con facturación consolidada y SCP | varias cuentas, control central, gobernanza | no es IAM |
| **SCP** | límite máximo de permisos a nivel de cuenta u OU | bloquear servicios o acciones en cuentas enteras | no concede permisos |
| **AWS Support Center** | portal para gestionar casos de soporte | apertura y seguimiento de casos | no es Health Dashboard |
| **AWS Health Dashboard** | información sobre incidentes y mantenimiento que afectan a AWS o a la cuenta | estado del servicio o eventos programados | no es Trusted Advisor |
| **AWS Trusted Advisor** | recomendaciones de optimización | costo, seguridad, rendimiento, tolerancia a fallos y límites de servicio | no informa de incidentes reales del servicio |
| **AWS Knowledge Center** | artículos técnicos oficiales | localización de información técnica | no es documentación de precios |
| **AWS re:Post** | preguntas y respuestas técnicas | apoyo comunitario y técnico | no es un caso formal de soporte |
| **AWS Professional Services** | apoyo experto de AWS para proyectos y transformaciones | acompañamiento profesional | no es un plan de soporte estándar |
| **Arquitectos de soluciones de AWS** | apoyo técnico y de arquitectura en contexto comercial o técnico | orientación sobre diseño y adopción | no sustituyen soporte operativo continuo |

#### Cómo no confundir IAM y SCP

| Si la pregunta busca... | La respuesta suele ser... | Por qué |
| --- | --- | --- |
| **dar permiso a un usuario, rol o grupo para hacer algo** | **IAM** | IAM concede permisos a identidades dentro de la cuenta |
| **limitar lo que puede usar una cuenta completa o una OU, aunque IAM lo permita** | **SCP (Service Control Policies)** | una SCP establece el máximo permitido a nivel de organización; no concede permisos, solo los restringe |

### Planes de soporte

> **Nota de vigencia:** a **23 de marzo de 2026**, la guía oficial de examen `CLF-C02` sigue haciendo referencia a `Developer Support`, `Business Support`, `Enterprise On-Ramp` y `Enterprise Support`. Al mismo tiempo, la documentación comercial actual de AWS Support ya muestra `Basic`, `AWS Business Support+`, `AWS Enterprise Support` y `AWS Unified Operations`, e indica que `Developer Support`, `Business Support` y `Enterprise On-Ramp` dejarán de estar disponibles el **1 de enero de 2027**. Para responder preguntas de examen, conviene priorizar la terminología de la guía oficial vigente del examen.

| Plan o referencia de examen | Qué se debe recordar |
| --- | --- |
| **Basic Support** | documentación, foros, soporte de cuenta y facturación básico |
| **Developer Support** | pensado para desarrollo temprano; la guía de examen todavía lo menciona |
| **Business Support** | soporte 24/7 para producción; la guía de examen todavía lo menciona |
| **Enterprise On-Ramp** | nivel intermedio con orientación más avanzada; la guía de examen todavía lo menciona |
| **Enterprise Support** | TAM y soporte de máximo nivel para cargas críticas |
| **TAM** | la referencia más clara suele asociarse a niveles empresariales altos |

### Partners, abuso y Marketplace

| Tema | Qué se debe recordar |
| --- | --- |
| **AWS Marketplace** | catálogo de software y soluciones de terceros para desplegar en AWS |
| **ISV** | proveedor de software independiente |
| **System Integrator** | socio que ayuda a implantar, integrar o transformar |
| **Beneficios de ser partner** | formación, certificación, programas, eventos y ventajas comerciales |
| **Trust and Safety / denuncia de abuso** | canal para reportar abuso de recursos AWS |

### Chuleta del Dominio

| Si aparece... | Pensar en... |
| --- | --- |
| alertas por presupuesto | **AWS Budgets** |
| análisis histórico del gasto | **Cost Explorer** |
| detalle granular de uso y costo | **CUR** |
| estimación antes de desplegar | **Pricing Calculator** |
| varias cuentas con una sola factura | **AWS Organizations** |
| limitar servicios a nivel cuenta | **SCP** |
| estado o mantenimiento que afecta al servicio | **AWS Health Dashboard** |
| recomendaciones de optimización | **Trusted Advisor** |
| software de terceros en AWS | **AWS Marketplace** |

---

## Tablas de confusión alta

### 1. CloudWatch vs CloudTrail vs Config vs Health

| Servicio | Pregunta mental correcta |
| --- | --- |
| **CloudWatch** | ¿cómo está el sistema ahora? |
| **CloudTrail** | ¿quién hizo qué? |
| **Config** | ¿cómo estaba configurado esto y cuándo cambió? |
| **Health Dashboard** | ¿AWS tiene un incidente o mantenimiento que me afecta? |

### 2. GuardDuty vs Inspector vs Security Hub vs Detective

| Servicio | Idea correcta |
| --- | --- |
| **GuardDuty** | detecta actividad sospechosa |
| **Inspector** | detecta vulnerabilidades |
| **Security Hub** | centraliza hallazgos |
| **Detective** | investiga y correlaciona incidentes |

### 3. WAF vs Shield

| Servicio | Idea correcta |
| --- | --- |
| **WAF** | ataques web y reglas de capa 7 |
| **Shield** | DDoS |

### 4. SQS vs SNS vs EventBridge vs Step Functions

| Servicio | Idea correcta |
| --- | --- |
| **SQS** | cola, desacoplamiento, mensajes que esperan |
| **SNS** | publicación a múltiples suscriptores |
| **EventBridge** | eventos que disparan acciones |
| **Step Functions** | orquestación de pasos |

### 5. S3 vs EBS vs EFS vs FSx

| Servicio | Idea correcta |
| --- | --- |
| **S3** | objetos |
| **EBS** | bloque para una EC2 |
| **EFS** | archivos compartidos Linux |
| **FSx** | sistema de archivos especializado |

### 6. RDS / Aurora vs DynamoDB vs ElastiCache vs Redshift

| Servicio | Idea correcta |
| --- | --- |
| **RDS / Aurora** | relacional transaccional |
| **DynamoDB** | NoSQL |
| **ElastiCache** | caché en memoria |
| **Redshift** | analítica y data warehouse |

### 7. Internet Gateway vs NAT Gateway vs Virtual Private Gateway vs Transit Gateway

| Componente | Idea correcta |
| --- | --- |
| **Internet Gateway** | internet directo para recursos públicos |
| **NAT Gateway** | salida a internet de recursos privados |
| **Virtual Private Gateway** | extremo VPN en AWS para una VPC |
| **Transit Gateway** | hub central de conectividad para múltiples redes |

### 8. Budgets vs Cost Explorer vs CUR vs Pricing Calculator

| Herramienta | Idea correcta |
| --- | --- |
| **Budgets** | alertar |
| **Cost Explorer** | analizar gasto histórico |
| **CUR** | detalle granular |
| **Pricing Calculator** | estimar antes de crear |

---

## Checklist final antes del examen

* Diferenciar con seguridad **agilidad**, **elasticidad**, **escalabilidad** y **alta disponibilidad**.
* Recordar que **multi-AZ** y **multi-región** no responden al mismo problema.
* Tener clara la diferencia entre **responsabilidad de AWS** y **responsabilidad del cliente** en `EC2`, `RDS`, `Lambda` y `S3`.
* Saber distinguir **IAM user**, **IAM role**, **IAM Identity Center**, **Cognito**, **STS** y **root**.
* Identificar sin duda las parejas que más se cruzan: `CloudWatch / CloudTrail / Config`, `GuardDuty / Inspector`, `WAF / Shield`, `SQS / SNS / EventBridge / Step Functions`.
* Elegir correctamente entre **consola**, **CLI/API/SDK** e **IaC** según se trate de operación puntual o proceso repetible.
* Reconocer **IGW**, **NAT Gateway**, **VGW**, **Transit Gateway**, **Security Group** y **NACL**.
* Diferenciar **S3**, **EBS**, **EFS**, **FSx**, **Storage Gateway** y **AWS Backup**.
* No confundir en `S3` **bucket policy**, **versioning**, **replication** y **Object Lock**.
* No confundir **AMI** y **EBS Snapshot**.
* Diferenciar **RDS / Aurora**, **DynamoDB**, **ElastiCache**, **DocumentDB**, **Neptune** y **Redshift**.
* Tener clara la diferencia entre **Multi-AZ** y **Read Replica** en `RDS`.
* Saber qué herramientas sirven para **migrar**, cuáles para **descubrir** y cuáles para **justificar económicamente**.
* Distinguir **On-Demand**, **RI**, **Savings Plans**, **Spot**, **Dedicated Hosts**, **Dedicated Instances** y **Capacity Reservations**.
* Saber cuándo usar **Budgets**, **Cost Explorer**, **CUR**, **Pricing Calculator**, **Organizations**, **Trusted Advisor** y **AWS Health**.

---

## Fuentes oficiales de referencia

* Guía del examen `CLF-C02`: <https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02.html>
* Dominio 1: <https://docs.aws.amazon.com/es_es/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain1.html>
* Dominio 2: <https://docs.aws.amazon.com/es_es/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain2.html>
* Dominio 3: <https://docs.aws.amazon.com/es_es/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain3.html>
* Dominio 4: <https://docs.aws.amazon.com/es_es/aws-certification/latest/cloud-practitioner-02/cloud-practitioner-02-domain4.html>
* Servicios oficiales incluidos en alcance: <https://docs.aws.amazon.com/aws-certification/latest/cloud-practitioner-02/clf-02-in-scope-services.html>
* Planes de soporte de AWS: <https://docs.aws.amazon.com/awssupport/latest/user/aws-support-plans.html>
* Avisos de fin de soporte de planes heredados: <https://docs.aws.amazon.com/awssupport/latest/user/support-plans-eos.html>
* AWS CloudShell: <https://docs.aws.amazon.com/cloudshell/latest/userguide/welcome.html>
* IAM Access Analyzer: <https://docs.aws.amazon.com/IAM/latest/UserGuide/what-is-access-analyzer.html>
* Bucket policies de Amazon S3: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-policies.html>
* S3 Versioning: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/Versioning.html>
* S3 Object Lock: <https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lock.html>
* Multi-AZ en Amazon RDS: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/Concepts.MultiAZSingleStandby.html>
* Read replicas en Amazon RDS: <https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/USER_ReadRepl.html>
* Snapshots de Amazon EBS: <https://docs.aws.amazon.com/ebs/latest/userguide/how_snapshots_work.html>
* Amazon Machine Images (AMI): <https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ComponentsAMIs.html>


-------------------------------
-------------------------------
-------------------------------
-------------------------------

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

https://github.com/roxsross/aws-cloud-practitioner-complete-guide/blob/master/practice-exams/practice-exam-3.md
