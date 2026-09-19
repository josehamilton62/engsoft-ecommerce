# Atividade Prática - Semana 1: Engenharia de Software I

## 1. Escolha do Sistema
O sistema adotado pelo grupo é um *Sistema E-commerce Dropshipping voltado para o mercado europeu*. Trata-se de uma plataforma de porte médio focada no gerenciamento de vendas, integração de logística com fornecedores internacionais e aplicação de estratégias de automação guiadas por Inteligência Artificial.

## 2. Justificativa da Escolha
* *Tamanho e Complexidade:* Utilizando a analogia da "casinha x prédio", este sistema se assemelha a um prédio. Ele possui complexidade média-alta devido às transações financeiras multimoeda, necessidade de conformidade com legislações europeias (como a GDPR) e integração de APIs de diversos distribuidores em tempo real.
* *Usuários e Equipe:* A plataforma seria utilizada por milhares de clientes europeus simultaneamente. Para sustentar a operação, a equipe de desenvolvimento provavelmente exigiria de 5 a 10 profissionais ao longo do tempo, divididos entre especialistas de back-end, front-end e integrações.
* *O risco do modelo "Artesanal":* Se o sistema fosse construído sem planejamento, processos e arquitetura definida, os prazos estourariam rapidamente e os custos disparariam. O software nasceria frágil, tornando qualquer modificação futura um risco de quebrar o sistema inteiro.
* *Insuficiência apenas da Programação:* Programar bem é apenas a escrita do código. Este sistema exige entender os requisitos legais do mercado europeu, projetar a arquitetura antes de programar, gerenciar riscos operacionais e coordenar o trabalho de várias pessoas na mesma base de código.

## 3. Aplicação dos Quatro Princípios

### Modularidade e Abstração
O sistema será dividido em responsabilidades separadas para esconder a complexidade interna de cada área:
* *Módulo de Autenticação:* Cuida exclusivamente do login, senhas e segurança das sessões dos usuários.
* *Módulo de Pagamentos:* Processa as transações financeiras e abstrai toda a complexidade de comunicação com bancos e gateways de pagamento europeus.
* *Módulo de Logística (Fornecedores):* Isola a comunicação, rastreamento e sincronização de catálogos via API com os distribuidores parceiros.
* *Módulo de Automação:* Concentra a lógica para precificação dinâmica e atendimento, sem interferir no fluxo principal de checkout.

### Qualidade de Software
Dentre os atributos da norma ISO 9126, os mais críticos para este sistema são:
* *Confiabilidade:* O sistema lidará com transações financeiras e dados sensíveis de clientes. Ele precisa se manter disponível e operando corretamente ao longo do tempo, sem falhas inesperadas.
* *Manutenibilidade:* Como as integrações de logística e gateways de pagamento sofrem atualizações frequentes, deve ser fácil realizar reparos e ajustes na base de código sem afetar outras áreas.

### Manutenibilidade e Evolução
O tipo de manutenção mais provável nos primeiros anos será a *Manutenção Adaptativa*.
* *Exemplo concreto:* Uma mudança nas regulamentações de proteção de dados na União Europeia ou uma alteração nas regras de impostos (VAT) exigirá que o software se adapte ao novo ambiente, demandando modificações no armazenamento de dados e na exibição de campos de faturamento no checkout.

### Boas Práticas Gerais
* *Documentação:* Não documentaremos cada linha de código, mas sim as decisões importantes de projeto, como os motivos para a escolha de determinada API de logística ou as regras de negócio europeias aplicadas.
* *Versionamento:* O histórico de todas as alterações será mantido de forma organizada utilizando o Git, permitindo que a equipe trabalhe simultaneamente sem arquivos duplicados e possibilitando a reversão de código caso uma mudança quebre o sistema.
* *Padronização:* A equipe adotará o padrão de nomenclatura em inglês (ex: camelCase para variáveis) e regras claras de formatação, garantindo que qualquer desenvolvedor consiga ler e entender o código escrito por outro colega sem estranhamento.
