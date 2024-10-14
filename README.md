# EnterpriseServices-Atacks

### HTTP (*Hypertext Transfer Protocol*) y HTTPS (*Hypertext Transfer Protocol Secure*)

**HTTP** (Protocolo de Transferencia de Hipertexto) es el protocolo estándar utilizado para la comunicación en la web. A través de HTTP, los navegadores solicitan páginas web y los servidores responden enviando el contenido solicitado. Sin embargo, HTTP es inherentemente **inseguro**, ya que los datos se transmiten en texto plano.

**HTTPS** (HTTP Seguro) mejora esta situación al añadir una capa de cifrado utilizando el protocolo SSL/TLS, lo que garantiza la confidencialidad, integridad y autenticidad de los datos. Esto protege contra ataques como el espionaje (eavesdropping) y la manipulación de datos, asegurando que la comunicación entre el usuario y el servidor esté cifrada.

### **Exploits HTTP**

#### **Malicious iFrames**

Un **iFrame** es un elemento HTML que permite incrustar contenido de otra página web dentro de una página principal. Aunque es una herramienta útil, también puede ser explotada por atacantes para cargar contenido malicioso.

**Proceso:**

- Un atacante inserta un **iFrame malicioso** en una página web legítima, que puede estar oculto para los usuarios.
- Este iFrame redirige a los usuarios a sitios web maliciosos o carga contenido malicioso, como exploits o malware, sin que la víctima se dé cuenta.
- Se usan en campañas de distribución de malware o para realizar ataques de tipo **drive-by download**, donde el simple hecho de visitar una página infectada puede infectar al dispositivo.

*Los usuarios pueden ser redirigidos a sitios de phishing o infectados con malware sin interacción directa.*

#### **HTTP 302 Cushioning**

El **HTTP 302 Cushioning** es un tipo de ataque que explota la redirección HTTP (código 302), utilizada normalmente para redirigir temporalmente a los usuarios a otra URL.

**Proceso:**

- El atacante compromete un sitio web o una parte de la red.
- Mediante la manipulación de las respuestas 302 (redirección), el atacante redirige a los usuarios a páginas maliciosas intercaladas entre redirecciones legítimas.

*Los usuarios pueden ser redirigidos a páginas maliciosas o fraudulentas sin notarlo, permitiendo a los atacantes lanzar ataques de phishing o infectar al usuario con malware.*

------

### **Vulnerabilidades y exploits relacionados con HTTPS**

 **HTTPS** no está exento de vulnerabilidades o exploits y estos pueden ser aprovechados por atacantes en ciertas circunstancias. Los mas comunes son

#### **Certificados SSL falsificados o comprometidos**

Los certificados SSL/TLS son la base de la autenticación HTTPS. Sin embargo, si un atacante logra obtener un certificado SSL falso o comprometer una autoridad certificadora (CA), puede realizar ataques como **suplantación de sitios** o **ataques Man-in-the-Middle (MITM)**.

- **Ataques a CA**: Si un atacante compromete una CA de confianza, puede emitir certificados falsos para dominios legítimos.
- **Certificados autofirmados**: Algunos sitios utilizan certificados autofirmados (sin una autoridad certificadora confiable), lo que puede ser explotado por los atacantes para hacer pasar sus sitios maliciosos como seguros.

*Los usuarios pueden ser engañados para creer que están accediendo a sitios legítimos, cuando en realidad están en sitios falsos o maliciosos.*

#### **Ataques de downgrade (SSL Stripping)**

El **SSL Stripping** es un ataque en el que un atacante degrada la conexión HTTPS segura a HTTP sin cifrar.

**Proceso:**

- Un atacante intercepta la solicitud de conexión HTTPS y la convierte en una conexión HTTP insegura.
- El usuario cree que está en una conexión segura, pero en realidad la transmisión de datos no está cifrada y el atacante puede interceptar o modificar la información.

*El atacante puede capturar datos sensibles (como credenciales) o inyectar contenido malicioso en una conexión que parece segura pero en realidad no lo es.*

#### **Debilidades en algoritmos de cifrado y versiones antiguas de TLS**

A lo largo de los años, algunos algoritmos y versiones de SSL/TLS han demostrado ser inseguros o débiles. Versiones antiguas de SSL (como SSLv2 y SSLv3) y algunos cifrados como **RC4** ya no son seguros y deben evitarse.

- **BEAST, POODLE, Heartbleed**: Son vulnerabilidades que han explotado debilidades en la implementación de SSL/TLS.
- **Cifrado débil**: El uso de cifrados débiles o incorrectos puede ser vulnerado por atacantes para interceptar o manipular comunicaciones.

*Incluso si se utiliza HTTPS, un cifrado débil o una versión antigua de TLS puede ser comprometida, permitiendo a los atacantes leer o alterar la información transmitida.*