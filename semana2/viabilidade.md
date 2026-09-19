# Estudo de Viabilidade

## Índice

1. [Identificação](#1-identificação)
2. [O Sistema](#2-o-sistema)
3. [Viabilidade Técnica](#3-viabilidade-técnica)
4. [Viabilidade Econômica](#4-viabilidade-econômica)
5. [Viabilidade Operacional](#5-viabilidade-operacional)
6. [Conclusão](#6-conclusão)

---

## 1. Identificação

| Campo | Preencher |
|---|---|
| Grupo | Grupo 3 |
| Integrantes | José Hamilton Meneses Filho e Ana Maria Gonçalves Alves |
| Disciplina | Engenharia de Software I |
| Semana | 2 |
| Data | 19 de Setembro de 2026 |

## 2. O Sistema

Sistema de E-commerce Dropshipping focado no mercado europeu. O software atua conectando clientes finais na Europa a produtos de fornecedores globais, sem a necessidade de manter estoque próprio. O sistema é responsável por gerenciar o catálogo, processar pagamentos, calcular impostos locais (IVA) e rotear ordens de envio automaticamente para os parceiros de logística.

| ID | Descrição |
|---|---|
| RF-01 | O sistema deve calcular automaticamente o valor do imposto de valor agregado (IVA/VAT) no carrinho de compras com base no país europeu de destino selecionado pelo usuário. |
| RF-02 | O sistema deve permitir que o cliente acompanhe o status logístico do pedido através de uma página de rastreamento. |
| RF-03 | O sistema deve encaminhar a ordem de compra e os dados de entrega para o sistema do fornecedor automaticamente após a aprovação financeira. |
| RF-04 | O sistema deve permitir que o usuário escolha entre opções de envio padrão ou envio rastreável premium durante a etapa de checkout. |
| RF-05 | O sistema deve disparar um recibo eletrônico detalhado para o e-mail do cliente após a confirmação do pagamento da reserva ou compra. |
| RF-06 | O sistema deve permitir que o dono da loja ative ou inative a visibilidade de produtos no catálogo manualmente. |

| ID | Categoria | Descrição |
|---|---|---|
| RNF-01 | Desempenho | O cálculo dos impostos do carrinho de compras deve ser processado e exibido em no máximo dois segundos. |
| RNF-02 | Usabilidade | Um usuário final sem experiência prévia com o sistema deve conseguir concluir uma compra (checkout) em menos de três minutos. |
| RNF-03 | Confiabilidade | O encaminhamento da ordem de compra para o fornecedor deve ter uma taxa de sucesso de pelo menos 99,9%. |
| RNF-04 | Segurança | O sistema deve processar os dados do cartão de crédito de forma criptografada de ponta a ponta, sem armazenar o código de segurança (CVV) no banco de dados. |
| RNF-05 | Manutenibilidade | O módulo de cálculo de impostos europeus deve estar isolado da interface do usuário, permitindo atualizações nas regras fiscais sem exigir modificações visuais no front-end. |
| RNF-06 | Portabilidade | A interface do e-commerce deve funcionar de forma equivalente e sem perda de funcionalidades tanto em navegadores de computador quanto em dispositivos móveis (smartphones). |

---

## 3. Viabilidade Técnica

A equipa possui conhecimentos base de desenvolvimento web para a construção da interface do catálogo e usabilidade da loja (RNF-02, RNF-06). O maior desafio técnico reside no RNF-01 (cálculo do IVA europeu em até dois segundos) e no RNF-04 (processamento seguro de cartões sem armazenar CVV). A lógica tributária europeia é complexa e volátil. 

**Riscos e Mitigação:** A tentativa de desenvolver internamente o cálculo de impostos e o processamento de pagamentos representa um risco elevado de segurança e conformidade. Esse risco será mitigado através da integração de APIs especializadas e prontas para o mercado europeu (como Stripe para pagamentos e TaxJar/Quaderno para o cálculo isolado do IVA, cumprindo o RNF-05), reduzindo a complexidade técnica para um nível comportável pela equipa.

## 4. Viabilidade Econômica

O modelo de dropshipping reduz drasticamente o investimento inicial, uma vez que não exige a aquisição de inventário físico ou arrendamento de armazéns. Os principais custos envolverão o alojamento na nuvem, o registo de domínio e as taxas cobradas pelas APIs de pagamento e de cálculo de IVA. 

O benefício financeiro compensa largamente o investimento, pois a automação do encaminhamento de ordens (RF-03) e do cálculo de impostos permite que a loja opere em todo o continente europeu 24 horas por dia, escalando o volume de vendas sem a necessidade de aumentar a equipa administrativa.

## 5. Viabilidade Operacional

Do ponto de vista do utilizador europeu, a plataforma não exige curva de aprendizagem. O cálculo automático e transparente do IVA no carrinho de compras (RF-01) gera confiança e está alinhado com as expectativas do mercado local.

Para a gestão interna (stakeholders), a aceitação será alta. O sistema elimina as tarefas repetitivas e sujeitas a erro humano, como contactar fornecedores manualmente para cada venda, graças à comunicação automática com os parceiros logísticos (RF-03 e RNF-03). Não é expectável qualquer resistência à mudança, sendo apenas necessária a monitorização esporádica da comunicação entre a loja e o fornecedor.

---

## 6. Conclusão

- [ ] Viável
- [x] Viável com ressalvas
- [ ] Não viável

O projeto é viável devido ao baixo custo de entrada do modelo de dropshipping e aos benefícios da automação. A ressalva deve-se à obrigatoriedade de garantir integrações externas robustas e seguras para lidar com a tributação europeia (IVA) e com a encriptação de pagamentos, sendo crítico para a conformidade legal do negócio.