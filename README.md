# Aprendendo a desenvolver um sistema de microsserviços do zero.

<p align="center">
<img src="https://img.shields.io/static/v1?label=java&message=Programming%20languages&color=red&style=for-the-badge&logo=JAVA"/>
<img src="https://img.shields.io/static/v1?label=spring%20boot&message=Framework&color=green&style=for-the-badge&logo=SPRING%20BOOT"/>
<img src="https://img.shields.io/static/v1?label=maven&message=Apache%20Maven%20Project&color=pink&style=for-the-badge&logo=MAVEN"/>
<img src="http://img.shields.io/static/v1?label=License&message=MIT&color=green&style=for-the-badge&logo=LICENSE"/>
<img src="http://img.shields.io/static/v1?label=STATUS&message=EM andamento&color=purple&style=for-the-badge&logo=FINALIZADO"/>
 </p>
 
<!-- > Status do Projeto: :heavy_check_mark: :warning: (Finalizado) -->
> Status do Projeto: :warning: (Em andamento) 
### Tópicos
:small_blue_diamond: [Links Úteis](#links-úteis)

:small_blue_diamond: [Descrição do projeto](#descrição-do-projeto)

:small_blue_diamond: [Funcionalidades do projeto](#funcionalidades-do-projeto)

:small_blue_diamond: [Pré-requisistos](#descrição-do-projeto)

:small_blue_diamond: [Clonando o projeto](#clonando-o-projeto)

:small_blue_diamond: [Criando o projeto com Spring Boot](#criando-o-projeto-com-spring-boot)

...

## Links Úteis

Para completar o desenvolvimento do projeto tutorial será necessário as seguintes ferramentas:

- [Java JDK (v8+)](https://www.oracle.com/technetwork/java/javase/downloads/index.html)
- [Maven (v3+)](https://maven.apache.org/download.cgi)
- [Postman](https://www.getpostman.com)
- [Spring Initializer](https://start.spring.io/)
- [Intellij](https://www.jetbrains.com/idea/download/?section=linux)

...

## Descrição do projeto

#### O que você aprenderá nesse projeto

- Instalar e configurar as ferramentas corretas para iniciar um projeto baseado em microsserviços do zero
- Conceitos de Spring Boot 2.x.x
- Spring Data JPA
- Spring Cloud
- Docker
- Docker compose
- Criar suas imagens Docker
- Registrar suas imagens em um docker registry
- Versionamento de código com Git e Github
- OpenFeign
- Eureka Server
- API Gateway
- Hibernate
- Criar uma API RESTful
- Consumir uma API REST usando a ferramenta
- Insomnia
- Utilização do banco de dados h2 em tempo de compilação
- Tratamento de exceções de forma personalizada
- Desenvolvimento em camadas
- Protocolo HTTP no padrão REST

Nesse projeto será demonstrado como desenvolver um sistema de microsserviços com API RESTFUL para um CRUD (Create, Read, Update e Delete - em português Criar, Ler, Atualizar e Remover) utilizando **Spring Boot**, **Spring Data JPA**, **Spring Cloud**, **Docker**, **Docker Compose**, **OpenFeign**, **API Gateway**, **Lombok**, **H2**, **Eureka-Server**, **Eureka-Client**.

...

## Funcionalidades do projeto

Será criado um sistema de microsserviços com servidor com **Eureka-server**

...

## Pré-requisitos

- :warning: Conhecimentos Progrmação Orientada a Objetos - POO.
- :warning: Conhecimentos de Programação Java.
- :warning: Conhecimentos de Hibernate.
- :warning: Conhecimentos de JPA.
- :warning: Conhecimentos de Banco de Dados.
- :warning: Conhecimentos de API.

...

## Clonando o projeto

```
git clone git@github.com:KleilsonSantos/microservices-system.git
```
...


## Criando o projeto com Spring Boot

O primeiro passo é criar o projeto com Spring Boot. Pode-se utilizar o serviço do https://start.spring.io, que fornece um projeto pronto para ser importado por uma IDE, ou pelo próprio Intellij caso tenha a versão Ultimate, além de uma classe main e arquivo pom.xml do Maven com as dependências. 

