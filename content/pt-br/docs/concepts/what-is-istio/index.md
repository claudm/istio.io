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

Referência da [arquitetura ](/pt-br/docs/ops/deployment/architecture/)para mais detalhes.

## Recursos principais

O Istio fornece vários recursos importantes de maneira uniforme em uma rede de
Serviços:

### Gerenciamento de tráfego

A configuração fácil de regras e o roteamento de tráfego do Istio permitem controlar o fluxo de tráfego e chamadas de API entre serviços. O Istio simplifica a configuração de
propriedades de nível de serviço como circuit breakers, timeouts, e retries, e facilita a configuração de tarefas importantes, como testes A/B, rollouts canary, e
rollouts em etapas com divisões de tráfego com base em porcentagem.

Com melhor visibilidade do seu tráfego, recursos de recuperação de falhas prontos para uso, é possível detectar problemas antes que eles causem problemas, tornando as chamadas mais confiáveis,
e sua rede mais robusta - independentemente das condições que você enfrenta.

Consulte o[Guia de conceitos de gerenciamento de tráfego ](/pt-br/docs/concepts/traffic-management/) para mais detalhes.
### Segurança

Os recursos de segurança do Istio permitem que os desenvolvedores se concentrem na segurança no nível do aplicativo. O Istio fornece o canal fundamental de comunicação segura, e
gerencia autenticação, autorização, e criptografia da comunicação de serviço em escala. Com o Istio, as comunicações de serviço são protegidas por padrão,permitindo que você aplique políticas de maneira consistente em diversos protocolos e tempos de execução - todos com poucas ou nenhuma alteração de sua  aplicação.

Embora o Istio seja independente de plataforma, use-o com o Kubernetes (ou infraestrutura) políticas de rede, os benefícios são ainda maiores, incluindo a capacidade de
segurança de  {{<gloss>}}pod{{</gloss>}}-to-pod ou comunicação service-to-service nas camadas de rede e aplicação.

Consulte o [Guia de conceitos de segurança ](/pt-br/docs/concepts/security/) para mais detalhes.

### Observabilidade

Istio possui recursos robustos de rastreamento, monitoramento e logs fornecem informações detalhadas sobre a implantação da malha de serviço. Obtenha um entendimento real de como o desempenho do serviço
afeta as coisas tanto upstream e downstream com os recursos de monitoramento do Istio, enquanto seus dashboards personalizados fornecem visibilidade do desempenho de todos os seus
serviços e permite que você veja como esse desempenho está afetando seus outros processos.

Todos esses recursos permitem que você defina, monitore e aplique SLOs de maneira mais eficaz nos serviços. Obviamente, o essencial é que você pode detectar e corrigir problemas rapidamente
e eficientemente.

Consulte o [Guia de conceitos de observabilidade](/pt-br/docs/concepts/observability/) para mais detalhes.

##Suporte das plataformas ao Istio

O Istio é independente de plataforma e projetado para ser executado em uma variedade de ambientes, incluindo os que abrangem Cloud,local, Kubernetes, Mesos e mais. Você pode
 fazer o deploy do Istio no Kubernetes ou no Nomad com o Consul. O Istio atualmente suporta:

* Deploy  de serviço no Kubernetes

* Serviços registrados no Consul

* Serviços em execução em máquinas virtuais individuais

## Integração e customização

O componente de aplicação de políticas do Istio pode ser estendido e personalizado para integrar-se às soluções existentes para ACLs, logging, monitoramento, quotas, auditoria,
e mais.
