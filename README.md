Blog Backend Microservices
======
Este repositorio no tiene ningun tipo de codigo, simplemente es la documentación de todas las partes de la aplicación y arquitectura necesaria para crearla con [Spring Boot](https://spring.io/projects/spring-boot) y [Maven](https://maven.apache.org/) en la parte backend y [Angular](https://angular.io/) en el frontend (*La parte de Angular se realizara despues finalizar la parte backend*)

### Table of Contents
**[Abeldevelop Parent POM](#abeldevelop-parent-pom)**<br>
**[Abeldevelop Maven Archetype](#abeldevelop-maven-archetype)**<br>
**[Starters](#starters)**<br>
**[Compilation and Excecution order](#compilation-and-excecution-order)**<br>
**[Libraries Repositories](#libraries-repositories)**<br>
**[Servers Repositories](#servers-repositories)**<br>
**[Services Repositories](#services-repositories)**<br>
**[Services Structure and modules](#services-structure-and-modules)**<br>
**[Data Base Models](#data-base-models)**<br>
**[Pending to Analize](#pending-to-analize)**<br>

Abeldevelop Architecture Repositories Resumen
======
* **[Abeldevelop parent POM](https://github.com/abeldevelop/abeldevelop-parent-pom)** => Parent pom con la gestion de las versiones de las dependencias
* **[Abeldevelop Config Repository](https://github.com/abeldevelop/abeldevelop-config-repository)** => Repositorio con la configuracion de las properties
* **[Abeldevelop Libraries](https://github.com/abeldevelop/abeldevelop-libraries)** => Librerias de la arquitectura
* **[Abeldevelop Servers](https://github.com/abeldevelop/abeldevelop-servers)** => Servidores (discovery, gateway, config, etc..)
* **[Abeldevelop Starters](https://github.com/abeldevelop/abeldevelop-starters)** => Starters para simplificar y automatizas las dependencias los servicios

Blog Repositories Resumen
======
* **[Abeldevelop parent POM](https://github.com/abeldevelop/blog-categories-service)**

Abeldevelop Parent POM
======
Para simplificar la gestión de las dependencias  ha creado un parent POM
* **[Abeldevelop parent POM](https://github.com/abeldevelop/abeldevelop-parent-pom)**

Abeldevelop Maven Archetype
======
Para simplificar la creacion de nuevos servicios se ha creado un arquetipo maven
* **[Abeldevelop Maven Archetype](https://github.com/abeldevelop/abeldevelop-maven-archetype)**


Starters
======
Debido a que cada modulo de los servicios tendra muchas dependencias comunes se ha decidido crear starters, para simplificar las dependencias en los servicios
* **[Abeldevelop Api Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/api-starter)**
* **[Abeldevelop Client Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/client-starter)**
* **[Abeldevelop Dto Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/dto-starter)**
* **[Abeldevelop Model Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/model-starter)**
* **[Abeldevelop Repository Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/repository-starter)**
* **[Abeldevelop Service Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/service-starter)**
* **[Abeldevelop Test Starter](https://github.com/abeldevelop/abeldevelop-starters/tree/develop/test-starter)**


Compilation and Excecution order
======
Como cada parte (starters, libraries, servers y cada service) tiene su propio parent pom. Se simplifica la compilacion
* **[Abeldevelop parent POM](https://github.com/abeldevelop/abeldevelop-parent-pom)**
* **[Abeldevelop Libraries](https://github.com/abeldevelop/abeldevelop-libraries)**
* **[Abeldevelop Starters](https://github.com/abeldevelop/abeldevelop-starters)**
* **[Abeldevelop Api Servers](https://github.com/abeldevelop/abeldevelop-servers)**

Servers deployment order
------
* config-server
* discovery-server


Services execution order
------
* No importa el orden de arranque. Solo necesita que esten todos los **servers** arrancados

Libraries repositories
======

| Library | Description | Repository |
| ------ | ------ | ------ |
| logging-library | Configuracion del logback para los logs | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/logging-library) |
| propertie-library | Contiene properties generales. bootstrap.properties | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/property-library) |
| pagination-library | Mappers y objetos de paginacion | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/pagination-library) |
| annotation-library | Anotaciones propias de la arquitectura | TODO |
| aspect-library | Aspectos de la arquitectura | TODO |
| context-library | Beans the spring generales | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/context-library) |
| exception-library | Excepciones generales y Handler | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/exception-library) |
| security-library | | TODO |
| common-library | Clases e interfaces comunes | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/common-library) |
| test-library | Configuracion para test con Cucumber | [Github Repository](https://github.com/abeldevelop/abeldevelop-libraries/tree/develop/test-library) |

 
Servers repositories
======

| Server | Port | Repository |
| ------ | ------ | ------ |
| discovery-server | 8761 | [Github Repository](https://github.com/abeldevelop/abeldevelop-servers/tree/develop/discovery-server) |
| gateway-server | 9000 | [Github Repository](https://github.com/abeldevelop/abeldevelop-servers/tree/develop/gateway-server) |
| config-server | 8888 | [Github Repository](https://github.com/abeldevelop/abeldevelop-servers/tree/develop/config-server) |
| hystrix-server | 0000 | TODO |
| security-server | 0000 | TODO |
| zipkin-server | 9411 | TODO |
| admin-server | 0000 | TODO |
| management-server | 8610 | TODO |
| parameterization-server | 8620 | TODO |
| text-server | 8630 | TODO |

Services repositories
======
| Service | Port | repository |
| ------ | ------ | ------ |
| blog-categories-service | 8210 | [Github Repository](https://github.com/abeldevelop/blog-categories-service) |
| blog-subcategories-service | 8220 | [Github Repository](https://github.com/abeldevelop/blog-subcategories-service) |
| blog-posts-service | 8230 | TODO |
| blog-comments-service | 8240 | TODO |
| blog-service | 8250 | TODO |
| users-service | 8260 | TODO |

Services Structure and modules
======
Todos los servicios tienen en la raiz del respositorio un proyecto parent pom de maven, dentro de este se encuentra los siguientes modulos
* blog-_serviceName_-api        => Interfaz con la definicion del contrato con las anotaciones Swagger
* blog-_serviceName_-client     => Clientes Feign para conectarse con el microservicio
* blog-_serviceName_-domain     => Objetos de dominion del microservicio
* blog-_serviceName_-dto        => DTOs de entrada y salida para el microservicio con las anotaciones Swagger
* blog-_serviceName_-model      => Modelo de la base de datos con las anotaciones JPA
* blog-_serviceName_-repository => Repositorio de acceso a datos con Spring Data y Query DSL
* blog-_serviceName_-service    => Microservicio con Spring Boot

Packages module blog-_serviceName_-api
------
* com.abeldevelop.blog.category.api => Interfaz para contrato de la API con anotaciones Swagger

Packages Module blog-_serviceName_-client
------
* com.abeldevelop.blog.category.client => Interfaz con anotaciones Feign para los clientes de la API

Packages Module blog-_serviceName_-domain
------
* com.abeldevelop.blog.category.domain => Objetos de dominio del microservicio

Packages Module blog-_serviceName_-dto
------
* com.abeldevelop.blog.category.dto   => DTOs de entrada y salida para el microservicio con las anotaciones Swagger

Packages Module blog-_serviceName_-model
------
* com.abeldevelop.blog.category.model => Modelo de la base de datos con las anotaciones JPA


Packages Module blog-_serviceName_-repository
------
* com.abeldevelop.blog.category.repository            => Interfaz con acceso a base de datos
* com.abeldevelop.blog.category.repository.predicate  => Predicados con Query DSL
* com.abeldevelop.blog.category.repository.springdata => Interfaz de repositorio de spring data



Packages Module blog-_serviceName_-service
------
* com.abeldevelop.blog.category.service.component   => Beans gestionados por Spring que no se corresponden con logica de negocio
* com.abeldevelop.blog.category.service.config      => Configuracion del microservicio
* com.abeldevelop.blog.category.service.controller  => Controlador del microservicio
* com.abeldevelop.blog.category.service.domain      => Objetos de dominio
* com.abeldevelop.blog.category.service.exception   => Excepciones propias del microservicio
* com.abeldevelop.blog.category.service.mapper      => Mapeo entre objetos con MapStruct
* com.abeldevelop.blog.category.service.service     => Beans de Spring con logica de negocio
* com.abeldevelop.blog.category.service.util        => Clases de utilidades/constantes
* com.abeldevelop.blog.category.service.validation  => Objetos de validacion de los datos de entrada al microservicio


Data Base Models
======

Contracts
------
Table contracts (Pending schema)
* id
* aplication
* service
* URL
* enabled

Management
------
Table services_versions (Pending schema)
* id
* service
* service_version
* parent_pom_version

Pending to Develop
======
* Handler the exceptions of spring data JpaSystemException and not showing the real message
* Cucumber add extra headers
* Cucumber read request from json in classpath
* Cucumber validate response with json classpath

Pending to Analize
======
* Front end para unificar contratos por aplicacion
* MS para dar de alta los contratos por aplicacion
* En el starter de los servicios registrar en BBDD al levantarse la version del MS y del parent pom
* Diseñar el modelo de datos para el menu
* ¿Como cambiar en caliente los datos de autenticación y los permisos?