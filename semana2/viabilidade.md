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
