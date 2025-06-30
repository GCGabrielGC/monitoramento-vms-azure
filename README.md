# 🚀 Monitoramento de Máquinas Virtuais no Microsoft Azure

## 📝 Descrição do Desafio

Este repositório foi criado como parte de um laboratório prático com o objetivo de configurar e gerenciar o monitoramento de recursos no Azure, com foco em máquinas virtuais (VMs). O desafio principal é demonstrar como manter visibilidade, controle e resposta proativa a eventos críticos no ambiente de nuvem, como a exclusão acidental de uma VM.

---

## 🎯 Objetivos

- Compreender os principais componentes do Azure Monitor.
- Aprender a configurar métricas, logs e alertas personalizados.
- Utilizar o Log Analytics para consultas específicas.
- Criar um repositório de apoio com anotações e dicas.

---

## 📊 Azure Monitor

O Azure Monitor é a principal ferramenta de monitoramento da Microsoft para recursos em nuvem. Ele coleta dados em tempo real e históricos para análise, diagnóstico e geração de alertas.

### Componentes principais:
- **Métricas:** Valores numéricos como uso de CPU, memória e disco.
- **Logs:** Informações detalhadas de eventos, como acessos e falhas.
- **Log de Atividades:** Histórico de ações realizadas em recursos.
- **Service Health:** Estado de serviços Azure a nível global.
- **Workspace (Log Analytics):** Contêiner para armazenar e consultar dados de log.

> 📚 [Documentação oficial do Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview)

---

## ⚠️ Configuração de Alertas

### Etapas:
1. Escolha do recurso a ser monitorado.
2. Definição do **sinal** (ex: CPU > 90%).
3. Criação de uma **regra de alerta**.
4. Associação a um **grupo de ação** (notificações por e-mail, webhook, etc).

> 💡 É possível associar até **5 grupos de ação** por regra.

> 📚 [Documentação: Criar alertas no Azure](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-unified-alerts)

---

## 📂 Log Analytics

O **Log Analytics** permite consultar dados de logs usando a linguagem **KQL (Kusto Query Language)**.

### Exemplo de Consulta:
```kusto
Event
| where (EventLevelName == "Error")
| where (TimeGenerated > ago(1d))
| summarize ErrorCount = count() by Computer
| top 10 by ErrorCount desc
```

Recursos:
1. Consultas interativas
2. Exportação de dados para Power BI ou Excel
3. Alertas baseados em logs

> 📚 [Documentação: Criar alertas no Azure](https://learn.microsoft.com/pt-br/azure/azure-monitor/logs/log-query-overview)

---

## 🧠 Dicas Finais
1. Use ações rápidas para configurar grupos de ação.
2. Sempre verifique se o Workspace está corretamente associado.
3. Combine métricas e logs para uma visão completa da saúde do recurso.
4. Utilize os filtros no Log de Atividades para identificar eventos específicos.

---

## 📚 Fontes e Leitura Complementar
> [1. Visão geral do Azure Monitor](https://learn.microsoft.com/pt-br/azure/azure-monitor/fundamentals/overview)
> [2. Guia de Alertas](https://learn.microsoft.com/pt-br/azure/azure-monitor/alerts/alerts-overview)
> [3. Consultas no Log Analytics](https://learn.microsoft.com/pt-br/azure/azure-monitor/logs/log-query-overview)

---

