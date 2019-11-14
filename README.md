Blog Backend Microservices
======
Este repositorio no tiene ningun tipo de codigo, simplemente es la documentación de todas las partes de la aplicación y arquitectura necesaria para crearla con [Spring Boot](https://spring.io/projects/spring-boot) y [Maven](https://maven.apache.org/) en la parte backend y [Angular](https://angular.io/) en el frontend (*La parte de Angular se realizara despues finalizar la parte backend*)

### Table of Contents
**[Maven Parent POMs](#maven-parent-poms)**<br>
**[maven-archetypes](#maven-archetypes)**<br>
**[Compilation and Excecution order](#compilation-and-excecution-order)**<br>
**[Liraries Repositories](#liraries-repositories)**<br>
**[Servers Repositories](#servers-repositories)**<br>
**[Services Repositories](#services-repositories)**<br>

Maven Parent POMs
======
Para simplificar la creacion de nuevos servicios y librerias se ha creado parents POM
* **[Architecture parent POM](https://github.com/abeldevelop/parent-pom/tree/develop/architecture-parent-pom)**
* **[Services Parent POM](https://github.com/abeldevelop/parent-pom/tree/develop/services-parent-pom)**

Maven Archetypes
======
Para simplificar la creacion de nuevos servicios y librerias se ha creado arquetipos maven
* **Service Archetype** => TODO
* **Library Archetype** => TODO

Compilation and Excecution order
======

Liraries compilation order
------
* 

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
| properties-library | TODO |
| aspects-library | TODO |
| context-library | TODO |
| exception-library | TODO |
| security-library | TODO |
| common-library | TODO |
| test-library | TODO |

 
Servers repositories
======

| Server | Repository |
| ------ | ------ |
| discovery-server | TODO |
| gateway-server | TODO |
| config-server | TODO |
| hystrix-server | TODO |
| security-server | TODO |
| zipkin-server | TODO |
| discovery-server | TODO |
| admin-server | TODO |

Services repositories
======
| Service | repository |
| ------ | ------ |
| blog-categories-service | [Github Repository](https://github.com/abeldevelop/blog-categories-service) |
| blog-subcategories-service | TODO |
| blog-posts-service | TODO |
| blog-comments-service | TODO |
| blog-service | TODO |
| users-service | TODO |