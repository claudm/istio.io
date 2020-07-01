---
title: O que é Istio?
description: Apresentação do Istio, os problemas que ele resolve, sua arquitetura de alto nível e seus objetivos de design.
weight: 10
aliases:
    - /pt-br/docs/concepts/what-is-istio/overview
    - /pt-br/docs/concepts/what-is-istio/goals
    - /pt-br/about/intro
test: n/a
---

As plataformas em nuvem oferecem muitos benefícios para as organizações que a usam. Contudo, não há como negar que a adoção da nuvem pode sobrecarregar as equipes de DevOps. Os desenvolvedores devem usar microsserviços para projetar a portabilidade, Enquanto isso, as operadoras estão gerenciando implantações híbridas e de múltiplas nuvens extremamente grandes.
O Istio permite conectar, proteger, controlar e observar serviços.

Em um nível alto, o Istio ajuda a reduzir a complexidade dessas implantações e diminui a pressão sobre suas equipes de desenvolvimento. É um código completamente aberto de service
mesh que coloca de forma transparente os aplicativos distribuídos existentes. É também uma plataforma, incluindo APIs que permitem a integração em qualquer plataforma de logs, ou
telemetria ou sistema de políticas. O conjunto de recursos diversos do Istio permite que você obtenha êxito, com eficiência, execute uma arquitetura de microsserviço distribuído e forneça uma
maneira uniforme de proteger, conectar e monitorar microsserviços.

## O que é um service mesh?

O Istio aborda os desafios que desenvolvedores e operadores enfrentam à medida que os aplicativos monolíticos passam para uma arquitetura de microsserviço distribuído. Para ver como,vamos te ajudar a dar uma olhada mais detalhada no service mesh Istio.

O termo service mesh é usado para descrever a rede de microsserviços que compõem esses aplicativos e as interações entre eles. À medida que o service mesh  cresce
 em tamanho e complexidade, pode se tornar mais difícil de entender e gerenciar. Seus requisitos podem incluir descoberta, balanceamento de carga, recuperação de falhas, métricas e
 monitoramento. O service mesh também costuma ter requisitos operacionais mais complexos, como testes A/B,política de deploy canary, limite de taxa, controle de acesso e
 autenticação de ponta a ponta.

O Istio fornece informações comportamentais e controle operacional sobre o service mesh como um todo, oferecendo uma solução completa para satisfazer os diversos requisitos de
 aplicativos de microsserviço.

## Por que usar o Istio?

O Istio facilita a criação de deploy em uma rede de serviços com balanceamento de carga, autenticação de service a service, monitoramento e muito mais, com [poucos](/pt-br/docs/tasks/observability/distributed-tracing/overview/#trace-context-propagation) ou nenhuma alteração de código
 de seu serviço. Você adiciona o suporte do Istio aos deploys de serviços um sidecar proxy  especial em todo o ambiente que intercepta todas as comunicações de rede
entre microsserviços, configura e gerencie o Istio usando suas funcionalidadee do plano de controle, que inclui:

* Balanceamento de carga automático para tráfego HTTP, gRPC, WebSocket e TCP.

* Controle refinado do comportamento do tráfego com regras de roteamento avançadas, novas tentativas, failovers e injeção de falhas.

* Uma camada de política conectável e API de configuração que suporta controles de acesso, limites de taxas e cotas.

* Métricas, logs e rastreamentos automáticos para todo o tráfego em um cluster, incluindo o cluster ingress e egress.

* Comunicação segura de services as services em um cluster com autenticação e autorização fortes baseadas em identidade.

O Istio foi projetado para extensibilidade e atende a diversas necessidades de deploy. Ele faz isso interceptando e configurando o tráfego de mesh, como mostrado no diagrama a seguir:

{{< image width="80%"
    link="/pt-br/docs/ops/deployment/architecture/arch.svg"
    alt="The overall architecture of an Istio-based application."
    caption="Istio Architecture"
    >}}

Referência [arquitetura](/pt-br/docs/ops/deployment/architecture/)para mais detalhes.

## Recursos principais

O Istio fornece vários recursos importantes de maneira uniforme em uma rede de
Serviços:

### Gerenciamento de tráfego

Istio’s easy rules configuration and traffic routing lets you control the flow of traffic and API calls between services. Istio simplifies configuration of
service-level properties like circuit breakers, timeouts, and retries, and makes it a breeze to set up important tasks like A/B testing, canary rollouts, and
staged rollouts with percentage-based traffic splits.

With better visibility into your traffic, and out-of-box failure recovery features, you can catch issues before they cause problems, making calls more reliable,
and your network more robust -- no matter what conditions you face.

Refer to the [Traffic management concepts guide](/pt-br/docs/concepts/traffic-management/) for more details.

### Security

Istio’s security capabilities free developers to focus on security at the application level. Istio provides the underlying secure communication channel, and
manages authentication, authorization, and encryption of service communication at scale. With Istio, service communications are secured by default,
letting you enforce policies consistently across diverse protocols and runtimes -- all with little or no application changes.

While Istio is platform independent, using it with Kubernetes (or infrastructure) network policies, the benefits are even greater, including the ability to
secure {{<gloss>}}pod{{</gloss>}}-to-pod or service-to-service communication at the network and application layers.

Refer to the [Security concepts guide](/pt-br/docs/concepts/security/) for more details.

### Observability

Istio’s robust tracing, monitoring, and logging features give you deep insights into your service mesh deployment. Gain a real understanding of how service performance
impacts things upstream and downstream with Istio’s monitoring features, while its custom dashboards provide visibility into the performance of all your
services and let you see how that performance is affecting your other processes.

All these features let you more effectively set, monitor, and enforce SLOs on services. Of course, the bottom line is that you can detect and fix issues quickly
and efficiently.

Refer to the [Observability concepts guide](/pt-br/docs/concepts/observability/) for more details.

## Platform support

Istio is platform-independent and designed to run in a variety of environments, including those spanning Cloud, on-premise, Kubernetes, Mesos, and more. You can
 deploy Istio on Kubernetes, or on Nomad with Consul. Istio currently supports:

* Deploy  de serviço no Kubernetes

* Serviços registrados no Consul

* Serviços em execução em máquinas virtuais individuais

## Integração e customização

The policy enforcement component of Istio can be extended and customized to integrate with existing solutions for ACLs, logging, monitoring, quotas, auditing,
and more.
