# 🛒 Casos de Teste - Carrinho

**Feature:** Carrinho  
**Projeto:** QA Portfolio — Mercado Livre  
**Total de casos:** 9  

---

## Pré-condições
Acessar o Mercado Livre. Produto disponível em estoque.

---

## 🟢 Fluxo Positivo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CART-001 | Adicionar produto disponível ao carrinho | 1. Acessar página de produto disponível 2. Clicar em "Adicionar ao carrinho" | Produto adicionado; ícone do carrinho atualizado | ✅ Passou | Produto adicionado corretamente; contador do carrinho atualizado. |
| CT-CART-002 | Aumentar quantidade de um item no carrinho | 1. Acessar carrinho com item adicionado 2. Clicar em "+" na quantidade | Quantidade aumenta; subtotal atualizado automaticamente | ✅ Passou | Quantidade e subtotal atualizados corretamente. |
| CT-CART-003 | Diminuir quantidade de um item no carrinho | 1. Acessar carrinho com item de quantidade >1 2. Clicar em "-" na quantidade | Quantidade diminui; subtotal atualizado automaticamente | ✅ Passou | Quantidade e subtotal atualizados corretamente. |
| CT-CART-004 | Remover produto do carrinho | 1. Acessar carrinho com item adicionado 2. Clicar em "Remover" | Produto removido da lista; total recalculado | ✅ Passou | Produto removido e total atualizado corretamente. |
| CT-CART-005 | Persistência do carrinho ao atualizar a página | 1. Adicionar produto ao carrinho 2. Atualizar a página (F5) | Produto continua no carrinho após o reload | ✅ Passou | Produto permaneceu no carrinho após atualizar a página. |

---

## 🔴 Fluxo Negativo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CART-006 | Adicionar quantidade maior que o estoque disponível | 1. Acessar produto com estoque limitado (ex: 3 unidades) 2. Tentar adicionar quantidade maior (ex: 10) | Sistema impede; exibe mensagem de estoque insuficiente | ✅ Passou | Sistema limitou a quantidade ao estoque disponível e exibiu aviso. |
| CT-CART-007 | Tentar acessar carrinho vazio | 1. Garantir que carrinho está vazio 2. Acessar página do carrinho | Mensagem informando carrinho vazio; sugestão de produtos | ✅ Passou | Mensagem de carrinho vazio exibida com sugestões de produtos. |

---

## 🟡 Edge Cases

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CART-008 | Adicionar o mesmo produto duas vezes | 1. Adicionar produto ao carrinho 2. Voltar à página do produto e adicionar novamente | Sistema soma a quantidade do mesmo item, sem duplicar a linha | ✅ Passou | Quantidade somada corretamente na mesma linha do produto. |
| CT-CART-009 | Calcular subtotal com múltiplos produtos diferentes | 1. Adicionar 2 ou mais produtos diferentes ao carrinho 2. Verificar subtotal de cada item e total geral | Subtotal de cada item e total geral calculados corretamente | ✅ Passou | Valores calculados corretamente para todos os itens. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 9 |
| ❌ Falhou | 0 |
| 🔒 Bloqueado | 0 |
| **Total** | **9** |
