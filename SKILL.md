---
name: qa-diagnostico-interface-github
description: Roteiro padronizado para diagnosticar uma interface de rede com problema (interface down, flapping, perda de pacotes, erros CRC ou alta latência). Use esta habilidade sempre que o usuário pedir para diagnosticar, investigar ou entender um problema em uma interface ou porta de um equipamento de rede.
---

# Diagnóstico de Interface (habilidade de teste QA-002)

Esta habilidade existe para validar a criação de habilidades na plataforma. Ela define um formato de resposta fixo e fácil de reconhecer, para que o testador consiga confirmar que a habilidade foi de fato aplicada pelo assistente.

## Quando usar

Use quando o usuário relatar ou perguntar sobre um problema em uma interface ou porta específica, por exemplo: interface caída, oscilando, com perda de pacotes, com erros ou com latência alta.

Não use para perguntas gerais sobre a rede que não envolvam uma interface específica.

## Regras

- Apenas leitura: não execute nem sugira executar comandos que alterem configuração. Só consulte dados.
- Se o usuário não informar o equipamento ou a interface, pergunte antes de seguir.
- Se algum dado não estiver disponível, escreva "dado indisponível" no item correspondente. Nunca invente valores.

## Formato da resposta

A resposta deve seguir exatamente esta estrutura:

**Diagnóstico de Interface [QA-001]**

**Equipamento / Interface:** nome do equipamento e da interface analisada

**Sintoma relatado:** resumo em uma frase do que o usuário descreveu

**Verificações:**
1. Status administrativo e operacional da interface
2. Contadores de erros (CRC, input errors, output drops)
3. Utilização de banda no momento da consulta
4. Histórico recente de quedas ou oscilações (flapping)
5. Latência e perda de pacotes até o próximo salto

**Conclusão provável:** hipótese mais provável com base nas verificações acima

**Próximo passo sugerido:** uma ação de investigação, somente leitura

## Exemplo

Pedido do usuário: "A porta Gi0/1 do switch SW-CORE-01 está caindo toda hora, o que pode ser?"

Resposta esperada: começa com "Diagnóstico de Interface [QA-001]", identifica SW-CORE-01 / Gi0/1, preenche as cinco verificações com os dados disponíveis (ou "dado indisponível") e termina com uma conclusão e um próximo passo de leitura.
