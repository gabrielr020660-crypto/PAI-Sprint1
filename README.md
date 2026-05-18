# GoodWe ChargeGrid Assistant


## Contexto (EV Challenge 2026)
O EV Challenge 2026 apresenta desafios ligados à expansão de veículos elétricos e à necessidade de melhorar a gestão de eletropostos.  
A GoodWe propõe soluções inteligentes para infraestrutura de carregamento, mas ainda existe um problema central: a falta de mecanismos integrados para orquestrar potência, registrar ciclos de recarga, faturar corretamente e manter comunicação eficiente com operadores e usuários.

## Problema Abordado
Atualmente, muitos eletropostos comerciais operam sem um sistema automatizado completo que permita:

- Controle e orquestração de potência entre múltiplos carregadores
- Registro detalhado de ciclos/sessões de carregamento
- Faturamento automático baseado em consumo (kWh)
- Relatórios operacionais e financeiros
- Comunicação rápida sobre falhas e indisponibilidade

Isso causa perdas financeiras, baixa eficiência operacional e dificuldade no suporte técnico.

## Proposta do Chatbot
O **GoodWe ChargeGrid Assistant** é um chatbot operacional com IA, voltado para eletropostos comerciais (ChargeGrid Intelligence).  
Seu objetivo é auxiliar operadores e gestores a monitorar carregadores, organizar distribuição de potência, consultar logs de sessões e apoiar faturamento e comunicação.

O chatbot será integrado ao sistema do eletroposto e funcionará como uma interface inteligente para consulta e suporte em tempo real.

## Persona Principal
 **Gestor/Operador Comercial de Eletroposto**

Justificativa: essa persona é responsável pela operação diária, faturamento e tomada de decisão sobre uso e disponibilidade dos carregadores, sendo diretamente impactada pelo problema central do desafio.

## Escopo do Chatbot (O que ele deve fazer)
O chatbot deve ser capaz de:

- Informar status dos carregadores (livre, ocupado, falha, manutenção)
- Consultar sessões de carregamento e consumo registrado (kWh)
- Auxiliar no cálculo de faturamento e geração de relatórios
- Identificar carregadores com maior índice de falha
- Sugerir ações para balanceamento/orquestração de potência
- Orientar procedimentos básicos de reinício e segurança
- Registrar ocorrências e sugerir abertura de chamados técnicos

## O que o chatbot NÃO deve fazer
- Inventar dados técnicos ou financeiros
- Autorizar mudanças críticas sem validação/autenticação
- Realizar diagnósticos elétricos avançados sem confirmação de dados reais
- Substituir equipe técnica especializada

## Tecnologias Selecionadas (com justificativa)
### LLM (Modelo de IA)
**OpenAI API (GPT-4o / GPT-4.1)**  
Motivo: alta precisão em linguagem natural, boa capacidade de seguir prompts técnicos e excelente desempenho em respostas contextualizadas.

### Orquestração
**LangChain**  
Motivo: facilita integração com LLM, implementação de memória e pipelines com RAG.

### Base de conhecimento / Busca semântica
**ChromaDB ou Pinecone (Vector Database)**  
Motivo: permite busca semântica eficiente em manuais técnicos, regras operacionais, logs e FAQs.

### Backend
**Python + FastAPI**  
Motivo: rápido, simples e ideal para criação de APIs REST para integração com sistemas do eletroposto.

### Banco de Dados (dados operacionais)
**PostgreSQL**  
Motivo: armazenamento confiável para sessões, faturamento e logs.

## Funcionamento Geral (resumo)
1. Usuário envia pergunta (operador/gestor)
2. Sistema identifica intenção (ex: faturamento, falha, status)
3. Consulta logs e base de conhecimento
4. Injeta contexto no prompt do modelo
5. Modelo gera resposta objetiva e operacional
6. Resposta retorna ao usuário e é registrada no log do sistema

## Fluxograma
O fluxograma está disponível em:  
`/docs/fluxograma.png`

## Modelo de Testes
Os testes estão disponíveis em:  
`/tests/test_cases.md`

## System Prompt
O prompt base está disponível em:  
`/prompts/system_prompt.md`
