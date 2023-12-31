# Aprendendo a desenvolver um sistema de microsserviços do zero

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

:small_blue_diamond: [O que você aprenderá nesse projeto](#o-que-você-aprenderá-nesse-projeto)

:small_blue_diamond: [Funcionalidades do projeto](#funcionalidades-do-projeto)

:small_blue_diamond: [Pré-requisistos](#pré-requisitos)

:small_blue_diamond: [Clonando o projeto](#clonando-o-projeto)

:small_blue_diamond: [Criando o projeto com Spring Boot](#criando-o-projeto-com-spring-boot)

:small_blue_diamond: [Criando o projeto do servidor Eureka Server](#criando-o-projeto-do-servidor-eureka-server)

:small_blue_diamond: [Dependência Maven para o servidor Eureka Server](#dependência-maven-para-o-servidor-eureka-server)

:small_blue_diamond: [Editando extenção de arquivo para servidor Eureka Server](#editando-extenção-de-arquivo-para-servidor-eureka-server)

:small_blue_diamond: [Conteudo do arquivo de configuração do Eureka Server](#conteudo-do-arquivo-de-configuração-do-eureka-server)

:small_blue_diamond: [Adicionando a anotação EnableEurekaServer](#adicionando-a-anotação-enableeurekaserver)

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

O primeiro passo é criar o projeto com Spring Boot. Pode-se utilizar o serviço do <https://start.spring.io>, que fornece um projeto pronto para ser importado por uma IDE, ou pelo próprio Intellij caso tenha a versão Ultimate, além de uma classe main e arquivo pom.xml do Maven com as dependências.

## Criando o projeto do servidor Eureka Server

Para este exemplo, a dependência necessária será:
**Eureka Server Spring Cloud Discovery**
**spring-cloud-netflix Eureka Server**.

## Dependência Maven para o servidor Eureka Server

```
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
</dependency>
```

## Editando extenção de arquivo para servidor Eureka Server

Alterar a extenção do arquivo no Intellij de acordo como o caminho na hierarquia de pastas do projeto.

```
eureka-server>src>main>resources

Alterar de application.properties para application.yml
```

## Conteudo do arquivo de configuração do Eureka Server
```
eureka-server>src>main>resources>application.yml
```
```
spring:
  application:
    name: eureka-server
server:
  port: ${PORT:8761}
eureka:
  client:
    register-with-eureka: false
    fetch-registry: false
```

- **spring.application.name:**
Discovery Service (Serviço de Descoberta): Em ambientes de microsserviços, ao utilizar ferramentas como o Spring Cloud Netflix Eureka, essa propriedade é utilizada para registrar o serviço na descoberta de serviços. Isso ajuda na localização e comunicação entre diferentes microsserviços.
- **server.port:**
Especificar a Porta do Servidor com a definição manual da porta. Por padrão, o Spring Boot utiliza a porta 8080 para iniciar o servidor embutido Tomcat, mas através da propriedade server.port, você pode definir manualmente a porta na qual deseja que o servidor seja iniciado.
Por exemplo, server.port: 9090 faria a aplicação iniciar na porta 9090.
- **eureka.client.register-with-eureka:**
Essa propriedade tem a finalidade de configurar se um cliente (aplicativo) deve ou não se registrar automaticamente no servidor Eureka para permitir sua descoberta por outros serviços. Aqui está a explicação:
eureka.client.register-with-eureka:
Valor Padrão: Por padrão, essa propriedade é definida como true. Isso significa que, quando um aplicativo Spring Boot é configurado como cliente Eureka, ele se registrará automaticamente no servidor Eureka assim que iniciar.
Desabilitando o Registro Automático: Definir essa propriedade como false desabilita o registro automático do cliente no servidor Eureka. Isso pode ser útil em situações em que você deseja controlar manualmente o momento ou as condições em que o aplicativo é registrado no serviço de descoberta.
- **eureka.client.fetch-registry:**
Essa propriedade tem o propósito de controlar se um cliente (aplicativo) deve ou não buscar o registro de outros serviços no servidor Eureka para descoberta dinâmica de serviços disponíveis na rede.
Valor Padrão: Por padrão, essa propriedade é definida como true. Isso significa que, quando um aplicativo Spring Boot é configurado como cliente Eureka, ele automaticamente busca o registro de outros serviços no servidor Eureka ao iniciar.
Desabilitando a Busca Automática: Definir essa propriedade como false desativa a busca automática do registro de outros serviços no servidor Eureka. Isso pode ser útil em cenários onde o aplicativo não precisa consultar dinamicamente outros serviços registrados no Eureka ou quando você deseja controlar manualmente o comportamento de busca de registro.

## Adicionando a anotação EnableEurekaServer

Na classe no caminho correspondente, **eureka-server>src>main>java>com>microservice>eurekaservice>EurekaserverApplication.class**, acrescentar a seguinte anotação. **@EnableEurekaServer**

```
@SpringBootApplication
@EnableEurekaServer
public class EurekaServerApplication {
 public static void main(String[] args) {
  SpringApplication.run(EurekaServerApplication.class, args);
 }
}
```
