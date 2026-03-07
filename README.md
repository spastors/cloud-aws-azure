# Guía de Estudio AWS Certified Cloud Practitioner (CLF-C02)

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

**Cómputo (Compute):**

- **Amazon EC2:** Máquinas virtuales configurables en la nube. Permite elegir sistema operativo, CPU, memoria y almacenamiento. Se paga por segundo u hora de uso. Incluye instancias on-demand (sin compromiso, pago por uso) y opciones de ahorro, como instancias reservadas o Savings Plans, además de Spot (capacidad ociosa con hasta ~90% de descuento).

<img width="1681" height="876" alt="image" src="https://github.com/user-attachments/assets/96943499-a954-4caa-933b-b514f1bba01b" />

- **AWS Lambda:** Computación serverless que ejecuta código ante eventos (HTTP, mensajes o cambios en datos). Escala automáticamente y se cobra por milisegundos de ejecución y memoria utilizada. Es ideal para tareas puntuales sin administrar servidores.
- **Amazon ECS/EKS/Fargate:** Servicios para ejecutar contenedores Docker. **ECS** es el orquestador propio de AWS. **EKS** es Kubernetes gestionado. **Fargate** permite lanzar contenedores sin gestionar servidores subyacentes. Estos servicios facilitan el despliegue de microservicios y aplicaciones en contenedores.

**Almacenamiento:**
- **Amazon S3:** Almacenamiento de objetos en la nube (archivos, imágenes y copias de seguridad). Es altamente escalable y redundante. Soporta distintos *niveles de almacenamiento* (Standard, Infrequent Access, Glacier, etc.) según la frecuencia de acceso. Es ideal para datos estáticos con control de versiones o copias de seguridad. Bucket (cajon/directorio donde se guardan objetos, debe ser nombre único en todo el mundo).
- **Amazon EBS:** Volúmenes de disco en bloque para usar con instancias EC2 (similar a discos duros en la nube).
- **Amazon EFS:** Sistema de archivos compartido (file storage) accesible desde varias instancias simultáneamente.
- **Amazon Glacier / Deep Archive:** Almacenamiento de larga duración y bajo coste para datos archivados (acceso infrecuente).

**Bases de datos:**

- **Amazon RDS (Relation Database Service):** Bases de datos relacionales gestionadas (MySQL, PostgreSQL, SQL Server, Oracle y Aurora). AWS se encarga de aplicar parches, replicar y hacer copias de seguridad. Soporta **Multi-AZ** para alta disponibilidad (réplicas en distintas AZs).

<img width="1244" height="587" alt="image" src="https://github.com/user-attachments/assets/cddbd8c6-fe66-4573-802d-74779ecbfda3" />

- **Amazon DynamoDB:** es un servicio de base de datos NoSQL de clave-valor y documentos, totalmente administrado y sin servidor (serverless) de Amazon Web Services (AWS), que ofrece un rendimiento rápido y predecible (en milisegundos) con escalabilidad automática. Es ideal para aplicaciones modernas, móviles, web, IoT y juegos que requieren alta disponibilidad y manejo de gran volumen de datos.
- **Amazon ElastiCache:** Servicio de caché en memoria compatible con Redis o Memcached para mejorar el rendimiento de aplicaciones.
- **Amazon Redshift** es un servicio de almacenamiento de datos (data warehouse) en la nube, totalmente gestionado y a escala de petabytes, diseñado para analítica de alto rendimiento. Utiliza almacenamiento columnar y procesamiento paralelo masivo (MPP) para consultas rápidas, permitiendo analizar grandes volúmenes de datos usando SQL y herramientas de BI convencionales a bajo costo.
- **Otros:** Amazon Neptune (base de grafos), DocumentDB (compatible con MongoDB), etc.

**Redes y entrega de contenido:**

- **Amazon VPC:** Red virtual privada en AWS donde se definen subredes, tablas de enrutamiento y gateways. Cada cuenta de AWS inicia con una VPC por región. Dentro de la VPC se crean *subredes* (públicas o privadas) y recursos (EC2, RDS, etc.). Se conecta al exterior mediante una **Puerta de Enlace a Internet (Internet Gateway)** y se pueden usar **NAT Gateways** para el tráfico saliente de subredes privadas. VPC actúa como una red tradicional propia en la nube.

<img width="1786" height="751" alt="image" src="https://github.com/user-attachments/assets/9537aa49-102e-4fd3-9623-b341b1cc3dd8" />

<img width="1649" height="762" alt="image" src="https://github.com/user-attachments/assets/66371141-a3be-4c27-b34e-a1d28e1f1e9c" />

- **Grupos de seguridad:** Firewalls a nivel de instancia EC2. Controlan qué tráfico entra o sale de cada servidor (por ejemplo, permitir SSH solo desde ciertas IPs). Son *stateful*: permiten respuestas automáticamente cuando una instancia origina tráfico.
- **Listas de control de acceso (NACL):** Firewalls a nivel de subred, que evalúan el tráfico de entrada y salida por reglas (stateless).
- **Elastic Load Balancing (ELB):** Distribuye automáticamente el tráfico entre múltiples instancias en una o más zonas de disponibilidad. Aumenta la disponibilidad y la tolerancia a fallos. Soporta distintos tipos (Application Load Balancer para HTTP/HTTPS, Network Load Balancer de baja latencia y Gateway Load Balancer para tráfico L4).
- **Amazon Route 53:** Servicio DNS escalable y de alta disponibilidad. Traduce nombres de dominio a IPs y permite enrutar tráfico de forma inteligente (geolocalización y latencia). También soporta balanceo de carga simple a Load Balancers o puntos finales.
- **Amazon CloudFront:** Red de entrega de contenido (CDN) global para distribuir contenido (contenidos web estáticos y dinámicos, como HTML, CSS, JavaScript e imágenes, así como vídeos) con baja latencia.

<img width="1852" height="794" alt="image" src="https://github.com/user-attachments/assets/e33c0ad9-b1e7-4516-9f4f-6135c684fb11" />

<img width="1834" height="933" alt="image" src="https://github.com/user-attachments/assets/7dc0e166-02b5-45c9-8da1-e96a26db6d62" />

- **AWS Global Accelerator** es un servicio de red que mejora la disponibilidad y el rendimiento (hasta un 60% más rápido) de las aplicaciones web y de Internet al dirigir el tráfico de usuarios a través de la infraestructura de red global de Amazon, en lugar de la red pública de Internet. Utiliza direcciones IP estáticas con Anycast para enrutar el tráfico al punto de enlace más cercano.

**Seguridad e IAM:**

- **AWS Identity and Access Management (IAM):** Permite crear usuarios, grupos y roles con permisos específicos. Un **usuario IAM** representa a una persona o aplicación que interactúa con AWS. Se recomienda aplicar el **principio de privilegio mínimo**, dando a cada usuario solo los permisos necesarios. La *cuenta root* (creador de la cuenta) tiene todos los permisos. Se aconseja protegerla con **MFA** (autenticación de dos factores) y usarla solo cuando sea imprescindible. AWS permite habilitar MFA para cualquier usuario IAM, requiriendo un código adicional generado en un dispositivo, lo que mejora la seguridad.

<img width="1231" height="752" alt="image" src="https://github.com/user-attachments/assets/0bbb6e8e-477a-4c86-95aa-84bd387cd295" />

- **Políticas de IAM:** Documentos en JSON que definen permisos (qué acciones puede realizar un usuario o rol sobre qué recursos). Se adjuntan a usuarios, grupos o roles para controlar el acceso.

<img width="956" height="733" alt="image" src="https://github.com/user-attachments/assets/b3897885-dff2-407f-85d4-560d3b985a69" />
<img width="1638" height="761" alt="image" src="https://github.com/user-attachments/assets/01afeb5c-b3e3-4bf5-b41f-d516754e5527" />
<img width="1638" height="761" alt="image" src="https://github.com/user-attachments/assets/ebac3c56-ee47-4d46-92b8-bb75eb766b9d" />
<img width="1186" height="712" alt="image" src="https://github.com/user-attachments/assets/ba672110-7fd9-409b-8195-05eab527533e" />

- **Amazon Macie** es un servicio de seguridad y privacidad de datos totalmente gestionado que utiliza machine learning y coincidencia de patrones para descubrir, clasificar y proteger automáticamente información sensible (como datos personales o financieros) almacenada en Amazon S3.
- **Amazon Network ACLs** (Listas de Control de Acceso a la Red) son una capa de seguridad esencial en AWS que actúa como un firewall sin estado (stateless) a nivel de subred. Controlan el tráfico entrante y saliente, permitiendo o denegando reglas específicas para proteger los recursos dentro de una VPC.
- **Amazon Cognito** es un servicio de Amazon Web Services (AWS) que gestiona el registro, inicio de sesión y control de acceso de usuarios en aplicaciones web y móviles.
- **AWS Backup** es un servicio de gestión de copias de seguridad totalmente administrado y centralizado que automatiza la protección de datos en la nube de AWS y entornos híbridos. Permite configurar políticas, programar respaldos y gestionar retenciones para servicios como Amazon EC2, RDS, EBS, S3 y DynamoDB, facilitando el cumplimiento normativo.
- **Amazon GuardDuty** es un servicio de detección de amenazas inteligente y administrado que monitorea continuamente las cuentas, cargas de trabajo (como EC2, EKS, Lambda) y datos de almacenamiento (S3) de AWS en busca de actividades maliciosas, comportamientos inusuales y malware. Utiliza inteligencia artificial, aprendizaje automático y fuentes de datos de seguridad para proporcionar alertas detalladas, facilitando la remediación rápida.

- **Otros servicios de seguridad:** AWS ofrece servicios específicos como AWS KMS (gestión de claves), Shield/WAF (protección contra ataques DDoS y filtrado de tráfico web)

## Facturación y gestión de costes

AWS ofrece herramientas para controlar los gastos y entender los costes:

- **Modelos de precios:** AWS cobra mayoritariamente por consumo. En EC2, por ejemplo, existen instancias **bajo demanda** (pago por hora o segundo, sin compromiso previo), instancias **reservadas** o **Savings Plans** (compromiso por 1 a 3 años con descuento) y **Spot** (capacidad no usada, hasta ~90% más barato). Los servicios de almacenamiento y datos también se cobran según el uso y el nivel. Es clave conocer estas opciones para optimizar costes. **Amazon Spot Instances** son máquinas virtuales de Amazon EC2 que permiten utilizar la capacidad de cómputo sobrante de AWS con descuentos de hasta el 90% respecto a los precios bajo demanda. Son ideales para cargas de trabajo flexibles, sin estado y tolerantes a interrupciones, ya que AWS puede recuperar la instancia con un aviso de 2 minutos.
- **Facturación consolidada de Amazon AWS** es una funcionalidad de AWS Organizations que agrupa los cargos de múltiples cuentas de AWS en una sola factura, permitiendo una gestión financiera centralizada. Sus principales ventajas son la simplificación contable, una única fecha de pago, y descuentos por volumen acumulados de todas las cuentas. Ventajas clave:
  - Una sola factura: Simplifica la administración al consolidar los cargos de todas las cuentas vinculadas, reduciendo el papeleo.
  - Descuentos por volumen (Pricing Volume Discounts): Permite combinar el uso de servicios de todas las cuentas para alcanzar niveles de precios más bajos (descuentos por volumen) en servicios como S3, EC2 y Savings Plans, lo que reduce los costos generales.
  - Gestión eficiente y visibilidad: La cuenta principal ("master account") puede visualizar y desglosar los costos y el uso de cada cuenta miembro, facilitando la auditoría y control de costos.
  - Pagos simplificados: Estandariza los ciclos de facturación, lo que mejora la gestión del flujo de caja al tener fechas de vencimiento unificadas.
  - Independencia de cuentas: Aunque la facturación está centralizada, todas las cuentas miembros siguen siendo independientes en términos de recursos y seguridad

- **Etiquetado y reportes:** Se recomienda usar **tags (etiquetas)** en recursos para atribuir costes a proyectos o equipos. AWS Cost and Usage Reports y Cost Explorer permiten analizar el consumo histórico y las tendencias.
- **AWS Budgets:** Herramienta para establecer presupuestos y alertas. Permite definir alertas (por ejemplo, enviar un correo o disparar una acción cuando se supere el 80% del presupuesto mensual). Se pueden crear presupuestos de coste total, de uso de recursos o de cobertura (RI/Savings Plans) y recibir notificaciones vía email o SNS.
- **AWS Cost Explorer:** Interfaz para visualizar y analizar los costes y el uso históricos. Permite crear informes personalizados, ver tendencias de gasto de los últimos 13 meses y pronosticar hasta 18 meses. También ofrece recomendaciones de instancias reservadas óptimas.
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
  - Comercial (Business): Alinear la estrategia de TI con los objetivos de negocio.
  - Personas (People): Capacitar al personal y gestionar el cambio organizativo.
  - Gobernanza (Governance): Gestionar el cumplimiento, riesgos y prioridades.
  - Plataforma (Platform): Diseñar y escalar la arquitectura técnica.
  - Seguridad (Security): Garantizar la protección de datos y el cumplimiento.
  - Operaciones (Operations): Asegurar la fiabilidad y funcionamiento continuo. 

## Buenas prácticas en AWS

- **Responsabilidad Compartida:** AWS se encarga de la seguridad *de* la nube (infraestructura física, redes y centros de datos), mientras que el cliente es responsable de la seguridad *en* la nube (sistema operativo, aplicaciones, datos y configuraciones). Por ejemplo, AWS asegura la integridad del hardware y la virtualización, pero el usuario debe mantener los datos cifrados y los permisos de IAM bien configurados.

<img width="1818" height="784" alt="image" src="https://github.com/user-attachments/assets/d92afcb5-e11c-4d42-bad9-5c77a4e1354a" />

- **AWS Well-Architected Framework** es un conjunto de mejores prácticas, principios de diseño y guías de Amazon Web Services (AWS) para ayudar a arquitectos de la nube a construir infraestructura segura, de alto rendimiento, resiliente y eficiente. Se basa en seis pilares fundamentales, evaluando cargas de trabajo para optimizar costos y sostenibilidad. 
  - Excelencia operativa: Ejecutar y monitorear sistemas, mejorando procesos continuamente.
  - Seguridad: Proteger información, sistemas y activos.
  - Fiabilidad (Reliability): Capacidad de recuperarse de fallos y escalar recursos.
  - Eficiencia de rendimiento: Usar recursos computacionales de manera eficiente.
  - Optimización de costes: Evitar costos innecesarios y maximizar el retorno de inversión.
  - Sostenibilidad: Minimizar el impacto ambiental de la carga de trabajo.

- **AWS Trusted Advisor:** Herramienta que analiza el entorno de AWS y ofrece recomendaciones basadas en buenas prácticas extraídas de miles de clientes. Trusted Advisor sugiere acciones para *ahorrar dinero*, *mejorar la disponibilidad y el rendimiento* o *cerrar huecos de seguridad*. Con soporte básico se accede a algunas verificaciones. Con planes Business o Enterprise se tiene acceso completo a todos los checks. Por ejemplo, puede identificar instancias EC2 infrautilizadas para apagarlas y ahorrar costes.
- **Mínimo privilegio:** Otorgar solo los permisos estrictamente necesarios a usuarios y roles (evitando permisos administrativos innecesarios) es una práctica esencial de seguridad. Además, activar **MFA** (autenticación multifactor) en todas las cuentas de IAM refuerza la protección.

## Redes básicas de AWS

Cada cuenta de AWS dispone de una **VPC (Virtual Private Cloud)** por región. En la VPC se definen subredes (públicas o privadas), rutas y gateways. Por ejemplo, una subred pública se conecta a Internet mediante una **Puerta de Internet (IGW)**, mientras que una subred privada usa una **NAT Gateway** para el tráfico saliente. Los **Security Groups** actúan como cortafuegos virtuales a nivel de instancia. AWS organiza sus centros de datos en **Regiones** (ubicaciones geográficas) y **Zonas de Disponibilidad** (centros independientes dentro de cada región), lo que permite diseñar aplicaciones multi-AZ para alta disponibilidad.

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

La cultura **DevOps** fomenta la colaboración entre desarrollo y operaciones para entregar software con frecuencia y calidad, mediante automatización y CI/CD. En AWS, servicios como **CodeCommit** (repositorio Git), **CodeBuild** (compilación) y **CodeDeploy/CodePipeline** (entrega continua) ayudan a implementar DevOps. Por ejemplo, un cambio en el código puede activar automáticamente una pipeline que ejecute pruebas y despliegue en AWS. La **Infraestructura como Código (IaC)** permite definir recursos (redes, servidores y bases) en archivos (JSON o YAML). AWS CloudFormation es un servicio de IaC que modela y aprovisiona recursos de AWS de forma automática a partir de plantillas.

## Interoperabilidad y portabilidad

En la nube, **interoperabilidad** significa que distintos sistemas o nubes pueden comunicarse e intercambiar datos usando estándares comunes. La **portabilidad** es la capacidad de trasladar cargas de trabajo (aplicaciones y datos) entre proveedores o entre entornos local y nube con cambios mínimos. Por ejemplo, almacenar datos en formatos abiertos o usar contenedores puede facilitar mover una aplicación de AWS a Azure sin dependencias propietarias. Estos conceptos son clave para evitar el *vendor lock-in* y aprovechar múltiples nubes o centros locales según convenga.

## Ejemplos prácticos de uso y migración

- **Migración de datos grandes:** Usar AWS Snowball para copiar petabytes de información desde un centro de datos local a S3 (dispositivo físico seguro que se envía al cliente, se carga con datos y se devuelve).
- **Amazon S3 File Gateway** es un servicio de almacenamiento híbrido que permite a las aplicaciones locales (on-premises) acceder a datos en la nube de Amazon S3 utilizando protocolos estándar de archivos como NFS o SMB. Facilita la migración, copia de seguridad y almacenamiento en la nube al funcionar como un puente entre servidores locales y S3, ofreciendo almacenamiento casi ilimitado y caché local para baja latencia.
- **AWS Application Discovery Service (ADS)** es un servicio de Amazon Web Services diseñado para ayudar a las empresas a planificar su migración a la nube. Recopila automáticamente datos detallados de configuración, rendimiento y dependencia (conexiones TCP) de servidores locales y bases de datos, integrándose con AWS Migration Hub para facilitar la migración
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
