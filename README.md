#  Agente de Detecção de Anomalias Financeiras (Make.com + Gemini API)

## Visão Geral
Solução *no-code* criada para automatizar a ingestão de dados operacionais e financeiros do iFood/varejo, analisar discrepâncias de custos e emitir pareceres executivos via Inteligência Artificial em tempo real.

## Problema de Negócio
Em rotinas operacionais e financeiras, a validação de planilhas de fechamento mensal consome dezenas de horas humanas. Erros de digitação, taxas atípicas e desvios marginais frequentemente passam despercebidos até o fechamento contábil. Esta automação faz a triagem contínua dos dados e aciona o time apenas diante de inconsistências relevantes.

##  Arquitetura e Tecnologias
- **Orquestrador de Fluxo:** Make.com (Plano Cloud Gratuito)
- **Base de Dados de Entrada:** Google Sheets (Simulação de DRE e transações)
- **Motor de Inteligência:** Google AI Studio — API do Gemini 1.5 Flash (Gratuito)
- **Engenharia de Prompt:** System Prompt estruturado com saída padronizada em JSON/Markdown
- **Canal de Notificação:** E-mail automático / Telegram Bot

##  Fluxo de Funcionamento
1. **Trigger:** Nova linha de transação/custo registrada na planilha do Google Sheets.
2. **Leitura e Filtro:** O Make.com extrai os dados brutos e formata o payload.
3. **Análise Preditiva (Gemini API):** O modelo avalia a margem, compara com limites históricos e classifica o risco (`BAIXO`, `MÉDIO`, `ALTO`).
4. **Alerta:** Caso o risco seja MÉDIO ou ALTO, um resumo executivo com a causa raiz do desvio é enviado automaticamente ao gestor responsável.

##  Impacto de Negócio Medível
- **Economia de Tempo:** Redução de até 80% do tempo gasto em conferências manuais de planilhas.
- **Prevenção de Perdas:** Identificação imediata de cobranças indevidas ou erros de repasse.
- **Custo zero de infraestrutura:** Construído totalmente com ferramentas de nível gratuito e alta escalabilidade.
