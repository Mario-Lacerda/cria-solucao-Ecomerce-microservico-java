# Criando uma Solução de E-commerce com Microsserviços em Java
Neste projeto prático iremos desenvolver uma solução de e-commerce com a arquitetura de microsserviços e aplicar a integração entre eles orientada a eventos com Apache Kafka e garantir a compatibilidade entre da comunicação dos microsserviços com Schema Registry. Para isso, programaremos em Java utilizando a stack do Spring (Spring Boot, Spring Cloud Streams).

## Detalhes da aula
- Definição dos domínios

- Definição da arquitetura
      - checkout Front End realizado com HTML (layout pronto do Spring Boot)
          - checkout Api recebe todos os dados digitados no front end
          - payament Api recebe dados da checkout api e processa o pagamento
          - checkout Api recebe retorno da payament Api e devolve o resultado para usuário no Front End
          - KAFTA trata dados em forma de Streaming Data e utilizando Schema Registry
- Spring utilizado com as opções: Boot, Cloud stream, Sleuth e Web    
- Banco de dados Postgres definido para Manter dados das Apis (ver em docker-compose.yml)

# Dependências
- org.springframework.boot:spring-boot-starter-web
- org.springframework.cloud:spring-cloud-starter-sleuth
- org.springframework.cloud:spring-cloud-starter-stream-kafka
- io.confluent:kafka-avro-serializer:5.5.0
- org.projectlombok:lombok



## **Criando uma Solução de E-commerce com Microsserviços em Java**

Neste tutorial, você aprenderá a criar uma solução de e-commerce com microsserviços em Java. Você irá aprender sobre os conceitos de microsserviços, como criar microsserviços com Spring Boot, como integrar microsserviços com Kafka e como publicar e consumir eventos com Spring Cloud Stream.

### **Conceitos de Microsserviços**

Os microsserviços são uma arquitetura de software que divide um sistema em vários serviços menores e independentes. Cada serviço é responsável por uma única tarefa ou função, e os serviços são comunicados entre si usando APIs.

Os microsserviços têm várias vantagens sobre a arquitetura de software monolítica, incluindo:

- **Escalabilidade:** Os microsserviços podem ser escalados de forma independente, o que significa que você pode adicionar ou remover serviços conforme necessário para atender à demanda.
- **Resiliência:** Se um serviço falhar, os outros serviços não serão afetados. Isso torna os microsserviços mais resilientes a falhas de hardware ou software.
- **Facilidade de manutenção:** Os microsserviços são mais fáceis de manter do que os sistemas monolíticos, pois cada serviço é independente.

## **Criando Microsserviços com Spring Boot**

Spring Boot é um framework de desenvolvimento de aplicações Java que facilita a criação de microsserviços. Spring Boot fornece uma série de recursos que ajudam a simplificar o desenvolvimento de microsserviços, incluindo:

- **Autoconfiguração:** Spring Boot configura automaticamente muitos aspectos de sua aplicação, como dependências, propriedades e servidores de aplicativos.
- **Inicialização rápida:** Spring Boot permite que você inicie seus microsserviços rapidamente, sem a necessidade de escrever código de inicialização complexo.
- **Produção pronta:** Spring Boot fornece uma série de recursos que são úteis em ambientes de produção, como gerenciamento de logs, monitoramento e gerenciamento de memória.

### **Integrando Microsserviços com Kafka**

Kafka é um serviço de mensageria distribuído que pode ser usado para enviar e receber eventos entre microsserviços. Kafka é uma ótima escolha para microsserviços porque é altamente escalável, tolerante a falhas e fácil de usar.

Para integrar microsserviços com Kafka, você pode usar Spring Cloud Stream. Spring Cloud Stream é uma biblioteca que fornece uma API de alto nível para enviar e receber eventos com Kafka.

### **Publicando e Consumindo Eventos com Spring Cloud Stream**

Para publicar um evento com Spring Cloud Stream, você pode usar o método `send()` da classe `OutputChannel`. Por exemplo, o seguinte código publica um evento chamado `product-created` no tópico `product-events`:

java

```java
outputChannel.send(new ProductCreatedEvent(productId, productName));
```

Para consumir um evento com Spring Cloud Stream, você pode usar o método `receive()` da classe `InputChannel`. Por exemplo, o seguinte código consome eventos do tópico `product-events` e imprime o nome do produto em um console:

java

```java
while (true) {
    ProductCreatedEvent event = inputChannel.receive();
    if (event != null) {
        System.out.println(event.getProductName());
    }
}
```

### **Conclusão**

Neste projeto, desenvolvemos uma solução de e-commerce com microsserviços em Java, utilizando Kafka para comunicação orientada a eventos e Schema Registry para garantir a compatibilidade. Ao seguir as melhores práticas de estruturação, documentação, definição de modelos, integração e teste, criamos uma solução robusta e escalável.   Criar uma solução de e-commerce com microsserviços em Java. Você aprendeu sobre os conceitos dele, como criar os mesmos com Spring Boot, como integrá-los com Kafka e como publicar e consumir eventos com Spring Cloud Stream.



### **Aplicabilidade Prática**

Esta solução pode ser aplicada em vários cenários do mundo real, como:

- Lojas de e-commerce que desejam escalar seus sistemas.
- Sistemas de processamento de pedidos que precisam lidar com grandes volumes de dados.
- Sistemas financeiros que exigem processamento de pagamentos em tempo real.



