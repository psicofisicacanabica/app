Este notebook implementa uma estrutura avançada para análise de intervenções em ansiedade, com foco na descoberta de subgrupos específicos que apresentam respostas particularmente fortes ou fracas à intervenção. Esta abordagem permite uma análise mais direcionada da eficácia das intervenções e fornece insights personalizados.

## Visão Geral

O notebook aprimora a estrutura de Mistura de Especialistas (MoE) para incorporar técnicas de descoberta de subgrupos, identificando padrões distintos de resposta entre os participantes de um estudo de intervenção em ansiedade.

## Fluxo de Trabalho

1. **Carregamento e Validação de Dados**: Carrega dados sintéticos de intervenção em ansiedade, valida sua estrutura, conteúdo e tipos de dados, tratando possíveis erros de forma adequada.

2. **Pré-processamento de Dados**: Realiza codificação one-hot da coluna de grupo e escala características numéricas para normalização.

3. **Descoberta de Subgrupos**: Implementa um método flexível de descoberta de subgrupos para identificar conjuntos baseados em respostas à intervenção:
   - Fortes Respondentes (Grupo A): Participantes com níveis de ansiedade pós-intervenção abaixo da média geral de ansiedade pré-intervenção
   - Fracos Respondentes (Grupo B): Participantes com níveis de ansiedade pós-intervenção acima da média geral de ansiedade pré-intervenção
   - Respondentes Típicos: Participantes não classificados nos outros subgrupos

4. **Análise de Valores SHAP**: Quantifica a importância das características dentro dos subgrupos descobertos, permitindo identificar fatores determinantes para diferentes níveis de resposta.

5. **Visualização de Dados**: Gera diversos gráficos destacando os subgrupos identificados:
   - Gráficos KDE (Kernel Density Estimation)
   - Gráficos de Violino
   - Gráficos de Coordenadas Paralelas
   - Visualizações de Hipergrafo

6. **Resumo Estatístico**: Realiza análise bootstrap e gera estatísticas resumidas para os subgrupos, incluindo intervalos de confiança.

7. **Relatório de Insights com LLMs**: Sintetiza descobertas usando três modelos de linguagem (Grok, Claude e Grok-Enhanced), enfatizando insights específicos para subgrupos, validando saídas dos LLMs e tratando potenciais erros de API.

## Bibliotecas Utilizadas

- pandas: Manipulação de dados
- matplotlib e seaborn: Visualizações estatísticas
- networkx: Criação de grafos e hipergrafos
- shap: Análise de importância de características
- scikit-learn: Regressão e pré-processamento
- plotly: Visualizações interativas
- scipy: Análise estatística avançada

## Características Principais

- **Tratamento Robusto de Erros**: Implementação abrangente de logging e tratamento de exceções em todas as funções
- **Visualização Avançada**: Uso de temas de visualização otimizados com paleta de cores neon sobre fundo escuro para destaque dos subgrupos
- **Integração com LLMs**: Arquitetura preparada para integração com múltiplos LLMs para análise complementar
- **Análise Estatística Rigorosa**: Implementação de bootstrapping para estimativas robustas de intervalos de confiança
- **Validação e Pré-processamento**: Verificação cuidadosa da integridade e formato dos dados antes da análise

## Uso

O notebook foi projetado para funcionar em ambiente Google Colab ou localmente, detectando automaticamente o ambiente e ajustando caminhos de saída. Para executar:

1. Instale as dependências necessárias (instalação automática incluída no notebook)
2. Execute todas as células do notebook
3. Os resultados (visualizações e relatórios) serão salvos no diretório de saída configurado

## Aplicações

Este framework é especialmente útil para:

- Pesquisadores de saúde mental analisando eficácia de intervenções
- Profissionais clínicos interessados em personalizar tratamentos
- Analistas de dados de saúde buscando padrões ocultos em respostas a tratamentos
- Estudos de eficácia comparativa entre diferentes abordagens terapêuticas

## Autor

Hélio Craveiro Pessoa Júnior
