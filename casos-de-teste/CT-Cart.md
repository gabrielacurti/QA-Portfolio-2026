# 🛒 Casos de Teste - Carrinho

**Feature:** Carrinho  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 11  

---

## Pré-condições
Acessar o Mercado Livre. Usuário logado. Produto com estoque disponível.

---

## 🟢 Fluxo Positivo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CART-001 | Adicionar produto disponível ao carrinho | Produto adicionado; contador do carrinho atualiza; subtotal calculado corretamente | ✅ Passou | Drawer lateral exibido imediatamente após inclusão; produto recém-adicionado aparece no topo; usuário pode continuar comprando ou acessar o carrinho. |
| CT-CART-002 | Aumentar quantidade de um item no carrinho | Quantidade atualizada; subtotal, frete e total recalculados automaticamente | ✅ Passou | Quantidade, subtotal, frete e total recalculados automaticamente. |
| CT-CART-003 | Diminuir quantidade de um item no carrinho | Quantidade reduzida em 1; valores recalculados corretamente | ✅ Passou | Quantidade reduzida em 1; valores recalculados corretamente. |
| CT-CART-004 | Remover produto do carrinho | Item removido; total atualizado; mensagem de carrinho vazio se aplicável | ✅ Passou | Item removido sem modal de confirmação; total atualizado; mensagem "Seu carrinho está vazio" exibida quando aplicável. |
| CT-CART-005 | Carrinho persiste após atualizar a página | Produto continua no carrinho com quantidade e valores preservados | ✅ Passou | Produto continuou no carrinho com quantidade e valores preservados após F5. |

---

## 🔴 Fluxo Negativo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CART-006 | Tentar adicionar produto sem estoque | Botão desabilitado ou ausente; mensagem "Produto indisponível" exibida | ✅ Passou | Botão ausente para compra; mensagem "Produto está indisponível no momento" exibida. |
| CT-CART-007 | Tentar aumentar quantidade além do estoque disponível | Botão "+" desabilitado ao atingir o limite; mensagem de estoque máximo | ✅ Passou | Botão "+" desabilitado ao atingir o limite; porém não exibe mensagem indicando estoque máximo atingido. |
| CT-CART-008 | Tentar diminuir quantidade abaixo de 1 pelo "−" | Sistema não permite quantidade 0; ou exibe confirmação de remoção | ✅ Passou | Sistema não permite quantidade 0 pelo "−"; mínimo é 1 produto, redução abaixo disso só pela remoção via lixeira. |
| CT-CART-009 | Verificar cálculo do total após alterar quantidade | Subtotal = preço × quantidade; total = subtotal + frete | ✅ Passou | Valores batem com o cálculo manual; subtotal e total corretos. |

---

## 🟡 Edge Cases

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CART-010 | Carrinho persiste após logout e novo login | Produto ainda presente no carrinho; persistência vinculada à conta | ✅ Passou | Produto continua presente no carrinho com a mesma quantidade adicionada. |
| CT-CART-011 | Produto no carrinho fica sem estoque antes do checkout | Sistema alerta indisponibilidade e impede finalização da compra | ✅ Passou | Produto e foto exibidos com opacidade reduzida; sistema alerta indisponibilidade e impede finalização da compra. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 11 |
| ❌ Falhou | 0 |
| 🔒 Bloqueado | 0 |
| **Total** | **11** |
