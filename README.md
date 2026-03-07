# Guía de Estudio AWS Certified Cloud Practitioner (CLF-C02)

## Fundamentos de Cloud Computing

La **computación en la nube** consiste en entregar recursos informáticos (cómputo, almacenamiento, bases de datos, etc.) *bajo demanda* a través de Internet, siguiendo un modelo de pago por uso[*[1][2]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). Esto elimina la necesidad de comprar y gestionar hardware propio, y permite a las organizaciones escalar rápidamente según la demanda. Entre las ventajas clave destacan la **agilidad** (poner recursos en marcha en minutos), la **elasticidad** (escalar automáticamente) y el **ahorro de costos**, al pagar solo por lo consumido[*[2]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).

En la nube, el gasto pasa de **CAPEX** (inversiones en infraestructuras fijas, como servidores o licencias) a **OPEX** (costos operativos variables, según el uso)[*[3][4]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). Esto reduce el *Costo Total de Propiedad* (TCO), ya que minimiza el CAPEX inicial y ajusta el gasto al uso real[*[5][6]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). Por ejemplo, en un entorno propio (on-premises) se asumen grandes CAPEX y costos de mantenimiento, mientras que en la nube el coste suele ser más predecible y flexible[*[5][6]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).

## Modelos de servicio y de despliegue

- **IaaS, PaaS y SaaS:** Son modelos de servicio en la nube que definen el nivel de control del usuario. En **IaaS (Infraestructura como Servicio)** el proveedor gestiona el hardware y la virtualización, mientras el cliente controla el sistema operativo, middleware y aplicaciones. En **PaaS (Plataforma)** el proveedor también gestiona el SO y el runtime, dejando al usuario enfocarse en las aplicaciones. En **SaaS (Software)**, el proveedor gestiona todo y el usuario solo utiliza la aplicación final. La siguiente tabla compara quién controla cada componente en IaaS, PaaS y SaaS[*[7]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)[[8]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)*:

| **Componente** | **IaaS** | **PaaS** | **SaaS** |
| --- | --- | --- | --- |
| **Hardware físico** | Proveedor | Proveedor | Proveedor |
| **Virtualización** | Proveedor | Proveedor | Proveedor |
| **Sistema operativo (OS)** | Cliente | Proveedor | Proveedor |
| **Middleware** | Cliente | Proveedor | Proveedor |
| **Runtime (ejecución)** | Cliente | Proveedor | Proveedor |
| **Aplicaciones** | Cliente | Cliente | Proveedor |
| **Datos de la aplicación** | Cliente | Cliente | Cliente |
| Cada modelo tiene casos de uso: por ejemplo, IaaS (EC2, EBS) es ideal si necesitas control total del entorno; PaaS (AWS Elastic Beanstalk, RDS) acelera el desarrollo sin gestionar infra; SaaS (Gmail, Salesforce) ofrece aplicaciones listas para usar. |  |  |  |
- **Nubes públicas, privadas, híbridas y multicloud:**
- **Nube pública:** Infraestructura compartida, proveída por terceros (ej. AWS, Azure, GCP) y usada *por muchos clientes*. Ofrece alta escalabilidad y costos bajos por pago por uso, pero menor control sobre la infraestructura[*[9]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)[[10]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)*.
- **Nube privada:** Infraestructura dedicada a una sola organización, ya sea en sus propias instalaciones o en un centro del proveedor. Ofrece más control, seguridad y cumplimiento, pero requiere alta inversión (mayor CAPEX) y gestión propia[*[10]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **Nube híbrida:** Combina pública y privada. Permite, por ejemplo, mantener datos sensibles en la nube privada y procesarlos en la pública cuando la demanda sube, conectando ambos entornos y compartiendo datos[*[11]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). Es útil para combinar escalabilidad con seguridad.
- **Multicloud:** Uso de servicios de *varios* proveedores públicos a la vez. Reduce dependencia de un solo proveedor y permite aprovechar fortalezas de cada nube, pero requiere gestionar compatibilidad e integración[*[12]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)[[13]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)*.

Cada tipo responde a necesidades distintas. Por ejemplo, una empresa puede usar AWS (pública) para cargas generales y mantener su propio centro (privada) para datos críticos, o usar AWS + Azure simultáneamente (multicloud) para evitar vendor lock-in[*[12]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)[[13]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)*.

## Principales proveedores de la nube

Los líderes del mercado de servicios cloud son **Amazon Web Services (AWS)**, **Microsoft Azure** y **Google Cloud Platform (GCP)**, que ofrecen conjuntos similares de servicios globales. AWS es el proveedor más maduro y amplio, seguido por Azure (fuerte en entornos empresariales) y GCP (foco en datos/ML). También existen otros proveedores relevantes: IBM Cloud, Oracle Cloud, Alibaba Cloud, entre otros[*[14]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). En general, AWS se destaca por su catálogo de servicios muy extenso y presencia global, lo que la hace ideal para empezar en la nube.

## Servicios principales de AWS

- **Cómputo (Compute):**
- **Amazon EC2:** Máquinas virtuales configurables en la nube. Permite elegir sistema operativo, CPU, memoria y almacenamiento. Se paga por segundo u hora de uso[*[15]*](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20bajo%20demanda%20Las%20instancias,M%C3%A1s%20informaci%C3%B3n). Incluye instancias on-demand (sin compromiso, pago por uso) y modos de ahorro: instancias reservadas/Savings Plans y Spot (capacidad ociosa con hasta ~90% de descuento)[*[15]](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20bajo%20demanda%20Las%20instancias,M%C3%A1s%20informaci%C3%B3n)[[16]](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20de%20spot%20Con%20las,M%C3%A1s%20informaci%C3%B3n)*.
- **AWS Lambda:** Computación serverless que ejecuta código ante eventos (HTTP, mensajes, cambios en datos). Escala automáticamente y se cobra por milisegundos de ejecución y memoria usada. Ideal para tareas puntuales sin administrar servidores.
- **Amazon ECS/EKS/Fargate:** Servicios para ejecutar contenedores Docker. **ECS** es el orquestador propio de AWS; **EKS** es Kubernetes gestionado; **Fargate** permite lanzar contenedores sin gestionar servidores subyacentes. Estos servicios facilitan desplegar microservicios y aplicaciones en contenedores.
- **Almacenamiento:**
- **Amazon S3:** Almacenamiento de objetos en la nube (archivos, imágenes, backups). Altamente escalable y redundante. Soporta distintos *niveles de almacenamiento* (Standard, Infrequent Access, Glacier, etc.) según frecuencia de acceso. Ideal para datos estáticos o backups.
- **Amazon EBS:** Volúmenes de disco en bloque para usar con instancias EC2 (similar a discos duros en nube).
- **Amazon EFS:** Sistema de archivos compartido (file storage) accesible desde varias instancias simultáneamente.
- **Amazon Glacier / Deep Archive:** Almacenamiento de larga duración y bajo costo para datos archivados (acceso infrecuente).
- **Bases de datos:**
- **Amazon RDS:** Bases de datos relacionales gestionadas (MySQL, PostgreSQL, SQL Server, Oracle, Aurora). AWS se encarga de parchear, replicar y hacer backups. Soporta **Multi-AZ** para alta disponibilidad (réplicas en distintas AZs).
- **Amazon DynamoDB:** Base de datos NoSQL (clave-valor, docu­mento) totalmente gestionada, con latencia baja y escalabilidad automática.
- **Amazon ElastiCache:** Servicio de caché en memoria compatible con Redis o Memcached para mejorar rendimiento de aplicaciones.
- **Amazon Redshift:** Almacén de datos (data warehouse) para análisis a gran escala.
- **Otros:** Amazon Neptune (base de grafos), DocumentDB (MongoDB compatible), etc.
- **Redes y entrega de contenido:**
- **Amazon VPC:** Red virtual privada en AWS donde se definen subredes, tablas de enrutamiento y gateways[*[17]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS). Cada cuenta AWS inicia con una VPC por región. Dentro de la VPC se crean *subredes* (públicas o privadas) y recursos (EC2, RDS, etc.). Se conecta al mundo exterior mediante una **Puerta de Enlace a Internet (Internet Gateway)** y se puede usar **NAT Gateways** para tráfico saliente de subredes privadas. VPC actúa como una red tradicional propia en la nube[*[18]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS).
- **Grupos de seguridad:** Firewalls a nivel de instancia EC2. Controlan qué tráfico entra o sale de cada servidor (por ejemplo, permitir SSH solo desde ciertas IPs)[*[19]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html#:~:text=Un%20grupo%20de%20seguridad%20controla,y%20salida%20de%20la%20instancia). Son *stateful*: permiten respuestas automáticamente cuando una instancia origina tráfico.
- **Listas de control de acceso (NACL):** Firewalls a nivel de subred, que evalúan tráfico de entrada/salida por reglas (stateless).
- **Elastic Load Balancing (ELB):** Distribuye automáticamente tráfico entre múltiples instancias en una o más zonas de disponibilidad[*[20]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=Elastic%20Load%20Balancing%20distribuye%20autom%C3%A1ticamente,cambios%20en%20el%20tr%C3%A1fico%20entrante). Aumenta disponibilidad y tolerancia a fallos; soporta distintos tipos (Application Load Balancer para HTTP/HTTPS, Network Load Balancer de baja latencia, Gateway Load Balancer para tráficos L4).
- **Amazon Route 53:** Servicio DNS escalable de alta disponibilidad. Traduce nombres de dominio a IPs, posibilita direccionar tráfico de forma inteligente (geolocalización, latencia)[*[21]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=,Gu%C3%ADa%20para%20desarrolladores%20de%20Amazon). También soporta balanceo de carga simple a Load Balancers o puntos finales.
- **Amazon CloudFront:** Red de entrega de contenido (CDN) global para distribuir contenido con baja latencia.
- **Seguridad e IAM:**
- **AWS Identity and Access Management (IAM):** Permite crear usuarios, grupos y roles con permisos específicos. Un **usuario IAM** representa una persona o aplicación que interactúa con AWS[*[22]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=Un%20usuario%20de%20IAM%20es,de%20un%20nombre%20y%20credenciales). Es *recomendado* aplicar el **principio de privilegio mínimo**, dando a cada usuario sólo los permisos necesarios. La *cuenta root* (creador de la cuenta) tiene todos los permisos; se aconseja asegurarla con **MFA** (autenticación de dos factores) y usarla solo cuando sea imprescindible. AWS permite habilitar MFA para cualquier usuario IAM, requiriendo un código adicional generado en un dispositivo, lo que mejora la seguridad[*[23]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=,un%20smartphone%20o%20una%20tablet).
- **Políticas de IAM:** Documentos en JSON que definen permisos (qué acciones puede realizar un usuario/rol sobre qué recursos). Se adjuntan a usuarios/grupos/roles para controlar el acceso.
- **Otros servicios de seguridad:** AWS ofrece servicios específicos como AWS KMS (gestión de claves), Shield/WAF (protección contra ataques DDoS y filtrado de tráfico web), GuardDuty (detección de amenazas), etc., aunque no son obligatorios para el nivel Cloud Practitioner.

## Facturación y gestión de costos

AWS ofrece herramientas para controlar los gastos y entender los costos:

- **Modelos de precios:** AWS cobra mayoritariamente por consumo. En EC2, por ejemplo, existen instancias **bajo demanda** (pago por hora/segundo, sin compromiso previo)[*[15]*](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20bajo%20demanda%20Las%20instancias,M%C3%A1s%20informaci%C3%B3n), instancias **reservadas** o **Savings Plans** (compromiso por 1-3 años con descuento) y **Spot** (capacidad no usada, hasta ~90% más barato)[*[16]*](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20de%20spot%20Con%20las,M%C3%A1s%20informaci%C3%B3n). Los servicios de almacenamiento y datos también cobran según el uso y el nivel. Es clave conocer estas opciones para optimizar costos.
- **Facturación consolidada:** Con AWS Organizations se pueden vincular varias cuentas bajo una factura maestra, compartir beneficios (p. ej., volúmenes para descuentos) y aislar recursos por unidad de negocio.
- **Etiquetado y reportes:** Se recomienda usar **tags (etiquetas)** en los recursos para atribuir costos a proyectos o equipos. AWS Cost and Usage Reports y Cost Explorer permiten analizar el consumo histórico y las tendencias.
- **AWS Budgets:** Herramienta para definir presupuestos y alertas. Permite crear avisos (por ejemplo, enviar un correo o disparar una acción cuando se supere el 80% del presupuesto mensual)[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n). Se pueden crear presupuestos de costo total, de uso de recursos o de cobertura (RI/Savings Plans) y recibir notificaciones por email o SNS[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n).
- **AWS Cost Explorer:** Interfaz para visualizar y analizar los costes y el uso históricos[*[25]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html#:~:text=AWS%20Cost%20Explorer%20es%20una,usar%20para%20comprender%20los%20costos). Permite crear informes personalizados, ver tendencias de gasto de los últimos 13 meses y pronosticar hasta 18 meses[*[25]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html#:~:text=AWS%20Cost%20Explorer%20es%20una,usar%20para%20comprender%20los%20costos). También ofrece recomendaciones de instancias reservadas óptimas.

Un **ejemplo práctico**: una empresa puede crear en AWS Budgets un presupuesto mensual fijo para gastos, y configurar una alerta que envíe un correo si el costo real alcanza el 80% del presupuesto[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n). De esta forma, controlan sus gastos proactivamente y toman medidas (p.ej. apagar recursos no críticos) antes de exceder el presupuesto. Para migraciones de datos, se puede usar **AWS Snowball** (un dispositivo físico seguro) para trasladar petabytes de información a AWS sin depender de la red pública[*[26]*](https://aws.amazon.com/snowball/#:~:text=Simple%20migration). Este dispositivo se envía al cliente, se copia la data y luego se devuelve a AWS, acelerando migraciones masivas de datos.

## Soporte técnico (AWS Support)

Todos los clientes de AWS disponen de soporte *Básico* gratuito, que incluye acceso 24/7 a documentación, foros (AWS re:Post) y un número limitado de **Trusted Advisor Checks** básicos para límites de servicio[*[27]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=,el%20desempe%C3%B1o%20y%20la%20seguridad). Para soporte técnico con tiempos de respuesta garantizados, existen planes de pago: **Developer**, **Business** y **Enterprise**. Estos ofrecen asistencia 24/7 (teléfono, chat, email) y recursos especializados:

- **Developer:** soporte básico para una sola persona, con atención en horario comercial.
- **Business:** ideal para cargas de producción. Incluye atención 24/7 con tiempos de respuesta desde 1 hora (p. ej., 12-24 h para soporte general)[*[28]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=Tel%C3%A9fono%2C%20web%2C%20chat%20y%20correo,los%207%C2%A0d%C3%ADas%20de%20la%20semana).
- **Enterprise:** para negocios críticos. Incluye, además, un TAM (Técnico de Cuenta Designado) y revisión proactiva de arquitecturas.

En resumen, los planes de pago proporcionan **soporte técnico 24/7** y **recomendaciones ilimitadas** de Trusted Advisor[*[28]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=Tel%C3%A9fono%2C%20web%2C%20chat%20y%20correo,los%207%C2%A0d%C3%ADas%20de%20la%20semana). Por ejemplo, los planes Business y Enterprise permiten crear casos ilimitados y acceder a asesoría experta en arquitectura[*[28]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=Tel%C3%A9fono%2C%20web%2C%20chat%20y%20correo,los%207%C2%A0d%C3%ADas%20de%20la%20semana).

## Buenas prácticas en AWS

- **Responsabilidad Compartida:** AWS se encarga de la seguridad *de* la nube (infraestructura física, redes, centros de datos), mientras que el cliente es responsable de la seguridad *en* la nube (sistema operativo, aplicaciones, datos, configuraciones)[*[29]*](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=ya%20que%20AWS%20opera%2C%20administra,la%20legislaci%C3%B3n%20y%20los%20reglamentos). Por ejemplo, AWS asegura la integridad del hardware y la virtualización, pero el usuario debe mantener sus datos cifrados y sus permisos IAM bien configurados[*[29]](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=ya%20que%20AWS%20opera%2C%20administra,la%20legislaci%C3%B3n%20y%20los%20reglamentos)[[30]](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=AWS%20tiene%20la%20responsabilidad%20de,en%20la%20nube%20de%20AWS)*.
- **Framework Well-Architected:** AWS promueve 6 pilares para diseñar arquitecturas robustas: excelencia operativa, seguridad, fiabilidad, eficiencia de rendimiento, optimización de costos y sostenibilidad[*[31]*](https://aws.amazon.com/es/architecture/well-architected/#:~:text=AWS%20Well,ofrece%20un%20enfoque). Estas áreas reúnen buenas prácticas (por ejemplo, monitorizar logs, aplicar caching, automatizar pruebas). Se recomienda revisar nuestras cargas con estas pautas.
- **AWS Trusted Advisor:** Es una herramienta que analiza el entorno de AWS y brinda recomendaciones basadas en las mejores prácticas aprendidas de miles de clientes[*[32]*](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html#:~:text=Trusted%20Advisor%20se%20basa%20en,cerrar%20las%20brechas%20de%20seguridad). Advisor sugiere acciones para *ahorrar dinero*, *mejorar disponibilidad y rendimiento* o *cerrar huecos de seguridad[[32]](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html#:~:text=Trusted%20Advisor%20se%20basa%20en,cerrar%20las%20brechas%20de%20seguridad)*. Incluso con soporte básico se accede a algunas verificaciones, pero con planes Business/Enterprise se tiene acceso completo a todos los checks. Usar Trusted Advisor permite, por ejemplo, identificar instancias EC2 infrautilizadas para apagarlas y ahorrar costos.
- **Mínimo privilegio:** Otorgar solo los permisos estrictamente necesarios a usuarios y roles (evitar dar permisos administrativos innecesarios) es una práctica esencial de seguridad. Igualmente, activar **MFA** (autenticación multi-factor) en todas las cuentas IAM fortalece la protección[*[23]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=,un%20smartphone%20o%20una%20tablet).

## Redes básicas de AWS

Cada cuenta AWS dispone de una **VPC (Virtual Private Cloud)** por región. En la VPC se definen subredes (públicas/privadas), rutas y gateways. Por ejemplo, una subred pública conecta a Internet vía una **Puerta de Internet (IGW)**[*[33]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Puertas%20de%20enlace%20y%20puntos,de%20conexi%C3%B3n), mientras que una privada usa una **NAT Gateway** para tráfico saliente. Las **Security Groups** actúan como cortafuegos virtuales a nivel de instancia[*[19]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html#:~:text=Un%20grupo%20de%20seguridad%20controla,y%20salida%20de%20la%20instancia). AWS organiza sus datacenters en **Regiones** (ubicaciones geográficas) y **Zonas de Disponibilidad** (centros independientes dentro de cada región), lo que permite diseñar aplicaciones multi-AZ para alta disponibilidad.

**Route 53** es el servicio DNS de AWS, traduciendo nombres de dominio a direcciones IP e integrándose con balanceadores de carga[*[21]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=,Gu%C3%ADa%20para%20desarrolladores%20de%20Amazon). **Elastic Load Balancer** (ELB) reparte automáticamente tráfico de aplicaciones entre varias instancias en múltiples zonas, sólo enviando tráfico a instancias “saludables”[*[20]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=Elastic%20Load%20Balancing%20distribuye%20autom%C3%A1ticamente,cambios%20en%20el%20tr%C3%A1fico%20entrante). Esto mejora la escalabilidad y tolerancia a fallos de las aplicaciones.

## Contenedores y orquestación

Un **contenedor** encapsula una aplicación con sus dependencias en un entorno portátil y ligero (ej. Docker)[*[34]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). En AWS se pueden ejecutar contenedores mediante **Amazon ECS** o **EKS**. *Kubernetes* (open-source) es un sistema de orquestación que automatiza el despliegue, escalado y gestión de aplicaciones en contenedores[*[35]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). AWS ofrece **EKS** como servicio gestionado de Kubernetes, y **Fargate** para correr contenedores sin administrar servidores. Por ejemplo, una aplicación web puede desplegarse en un clúster ECS con varios contenedores que se escalan según la demanda.

## DevOps e Infraestructura como Código

La cultura **DevOps** fomenta la colaboración entre desarrollo y operaciones para entregar software con frecuencia y calidad, usando automatización y CI/CD[*[36]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). En AWS, servicios como **CodeCommit** (repositorio Git), **CodeBuild** (compilación), **CodeDeploy/CodePipeline** (entrega continua) ayudan a implementar DevOps. Por ejemplo, un cambio en el código puede activar automáticamente una pipeline que ejecute pruebas y despliegue en AWS. La **Infraestructura como Código (IaC)** permite definir recursos (redes, servidores, bases) en archivos (JSON/YAML). AWS CloudFormation es un servicio IaC que modela y aprovisiona de forma automática recursos AWS a partir de plantillas[*[37]*](https://aws.amazon.com/es/cloudformation/#:~:text=AWS%20CloudFormation).

## Interoperabilidad y portabilidad

En la nube, **interoperabilidad** significa que distintos sistemas o nubes pueden comunicarse e intercambiar datos usando estándares comunes[*[38]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). La **portabilidad** es la capacidad de trasladar cargas de trabajo (aplicaciones, datos) entre proveedores o entre local y nube con mínimos cambios[*[39]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). Por ejemplo, almacenar datos en formatos abiertos o usar contenedores puede facilitar mover una aplicación AWS a Azure sin dependencias propietarias. Estos conceptos son clave para evitar el *vendor lock-in* y poder aprovechar múltiples nubes o centros locales según convenga[*[40]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).

## Ejemplos prácticos de uso y migración

- **Migración de datos grandes:** Usar AWS Snowball para copiar petabytes de información desde un centro de datos local a S3[*[26]*](https://aws.amazon.com/snowball/#:~:text=Simple%20migration) (dispositivo físico seguro que se envía al cliente, se carga con datos y se devuelve).
- **Estrategia de migración (7 R’s):** Al planear migrar aplicaciones a la nube existen varias estrategias: Rehost (lift&shift), Repurchase (usar SaaS), Replatform (cambios menores), Refactor (rediseñar en cloud), Retire, Retain, Relocate. Estas estrategias se ilustran en la siguiente figura, que resume opciones para migrar o refactorizar cada aplicación:

*Ejemplo visual de estrategias de migración (“7 R’s”), desde lift & shift hasta re-diseñar aplicaciones para la nube.*

- **Optimización de costos:** Por ejemplo, una startup puede lanzar una aplicación en EC2 bajo demanda y luego, cuando se estabilice, reservar capacidad para reducir gastos. También puede habilitar Auto Scaling para reducir servidores en horas bajas.
- **Presupuestos y alertas:** Crear presupuestos mensuales en AWS Budgets y configurar notificaciones (SNS/email) cuando se aproxime el límite. Como práctica, se puede fijar una alerta al 80% del presupuesto para revisar el gasto[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n).
- **Seguridad:** Implementar políticas de IAM estrictas y habilitar MFA. Por ejemplo, exigir que sólo los ingenieros senior puedan lanzar instancias EC2 productivas, mientras que desarrolladores tienen permisos más limitados en entornos de prueba.
- **Alta disponibilidad:** Desplegar instancias en múltiples AZ dentro de una región. Por ejemplo, una base de datos RDS se configura con Multi-AZ para replicar datos en otra zona y soportar fallos.
- **Contenedores y Serverless:** Para una app web con picos de tráfico, se puede ejecutar el backend en contenedores (ECS/EKS) y funciones Lambda para tareas puntuales (procesar imágenes, enviar emails), aprovechando la escalabilidad automática.

## Glosario de términos clave

- **CAPEX (Capital Expenditure):** Gastos de capital; inversiones iniciales en activos duraderos (servidores, hardware, licencias perpetuas)[*[3]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). En la nube, el CAPEX se minimiza.
- **OPEX (Operational Expenditure):** Gastos operativos; costos recurrentes de operación (consumo de recursos, suscripciones, licencias anuales)[*[4]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21). En la nube, la mayoría de costos son OPEX (pago por uso).
- **TCO (Total Cost of Ownership):** Costo total de propiedad; suma de todos los gastos de un sistema en un período (CAPEX + OPEX + mantenimiento + actualizaciones)[*[6]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **IaaS/PaaS/SaaS:** Modelos de servicio en la nube donde IaaS (Infraestructura como Servicio) entrega recursos básicos (máquinas virtuales, almacenamiento), PaaS (Plataforma) ofrece entornos listos para desarrollar (bases de datos gestionadas, frameworks) y SaaS (Software) entrega aplicaciones completas por Internet.
- **Contenedor:** Entorno ligero y portátil que encapsula una aplicación y sus dependencias (por ejemplo, Docker), aislando procesos sobre un kernel compartido[*[34]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **Kubernetes:** Plataforma open source para **orquestar contenedores**. Automatiza el despliegue, escalado y administración de aplicaciones en contenedores[*[35]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **DevOps:** Metodología y cultura de desarrollo + operaciones orientada a entregar software continuamente mediante automatización y colaboración[*[36]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **Interoperabilidad:** Capacidad de sistemas o nubes diferentes para comunicarse e intercambiar datos usando estándares comunes[*[38]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **Portabilidad:** Facilidad para trasladar datos, aplicaciones o cargas de trabajo entre entornos de nube o entre nube y local, minimizando dependencias de proveedor[*[39]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21).
- **Región y Zona de Disponibilidad (AZ):** AWS organiza su infraestructura en **regiones** (localidades geográficas grandes) y cada región tiene varias **AZ** (centros de datos aislados). Desplegar en múltiples AZ mejora la disponibilidad.
- **Máquina virtual (EC2):** Servidor virtual en la nube que corre un sistema operativo completo. Se cobra por tiempo de uso.
- **Instancia Spot:** Tipo de pago a muy bajo costo para computación aprovechando capacidad no usada; AWS puede interrumpirla con 2 minutos de aviso.
- **Elasticidad:** Capacidad de escalar recursos (subir/bajar) dinámicamente según demanda.
- **Auto Scaling:** Servicio que ajusta automáticamente el número de instancias EC2 según métricas (uso CPU, tráfico, etc.).
- **ELB (Elastic Load Balancer):** Servicio que reparte tráfico de red entre múltiples instancias (mejorando escalabilidad y tolerancia a fallos)[*[20]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=Elastic%20Load%20Balancing%20distribuye%20autom%C3%A1ticamente,cambios%20en%20el%20tr%C3%A1fico%20entrante).
- **Route 53:** Servicio DNS de AWS para traducir dominios a IPs y balancear tráfico globalmente[*[21]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=,Gu%C3%ADa%20para%20desarrolladores%20de%20Amazon).
- **VPC (Virtual Private Cloud):** Red virtual aislada en AWS donde se despliegan recursos. Funciona como una red propia en la nube[*[17]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS).
- **Grupo de Seguridad:** Firewall virtual a nivel de instancia EC2; controla qué tráfico entra/sale de la instancia[*[19]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html#:~:text=Un%20grupo%20de%20seguridad%20controla,y%20salida%20de%20la%20instancia).
- **MFA (Autenticación Multifactor):** Seguridad adicional que exige, además de la contraseña, un código temporal (p.ej. de app móvil) para iniciar sesión[*[23]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=,un%20smartphone%20o%20una%20tablet).
- **Trusted Advisor:** Servicio que realiza comprobaciones automáticas de buenas prácticas (costos, rendimiento, seguridad) y sugiere mejoras[*[32]*](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html#:~:text=Trusted%20Advisor%20se%20basa%20en,cerrar%20las%20brechas%20de%20seguridad).
- **AWS Budgets / Cost Explorer:** Herramientas para gestionar costos: Budgets crea alertas de gasto[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n); Cost Explorer visualiza/análisis de uso pasado y predicciones[*[25]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html#:~:text=AWS%20Cost%20Explorer%20es%20una,usar%20para%20comprender%20los%20costos).
- **Snowball:** Dispositivo físico de AWS para migrar grandes volúmenes de datos a la nube (petabytes) de forma segura[*[26]*](https://aws.amazon.com/snowball/#:~:text=Simple%20migration).

**Referencias:** Documentación oficial de AWS y guías de estudio sobre conceptos de computación en la nube[*[1]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)[[29]](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=ya%20que%20AWS%20opera%2C%20administra,la%20legislaci%C3%B3n%20y%20los%20reglamentos)[[31]](https://aws.amazon.com/es/architecture/well-architected/#:~:text=AWS%20Well,ofrece%20un%20enfoque)[[15]](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20bajo%20demanda%20Las%20instancias,M%C3%A1s%20informaci%C3%B3n)[[24]](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n)[[25]](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html#:~:text=AWS%20Cost%20Explorer%20es%20una,usar%20para%20comprender%20los%20costos)[[27]](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=,el%20desempe%C3%B1o%20y%20la%20seguridad)[[17]](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS)[[20]](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=Elastic%20Load%20Balancing%20distribuye%20autom%C3%A1ticamente,cambios%20en%20el%20tr%C3%A1fico%20entrante)[[19]](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html#:~:text=Un%20grupo%20de%20seguridad%20controla,y%20salida%20de%20la%20instancia)[[32]](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html#:~:text=Trusted%20Advisor%20se%20basa%20en,cerrar%20las%20brechas%20de%20seguridad)[[5]](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21)*, así como recursos educativos proporcionados por AWS. Cada sección incluye enlaces a la documentación oficial para profundizar en los servicios relevantes.

[*[1]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[2]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[3]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[4]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[5]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[6]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[7]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[8]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[9]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[10]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[11]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[12]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[13]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[14]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[34]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[35]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[36]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[38]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[39]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) [*[40]*](https://www.notion.so/31c3bfd0fe87807f842cff674834a3c6?pvs=21) 8a3bbd3c-4915-4073-94b3-2317e55c5631_AWS.pdf

*file://file_00000000d5dc7243831be71815083ea1*

[*[15]*](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20bajo%20demanda%20Las%20instancias,M%C3%A1s%20informaci%C3%B3n) [*[16]*](https://aws.amazon.com/es/ec2/pricing/#:~:text=Instancias%20de%20spot%20Con%20las,M%C3%A1s%20informaci%C3%B3n) Amazon EC2 - Capacidad de computación segura y de tamaño ajustable - AWS

[*https://aws.amazon.com/es/ec2/pricing/*](https://aws.amazon.com/es/ec2/pricing/)

[*[17]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS) [*[18]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Con%20Amazon%20Virtual%20Private%20Cloud,la%20infraestructura%20escalable%20de%20AWS) [*[33]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html#:~:text=Puertas%20de%20enlace%20y%20puntos,de%20conexi%C3%B3n) ¿Qué es Amazon VPC? - Amazon Virtual Private Cloud

[*https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/what-is-amazon-vpc.html)

[*[19]*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html#:~:text=Un%20grupo%20de%20seguridad%20controla,y%20salida%20de%20la%20instancia) Controlar el tráfico hacia los recursos de AWS mediante grupos de seguridad - Amazon Virtual Private Cloud

[*https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html*](https://docs.aws.amazon.com/es_es/vpc/latest/userguide/vpc-security-groups.html)

[*[20]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=Elastic%20Load%20Balancing%20distribuye%20autom%C3%A1ticamente,cambios%20en%20el%20tr%C3%A1fico%20entrante) [*[21]*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html#:~:text=,Gu%C3%ADa%20para%20desarrolladores%20de%20Amazon) ¿Qué es Elastic Load Balancing? - Elastic Load Balancing

[*https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html*](https://docs.aws.amazon.com/es_es/elasticloadbalancing/latest/userguide/what-is-load-balancing.html)

[*[22]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=Un%20usuario%20de%20IAM%20es,de%20un%20nombre%20y%20credenciales) [*[23]*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html#:~:text=,un%20smartphone%20o%20una%20tablet) Usuarios de IAM - AWS Identity and Access Management

[*https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html*](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/id_users.html)

[*[24]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html#:~:text=,antes%20de%20la%20acumulaci%C3%B3n) Gestione sus costes con AWS presupuestos - AWS Gestión de costes

[*https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/budgets-managing-costs.html)

[*[25]*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html#:~:text=AWS%20Cost%20Explorer%20es%20una,usar%20para%20comprender%20los%20costos) Análisis de los costes y el uso con AWS Cost Explorer - AWS Gestión de costes

[*https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html*](https://docs.aws.amazon.com/es_es/cost-management/latest/userguide/ce-what-is.html)

[*[26]*](https://aws.amazon.com/snowball/#:~:text=Simple%20migration) AWS Snowball | Secure Edge Computing and Offline Data Transfer | Amazon Web Services

[*https://aws.amazon.com/snowball/*](https://aws.amazon.com/snowball/)

[*[27]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=,el%20desempe%C3%B1o%20y%20la%20seguridad) [*[28]*](https://aws.amazon.com/es/premiumsupport/plans/#:~:text=Tel%C3%A9fono%2C%20web%2C%20chat%20y%20correo,los%207%C2%A0d%C3%ADas%20de%20la%20semana) Comparación de planes de AWS Support — Características de AWS Support — AWS

[*https://aws.amazon.com/es/premiumsupport/plans/*](https://aws.amazon.com/es/premiumsupport/plans/)

[*[29]*](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=ya%20que%20AWS%20opera%2C%20administra,la%20legislaci%C3%B3n%20y%20los%20reglamentos) [*[30]*](https://aws.amazon.com/es/compliance/shared-responsibility-model/#:~:text=AWS%20tiene%20la%20responsabilidad%20de,en%20la%20nube%20de%20AWS) Modelo de responsabilidad compartida. Amazon Web Services (AWS)

[*https://aws.amazon.com/es/compliance/shared-responsibility-model/*](https://aws.amazon.com/es/compliance/shared-responsibility-model/)

[*[31]*](https://aws.amazon.com/es/architecture/well-architected/#:~:text=AWS%20Well,ofrece%20un%20enfoque) AWS Well-Architected: Desarrolle aplicaciones seguras y eficaces en la nube

[*https://aws.amazon.com/es/architecture/well-architected/*](https://aws.amazon.com/es/architecture/well-architected/)

[*[32]*](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html#:~:text=Trusted%20Advisor%20se%20basa%20en,cerrar%20las%20brechas%20de%20seguridad) AWS Trusted Advisor - AWS Support

[*https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html*](https://docs.aws.amazon.com/es_es/awssupport/latest/user/trusted-advisor.html)

[*[37]*](https://aws.amazon.com/es/cloudformation/#:~:text=AWS%20CloudFormation) Aprovisionamiento de infraestructura como código - AWS CloudFormation - AWS

[*https://aws.amazon.com/es/cloudformation/*](https://aws.amazon.com/es/cloudformation/)
