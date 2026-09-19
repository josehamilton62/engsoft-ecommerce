# Dinâmica de Elicitação e Análise - Semana 2

## 1. Divisão de Papéis e Personas

**Papel 1: Engenheiro de Requisitos e Dono do Sistema (Stakeholder)**
*   **Responsável:** José Hamilton
*   **Persona (Dono do Sistema):** José é o empreendedor e gestor principal do e-commerce de dropshipping. Ele deseja automatizar o fluxo de pedidos para os fornecedores asiáticos/europeus para maximizar sua margem de lucro. O que mais o frustra hoje são custos ocultos de logística e integrações manuais que tomam tempo e causam erros de digitação nos endereços de entrega.

**Papel 2: Usuário Final (Stakeholder)**
*   **Responsável:** Ana Maria
*   **Persona (Usuária Final):** Ana é uma consumidora europeia residente no Porto, Portugal. Ela adora comprar produtos inovadores online com clareza nos preços. Ela se frustra profundamente com lojas virtuais que escondem taxas alfandegárias (IVA/VAT) que só aparecem na entrega ou e-commerces que não fornecem o rastreio detalhado do pacote.

## 2. Notas das Entrevistas

**Entrevista 1: Engenheiro de Requisitos (José) entrevistando Usuária Final (Ana)**
*   **Técnica utilizada:** Entrevista aberta, focada em entender o problema e não em perguntar a solução, conforme os princípios de elicitação.
*   **Notas:** Ana destacou que a transparência é o fator decisivo para ela finalizar uma compra. Ela relatou que abandona o carrinho se não houver um cálculo claro e antecipado de impostos para Portugal. Além disso, ela relatou a necessidade de saber exatamente o status do envio.

**Entrevista 2: Engenheira de Requisitos Auxiliar (Ana) entrevistando Dono do Sistema (José)**
*   **Técnica utilizada:** Entrevista semiestruturada.
*   **Notas:** José explicou que o repasse do pedido do cliente para o fornecedor precisa ser automático, sem intervenção humana, assim que o pagamento é aprovado. Ele também revelou preocupação com o custo financeiro: sistemas de rastreamento "em tempo real" (passo a passo via satélite) cobram taxas altas por requisição na API, o que destrói a margem de lucro em produtos baratos (low-ticket).

**O Conflito:**
Durante a reunião conjunta, surgiu uma divergência clara. A persona de Ana (Usuária Final) exigiu rastreamento passo a passo em tempo real para se sentir segura com a compra internacional. A persona de José (Dono do Sistema) recusou a ideia, argumentando que o custo das APIs de rastreio premium inviabilizaria o negócio financeiramente. 

**A Mediação (pelo Engenheiro de Requisitos - José):**
Agindo como mediador[cite: 2], o Engenheiro de Requisitos não cedeu a quem "gritou mais alto". Foi proposto um meio-termo apresentando os trade-offs: 
*   **Resolução:** O sistema oferecerá o rastreamento padrão gratuitamente (atualizações apenas nos marcos principais: saída, chegada na Europa e saiu para entrega). O rastreamento premium, passo a passo, será oferecido como um *upsell* (cobrado à parte como taxa extra) no momento do checkout, para quem deseja pagar por essa segurança extra. Ambas as partes aceitaram.