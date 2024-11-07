## Spring Security JWT Application

### 📄 Descripción del proyecto:

Este proyecto es una aplicación Spring Boot que implementa un sistema de autenticación y autorización de usuarios mediante Spring Security y JWT (JSON Web Tokens). Proporciona controladores para manejar endpoints asegurados, autenticación basada en roles y persistencia en una base de datos MySQL.

### 🛠️ Herramientas utilizadas:

- Java 17: Lenguaje de programación.
- Spring Boot: Framework principal para el desarrollo de aplicaciones.
- spring-boot-starter-security: Implementa seguridad en la aplicación.
- spring-boot-starter-data-jpa: Persistencia de datos con JPA y Hibernate.
- spring-boot-starter-web: Creación de la API REST.
- JWT: JSON Web Tokens para autenticación sin estado.
- MySQL: Base de datos relacional.
- Lombok: Anotaciones para reducir el código repetitivo.

### ⚙️ Configuración inicial

#### 🗄️ Base de datos:

Este proyecto utiliza MySQL como base de datos. La configuración de la conexión se encuentra en el archivo application.properties, donde se deben proporcionar las credenciales de acceso y el nombre de la base de datos.

#### 🔧 Configuración del entorno:

Para clonar y ejecutar este proyecto, debes configurar el archivo application.properties con las credenciales de tu base de datos MySQL y las variables para JWT:

#### 💾 Datos de conexión a la base de datos
- spring.datasource.url=jdbc:mysql://localhost:3306/tu_basededatos
- spring.datasource.username=root
- spring.datasource.password=tu_contraseña
- spring.datasource.driverClassName=com.mysql.cj.jdbc.Driver
- spring.jpa.database-platform=org.hibernate.dialect.MySQL8Dialect
- spring.jpa.show-sql=true
- spring.jpa.hibernate.ddl-auto=create

Asegúrate de reemplazar tu_basededatos, root, y tu_contraseña con los valores correspondientes a tu entorno.

#### 🔑 Configuración de JWT

También en application.properties, proporciona la clave secreta para la firma de los tokens JWT y el tiempo de expiración en milisegundos:

- jwt.secret.key=claveSecretaEnBase64
- jwt.time.expiration=86400000  # Tiempo en milisegundos (por ejemplo, 1 día)

Asegúrate de codificar tu clave secreta en Base64 antes de usarla.

### 🚀 Ejecución del proyecto

Sigue estos pasos para ejecutar el proyecto:

1. Clonar el repositorio
2. Configura el archivo application.properties con tus credenciales de MySQL y los valores de JWT.
3. Ejecutar el proyecto usando Maven con el siguiente comando:

- mvn spring-boot:run

### 📝 Documentación de la API

Para probar los endpoints y autenticar usuarios mediante tokens JWT, puedes usar herramientas como Postman. A continuación, algunos endpoints principales:

- GET /hello: Endpoint público.
- GET /helloSecured: Endpoint protegido.
- POST /createUser: Crea un nuevo usuario.

##### Endpoints según roles:

- GET /accessAdmin: Acceso para usuarios con rol ADMIN.
- GET /accessUser: Acceso para usuarios con rol USER.
- GET /accessInvited: Acceso para usuarios con rol INVITED.

### 📌 Notas adicionales

- La opción spring.jpa.hibernate.ddl-auto=create en el archivo application.properties crea automáticamente las tablas en la base de datos al iniciar la aplicación.
- Asegúrate de configurar correctamente el archivo application.properties antes de ejecutar el proyecto.