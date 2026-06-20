# 📊 Test Report — Sprint 1

**Projeto:** QA Portfolio — Mercado Livre  
**Sprint:** Sprint 1  
**Board:** [Jira — SCRUM](https://gabrielacurti.atlassian.net/jira/software/projects/SCRUM/boards/1)  
**Período:** Execução em 10 dias  
**Features cobertas:** Login, Busca de Produto, Frete, Carrinho, Checkout

---

## 📌 Resumo Executivo

A Sprint 1 cobriu o fluxo completo de compra do Mercado Livre, com execução de **56 casos de teste** distribuídos em 5 funcionalidades principais. Foram identificados **3 bugs reais** no sistema em produção, todos relacionados ao módulo de Busca de Produto.

---

## 📈 Status Geral dos Casos de Teste

| Feature | Total de Casos | ✅ Passou | ❌ Falhou | 🔒 Bloqueado | 🆕 Novo |
|---------|----------------|-----------|-----------|--------------|---------|
| Login | 14 | 8 | 6 | 0 | 0 |
| Busca de Produto | 10 | 7 | 3 | 0 | 0 |
| Frete | 9 | 9 | 0 | 0 | 0 |
| Carrinho | 11 | 11 | 0 | 0 | 0 |
| Checkout | 12 | 10 | 0 | 1 | 1 |
| **Total** | **56** | **45** | **9** | **1** | **1** |

**Taxa de aprovação geral:** ~80%

---

## 🐛 Defeitos Identificados

| ID | Título | Prioridade | Tipo | Feature |
|----|--------|------------|------|---------|
| [BUG-BUSCA-001](../bug-reports/BUG-BUSCA-001.md) | Busca retorna resultados irrelevantes com termo inexistente | 🔴 Alta | Funcional | Busca |
| [BUG-BUSCA-002](../bug-reports/BUG-BUSCA-002.md) | Filtro de preço aceita faixa invertida e exibe produtos fora do range | 🟠 Média | Funcional | Busca |
| [BUG-BUSCA-003](../bug-reports/BUG-BUSCA-003.md) | Busca retorna resultados irrelevantes com caracteres especiais | 🟠 Média | Funcional | Busca |

**Total de bugs:** 3  
**Distribuição por prioridade:** 1 Alta · 2 Média · 0 Baixa  
**Distribuição por tipo:** 3 Funcional

---

## 🔎 Observações por Feature

### 🔐 Login
Maior concentração de falhas da sprint, majoritariamente ligadas a mensagens de sistema divergentes do esperado (reCAPTCHA e fluxo de autenticação multifator não previstos nas regras de negócio originais).

### 🔍 Busca de Produto
Feature com maior criticidade: todos os 3 bugs da sprint estão concentrados aqui. Padrão recorrente identificado — o sistema utiliza anúncios de serviços como fallback ao invés de tratar adequadamente buscas sem resultado ou com entrada inválida.

### 🚚 Frete e 🛒 Carrinho
100% de aprovação nos casos executados. Nenhum bug encontrado nesses fluxos durante a sprint.

### ✅ Checkout
Alto índice de aprovação. Um caso foi bloqueado pelo próprio comportamento do sistema (seleção automática de endereço impede testar o cenário sem endereço cadastrado) e um caso permanece pendente de execução.

---

## ✅ Conclusão

A sprint validou com sucesso o fluxo de compra ponta a ponta do Mercado Livre. O módulo de Busca de Produto se destacou como ponto de atenção prioritário para a próxima sprint, concentrando 100% dos defeitos identificados — recomenda-se priorização de correção nesse módulo.

---

> 📁 Para detalhes completos de cada caso de teste, consulte a pasta [`casos-de-teste/`](../casos-de-teste/).
