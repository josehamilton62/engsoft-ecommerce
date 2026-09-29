# Projeto Final

> Este arquivo funciona como o índice do projeto. Ele não repete o conteúdo de cada artefato, só resume e aponta o caminho. Preencham os resumos e ajustem os links para os arquivos reais do repositório de vocês.

## Índice

1. [Identificação](#1-identificação)
2. [Visão Geral do Sistema](#2-visão-geral-do-sistema)
3. [Fundamentos do Sistema (Semana 1)](#3-fundamentos-do-sistema-semana-1)
4. [Requisitos e Viabilidade (Semana 2)](#4-requisitos-e-viabilidade-semana-2)
5. [Modelagem UML (Semana 3)](#5-modelagem-uml-semana-3)
6. [Modelo de Processo (Semana 4)](#6-modelo-de-processo-semana-4)
7. [Cenário de Mudança](#7-cenário-de-mudança)

## 1. Identificação

| Campo | Preencher |
| --- | --- |
| Grupo | Grupo 3 |
| Tema | E-commerce de Pequeno Porte (Dropshipping) |
| Integrantes | José Hamilton Meneses Filho e Ana Maria Gonçalves Alves |
| Disciplina | Engenharia de Software I |

## 2. Visão Geral do Sistema

Plataforma web de e-commerce projetada para automatizar o processo de vendas online no modelo dropshipping para o mercado europeu. O sistema conecta clientes a fornecedores globais, gerindo o catálogo, o cálculo dinâmico de impostos (IVA) e a automação do roteamento logístico, dispensando a necessidade de manter stock físico próprio.

---

## 3. Fundamentos do Sistema (Semana 1)

O sistema exige Engenharia de Software devido à sua elevada complexidade inerente, como o processamento de transações financeiras multimoeda, a integração de APIs externas e a conformidade legal (GDPR e IVA europeu). Os princípios são aplicados através da separação do sistema em módulos independentes (modularidade), do foco na segurança rigorosa de pagamentos (qualidade), da garantia de adaptação rápida a novos fornecedores (manutenibilidade) e do versionamento contínuo e organizado do código via Git (boas práticas).

🔗 [semanal/](semanal/)

## 4. Requisitos e Viabilidade (Semana 2)

O processo de elicitação baseou-se em entrevistas estruturadas e abertas que revelaram um conflito: a utilizadora exigia um rastreio em tempo real, enquanto o administrador rejeitava os custos elevados dessa API. A mediação resolveu o problema oferecendo o rastreio detalhado apenas como um serviço premium pago no checkout. Foram consolidados 6 RFs e 6 RNFs, demonstrando-se que o projeto é técnica, económica e operacionalmente viável, com a ressalva obrigatória de delegar o cálculo do IVA e o processamento de pagamentos a APIs externas consolidadas para garantir a segurança.

🔗 [semana2/dinamica.md](semana2/dinamica.md)
🔗 [semana2/requisitos.md](semana2/requisitos.md)
🔗 [semana2/viabilidade.md](semana2/viabilidade.md)

## 5. Modelagem UML (Semana 3)

A estrutura do sistema foi mapeada pelo Diagrama de Casos de Uso (detalhando as interações entre os clientes, a gestão, os gateways de pagamento e os fornecedores) e pelo Diagrama de Classes (estruturando as entidades de negócio como `Pedido`, `Carrinho` e `Produto`). O comportamento dinâmico foi ilustrado através de Diagramas de Sequência distintos:

* **Ana Maria** modelou a ação: Finalizar Checkout.
* **José Hamilton** modelou a ação: Encaminhar Ordem de Compra ao Fornecedor Automático.

🔗 [semana3/](semana3/), incluindo `diagrama_de_caso_de_uso.drawio`, `diagrama_de_classes.drawio`, `sequencia_checkout.drawio` e `sequencia_encaminhar_fornecedor.drawio`

## 6. Modelo de Processo (Semana 4)

O modelo de processo adotado foi o **Ágil**, com recurso ao framework **Scrum**. Esta escolha justifica-se pela baixa estabilidade dos requisitos inerente ao mercado de e-commerce e pelo perfil técnico da nossa equipa, que beneficia de validações rápidas em iterações curtas (Sprints). Modelos rígidos, como o Cascata ou o Incremental, foram descartados por não possuírem rituais contínuos de repriorização do trabalho perante imprevistos. Utilizando o Scrum, o cenário de mudança imposto externamente não quebra o planeamento: a exigência seria adicionada imediatamente ao *Product Backlog* como uma nova *User Story* e desenvolvida na *Sprint* seguinte.

🔗 [semana4/processo.md](semana4/processo.md)

---

## 7. Cenário de Mudança

### O cenário recebido

> "Um fornecedor importante passou a exigir que todo pedido feito através da loja seja informado a ele assim que for realizado, para que ele possa preparar o envio antes mesmo da confirmação do pagamento."

### Tipo de manutenção

Esta alteração caracteriza-se como uma **Manutenção Adaptativa**. Justifica-se porque não se trata de uma correção de falhas e defeitos do código (corretiva) nem de uma otimização puramente opcional de usabilidade ou performance (perfectiva). Consiste numa adaptação estritamente obrigatória a uma nova regra imposta pelo ambiente externo (a exigência rigorosa de um parceiro de negócio de grande importância) para que a plataforma continue a operar e cumprir as suas funções logísticas no mercado.

### Análise de impacto

O cenário impacta diretamente os seguintes artefatos construídos nas semanas anteriores:

1. **Requisitos Funcionais (Semana 2):** O RF-03 (que originalmente exigia o envio da ordem apenas *após* a aprovação financeira) deve ser reescrito de forma a exigir o envio antecipado, separando obrigatoriamente os fluxos lógicos de notificação ao fornecedor do fluxo de verificação do pagamento financeiro.
2. **Diagramas de Sequência (Semana 3):** O diagrama "Encaminhar Ordem ao Fornecedor Automático" (elaborado pelo José Hamilton) sofre um impacto estrutural profundo e terá de ser redesenhado. O gatilho temporal deixa de ser a recepção bem-sucedida do pagamento por parte do Gateway; o sistema (Controlador de Vendas) terá de invocar o fornecedor logístico de modo assíncrono assim que os dados do pedido forem inseridos no checkout pela Interface do Utilizador.
3. **Diagrama de Classes (Semana 3):** A classe `Pedido` não necessitará de novos métodos, mas precisará de suportar novos estados lógicos associados ao seu atributo interno `statusLogistico` (por exemplo: "Reservado no Fornecedor / Aguarda Pagamento"), para garantir que a gestão interna compreende em que fase se encontra a transação.
4. **O que não muda:** A viabilidade económica do modelo não é alterada com esta modificação, pois o custo operacional de integração mantém-se. Além disso, o Diagrama de Casos de Uso mantém a sua validade total, pois as funções (Casos de Uso) continuam a existir exatamente para os mesmos Atores do sistema; a mudança ocorreu puramente na ordem cronológica de execução interna dos processos.
