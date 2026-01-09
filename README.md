# Análise Estratégica do Mercado de Dados 2024: Saários, Tendências e Oportunidades

![Dashboard Page 1](/images/pro1_pag1.png)

[View interactive dashboard here on the Power BI Service](https://app.powerbi.com/groups/me/reports/8dde87a8-019e-4038-a9de-9ba714b72c14/037162d7274a42ebc05d?experience=power-bi)

## Introduction

O mercado de tecnologia é dinâmico e, para profissionais em transição de carreira, a falta de clareza sobre salários e exigências pode levar a decisões erradas. Este dashboard foi projetado para responder:

1. Quais cargos possuem a melhor relação entre volume de vagas e remuneração mediana?

2. Como a modalidade de trabalho (WFH/Remoto) impacta a oferta salarial?

3. Qual a tendência de contratação ao longo do ano?

 

## Arquitetura Técnica e Decisões de Projeto

1. Processamento de Dados (ETL)
No Power Query, apliquei técnicas de limpeza para garantir a integridade dos KPIs:  
* Normalização de Tipos: Conversão de moedas e tratamento de valores nulos para evitar distorções na mediana.    
* Criação de Colunas Condicionais: Categorização de níveis de benefícios e regimes de trabalho.

2. Modelagem e DAX (O Cérebro)
* Diferente de modelos básicos, utilizei Medidas Explícitas em DAX para garantir performance e escalabilidade.

* Cálculo de Mediana: Optei pela mediana em vez da média para proteger os indicadores contra outliers (salários muito fora da curva).

* KPI de Rating: Desenvolvi uma lógica visual de "Star Rating" para classificar a atratividade salarial de cada cargo.

3. UX/UI e Storytelling Visual
O design foi pensado para reduzir a carga cognitiva:

* Scatter Plot (Dispersão): Utilizado para cruzar Salário Hora vs. Salário Anual, identificando quais cargos são mais valorizados em contratos curtos ou longos.

* Sparklines: Integradas na tabela de "Job Stats" para mostrar a tendência sem ocupar espaço extra.

* Navegação Inteligente: Implementação de um botão de Drill-Through dinâmico, permitindo que o usuário saia da visão macro para uma análise profunda de um cargo específico com um clique.

## Visão Geral do Dashboard

*Esse dashboard foi dividido em duas páginas tanto para um boa visão geral quanto para uma visão detalhada de cada profissão*

### Página 1: Panorama Geral do Mercado

![Dashboard Page 1](/images/pro1_pag1.png)

Esta página funciona como um sumário. O objetivo aqui é dar um panorama geral do mercado de dados em 2024, permitindo identificar padrões e tendências globais.

* Painel de KPIs: Entrega de imediato o volume total de vagas e a mediana salarial. O "Salary Star Rating" traduz um dado numérico em uma percepção de valor imediata.

* Hourly vs Yearly Salary (Scatter Plot): Este é o "pulo do gato" do seu design. Ele mostra a correlação entre ganhos anuais e ganhos por hora, ajudando a identificar quais cargos são mais valorizados em contratos de curto prazo ou consultorias.

* Job Over Time: Uma análise de série temporal que revela a sazonalidade das contratações. Note como a linha de tendência (sparkline) ajuda a prever o ritmo do mercado.

* Job Stats Table: Uma visão tabular enriquecida com Sparklines, permitindo comparar números exatos e tendências de crescimento em uma única linha.

### A Experiência de Drill-Through e Interatividade
O diferencial sênior deste dashboard é a Interatividade Contextual.

**Como funciona:** O usuário não precisa procurar o mesmo cargo em duas páginas diferentes. Ao selecionar um cargo específico na tabela ou nos gráficos da Página 1 e clicar no botão "Drill Through Job", o Power BI "carrega" esse filtro para a Página 2. Isso cria uma experiência de navegação fluida, onde o sistema entende o interesse do usuário e fornece os detalhes sem que ele precise filtrar tudo novamente.     

**Continuidade de Contexto e Filtros:** Também implementei a técnica de Cross-report Filtering via Drill-Through. Ao navegar da visão macro para a micro, o sistema preserva o intervalo de tempo selecionado no slider da Página 1 através da configuração Keep All Filters. Isso permite que o usuário analise o comportamento de um cargo específico exatamente dentro do período de tempo que despertou seu interesse inicial, garantindo uma análise coerente e sem perdas de contexto.
### Página 2: Job Title Drill Through (Visão Micro)

![Dashboard Page 1](/images/pro1_pag2.png)

Uma vez que o usuário escolheu um cargo (ex: Data Engineer), esta página oferece uma análise daquela função específica.

* Gauges de Salário: Diferente de um card comum, o Gauge mostra onde a mediana do cargo se posiciona em relação ao mínimo e máximo do mercado. Se o ponteiro está à direita(ou seja, passa do meio), o cargo é de elite salarial.

* Análise de Perfil (WFH, Degree, Insurance): Três gráficos de rosca que respondem às principais dúvidas de quem busca uma vaga: "Posso trabalhar de casa?", "Preciso de diploma?", "Terei plano de saúde?".

* Distribuição Global (Mapa): Visualização geográfica de onde as oportunidades para este cargo estão concentradas, permitindo análises de realocação ou busca por vagas remotas internacionais.

* Marketplaces & Platforms: Identifica quais plataformas (LinkedIn, Indeed, etc.) são mais eficazes para encontrar esse tipo de vaga, economizando tempo do candidato.

## Conclusão


Este dashboard demonstra como o Power BI pode transformar dados brutos de vagas de emprego em uma ferramenta poderosa para análise de carreira. Ele permite que os usuários segmentem, filtrem e explorem detalhadamente os dados para tomar decisões fundamentadas sobre suas trajetórias profissionais. Além disso, Este projeto demonstra minha capacidade de transformar dados brutos em uma ferramenta de suporte à decisão. Mais do que um visual bonito, o foco foi criar uma estrutura de dados robusta e uma interface que guie o usuário até a resposta que ele procura.