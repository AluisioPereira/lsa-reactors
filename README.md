# Sistema de Simulação de Reatores SBR com Machine Learning

**Acesso:** [https://aluisiopereira.github.io/lsa-reactors](https://aluisiopereira.github.io/lsa-reactors)

> Plataforma desenvolvida com base nos dados experimentais e no aparato operacional descritos na tese de **Elissandra Cheu Pereira do Nascimento**, voltada ao estudo da formação de grânulos aeróbios, desempenho de reatores SBR e dinâmica microbiológica em sistemas de tratamento biológico de efluentes.

O projeto integra:
- Simulação visual dos reatores
- Dados experimentais reais
- Formação dinâmica de biofilme e grânulos
- Controle operacional interativo
- Machine Learning aplicado à otimização do sistema

---

# Contexto Científico

Este sistema foi desenvolvido como uma representação computacional inspirada no experimento real conduzido na tese de **Elissandra Cheu Pereira do Nascimento**, reproduzindo:

- Estrutura física dos reatores
- Ciclos operacionais SBR
- Fotoperíodo experimental
- Formação progressiva de biomassa granular
- Variáveis físico-químicas monitoradas experimentalmente
- Comportamento operacional ao longo dos dias de operação

Os dados integrados foram extraídos e organizados a partir das informações experimentais presentes na pesquisa original.

---

# Principais Funcionalidades

## Dados Reais Integrados

O sistema utiliza aproximadamente **100 observações experimentais reais** dos reatores **F1** e **F2**, abrangendo os dias **6–500** do experimento original.

### Variáveis integradas
- DQO
- NH₄-N
- PT
- N-NO₂⁻
- SSVLM
- IVL30 / IVL10
- Granulometria
- EPS

Os dados foram extraídos diretamente dos PDFs experimentais e integrados ao motor de simulação e análise.

---

# Simulação dos Reatores SBR

## Ciclo Operacional Completo

A aplicação reproduz visualmente todas as etapas do ciclo operacional do SBR:

1. Enchimento
2. Reação aeróbia
3. Sedimentação
4. Descarte
5. Repouso

Cada etapa possui animações e transições dinâmicas em tempo real.

---

## Controle Operacional Interativo

Os principais parâmetros operacionais podem ser ajustados via interface gráfica:

- Tempos de ciclo
- SSVLM
- IVL
- Cargas afluentes
- Percentual de descarte

---

## KPIs em Tempo Real

O sistema calcula continuamente indicadores de desempenho:

- Eficiência de remoção de DQO
- Eficiência de remoção de NH₄-N
- Eficiência de remoção de PT
- Perfil de N-NO₂⁻

---

# Aparato Visual Fiel ao Experimento Real

## Estrutura Física dos Reatores

A interface foi desenvolvida com base nas fotos reais do experimento:

- Armário branco com trilhos laterais e suporte de prateleiras
- Dois reatores cilíndricos verticais (**R1** e **R2**)
- Tampa superior e base metálica
- Detalhes de ferrugem laranja reproduzidos visualmente
- Três válvulas laranja posicionadas conforme o sistema real
- Tubulações peristálticas azuis conectadas às bombas inferiores

---

## Biofilme e Crescimento Biológico

O sistema simula a evolução biológica dos reatores ao longo do tempo:

- Formação gradual de biofilme
- Crescimento de manchas verdes/amareladas
- Alteração visual da biomassa conforme os dias operacionais

---

# Fotoperíodo Dinâmico (12h/12h)

## Sistema de Iluminação Automatizado

O ambiente reproduz o fotoperíodo real do experimento.

### Período diurno
- Iluminação quente amarela
- Biomassa com tonalidade amarelo-esverdeada vibrante

### Período noturno
- Overlay escuro
- LED azul suave
- Escurecimento das algas e biofilme

---

## Relógio Operacional

- Relógio animado com ponteiro giratório
- Indicador visual de transição entre dia e noite

---

# Formação Progressiva de Grânulos

A evolução dos grânulos aeróbios é simulada dinamicamente.

## Estágios de desenvolvimento
- Inóculo
- Formando
- Jovens
- Maduros (~22 dias)

## Evolução visual
- Aumento progressivo do número de partículas
- Crescimento do tamanho dos grânulos
- Intensificação do biofilme nas paredes internas

---

# Sistema de Descarte Configurável

O usuário pode selecionar diferentes percentuais de descarte:

- 25%
- 50%
- 75%
- 100%

Durante a fase de descarte:
- O nível líquido reduz proporcionalmente
- O fluxo é animado saindo pelas válvulas dos reatores

---

# Painel de Nutrientes (CHONPS)

O painel lateral exibe continuamente os parâmetros do afluente:

- Carbono (DQO)
- Nitrogênio (NH₄)
- Fósforo (PT)
- Alcalinidade
- NaHCO₃
- Glicose

Os valores são atualizados dinamicamente conforme a configuração operacional.

---

# Motor de Machine Learning

## Random Forest Simplificado

O sistema possui um modelo de Machine Learning treinado com os dados experimentais reais.

### Funcionalidades
- Predição da eficiência de remoção
- Recomendação automática da melhor configuração operacional
- Identificação dos períodos de maior desempenho

---

## Recursos Analíticos

- Importância das features
- Gráfico predição vs. real
- Sensibilidade paramétrica
- Recomendações operacionais automáticas

---

# Visualizações e Dashboards

## Aba: Desempenho
- Eficiência ao longo do tempo
- Perfil de nitrogênio
- DQO afluente vs. efluente

## Aba: Grânulos
- Distribuição granulométrica (mm)
- Relação EPS/PN
- Evolução temporal de SSVLM e IVL

## Aba: Otimização ML
- Painel completo de otimização operacional
- Recomendações automáticas

## Aba: Dados Reais
- Tabela filtrável dos reatores F1/F2
- Codificação por cores baseada em performance


## Aba ⚗ Volume & Ciclo
- Balanço volumétrico R1 e R2 lado a lado — Vol. enchimento, Vol. descarte, Variação/ciclo (verde = estável, âmbar = crescendo, vermelho = esvaziando), TRH estimado
- Slider "% Enchimento" — independente para R1 e R2, simula quanto volume entra por ciclo
- Barra de nível visual — mostra o nível atual do reator (R1 verde, R2 roxo) com rótulo "X.XX L (Y%)"
- Gráfico de evolução do volume por ciclo — 4 linhas: pós-enchimento e pós-descarte para R1 e R2, com linha de capacidade máxima
- Tabelas de parâmetros hidráulicos — R1 e R2 com 14 linhas cada (TRH, carga hidráulica, ciclos/dia, tempos de fase, taxa de troca, estado estável)
- Slider Ciclos/dia — afeta TRH e carga hidráulica de ambos reatores

## Aba 🧬 CHONPS & Efluente
- Sliders afluente adicionais — DBO₅, SO₄²⁻, OD, pH, Temperatura, N orgânico (independentes R1/R2 via abas R1/R2)
- Botão "▶ Simular Efluente" — calcula e renderiza tudo imediatamente
- Tabelas CHONPS R1 e R2 — 14 linhas com elementos C, N, P, S, O, H, mostrando Afluente → Efluente → Eficiência (colorida: verde ≥85%, âmbar ≥60%, vermelho <60%)
- Gráfico Balanço de Massa — entradas e saídas em g/dia para R1 e R2 (barras comparativas)
- Gráfico Eficiências de Remoção — R1 vs R2 em %, para DQO, DBO₅, NH₄-N, PT, SO₄²⁻, Alcalinidade
- Tabela comparativa R1 vs R2 — afluente, efluente e eficiência de ambos os reatores lado a lado

---

# Tecnologias Utilizadas

- React
- TypeScript
- TailwindCSS
- Framer Motion
- Chart.js / Recharts
- Random Forest (Scikit-learn)
- Processamento de dados experimentais em Python

---

# Objetivo do Projeto

Este projeto foi desenvolvido para:

- Simular o comportamento operacional de reatores SBR
- Integrar dados experimentais reais em ambiente interativo
- Demonstrar formação de grânulos aeróbios
- Aplicar Machine Learning para suporte à operação e otimização
- Criar uma representação visual próxima ao sistema experimental físico real
