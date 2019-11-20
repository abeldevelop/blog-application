Blog Backend Microservices
======
Este repositorio no tiene ningun tipo de codigo, simplemente es la documentación de todas las partes de la aplicación y arquitectura necesaria para crearla con [Spring Boot](https://spring.io/projects/spring-boot) y [Maven](https://maven.apache.org/) en la parte backend y [Angular](https://angular.io/) en el frontend (*La parte de Angular se realizara despues finalizar la parte backend*)

### Table of Contents
**[Maven Parent POMs](#maven-parent-poms)**<br>
**[maven-archetypes](#maven-archetypes)**<br>
**[Starters](#starters)**<br>
**[Compilation and Excecution order](#compilation-and-excecution-order)**<br>
**[Liraries Repositories](#liraries-repositories)**<br>
**[Servers Repositories](#servers-repositories)**<br>
**[Services Repositories](#services-repositories)**<br>
**[Services Structure and modules](#services-structure-and-modules)**<br>
**[Data Base Models](#data-base-models)**<br>
**[Pending to Analize](#pending-to-analize)**<br>


Maven Parent POMs
======
Para simplificar la gestión de las dependencias  ha creado un parent POM
* **[Abeldevelop parent POM](https://github.com/abeldevelop/parent-pom/tree/develop/abeldevelop-parent-pom)**

Maven Archetypes
======
Para simplificar la creacion de nuevos servicios y librerias se han creado arquetipos maven
* **Abeldevelop Service Archetype** => TODO
* **Abeldevelop Library Archetype** => TODO

Starters
======
Debido a que cada modulo tendra muchas dependencias comunes se ha decidido crear starters
* **[Abeldevelop Api Starter](https://github.com/abeldevelop/starters/tree/develop/api-starter)**
* **[Abeldevelop Client Starter](https://github.com/abeldevelop/starters/tree/develop/client-starter)**
* **[Abeldevelop Dto Starter](https://github.com/abeldevelop/starters/tree/develop/dto-starter)**
* **[Abeldevelop Model Starter](https://github.com/abeldevelop/starters/tree/develop/model-starter)**
* **[Abeldevelop Repository Starter](https://github.com/abeldevelop/starters/tree/develop/repository-starter)**
* **[Abeldevelop Service Starter](https://github.com/abeldevelop/starters/tree/develop/service-starter)**
* **[Abeldevelop Test Starter](https://github.com/abeldevelop/starters/tree/develop/test-starter)**


Compilation and Excecution order
======

Lo primero de todo que se debe compilar es [Abeldevelop parent POM](https://github.com/abeldevelop/parent-pom/tree/develop/abeldevelop-parent-pom)

Liraries compilation order
------
* context-library
* exception-library
* common-library

Starters compilation order
------
* No importa el orden

Servers execution order
------
* discovery-server

Services execution order
------
* No importa el orden de arranque. Solo necesita el **config-server** arrancado

Liraries repositories
======

| Library | Repository |
| ------ | ------ |
| logging-library | TODO |
| propertie-library | TODO |
| pagination-library | TODO |
| annotation-library | TODO |
| aspect-library | TODO |
| context-library | [Github Repository](https://github.com/abeldevelop/context-library) |
| exception-library | [Github Repository](https://github.com/abeldevelop/exception-library) |
| security-library | TODO |
| common-library | [Github Repository](https://github.com/abeldevelop/common-library) |
| test-library | TODO |

 
Servers repositories
======

| Server | Port | Repository |
| ------ | ------ | ------ |
| discovery-server | 8761 | TODO |
| gateway-server | 9000 | TODO |
| config-server | 8888 | TODO |
| hystrix-server | 0000 | TODO |
| security-server | 0000 | TODO |
| zipkin-server | 9411 | TODO |
| admin-server | 0000 | TODO |
| management-server | 8610 | TODO |
| parameterization-server | 8620 | TODO |

Services repositories
======
| Service | Port | repository |
| ------ | ------ | ------ |
| blog-categories-service | 8210 | [Github Repository](https://github.com/abeldevelop/blog-categories-service) |
| blog-subcategories-service | 8220 | TODO |
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
* 

Pending to Analize
======
* Front end para unificar contratos por aplicacion
* MS para dar de alta los contratos por aplicacion
* En el starter de los servicios registrar en BBDD al levantarse la version del MS y del parent pom
* Diseñar el modelo de datos para el menu
* ¿Como cambiar en caliente los datos de autenticación y los permisos?