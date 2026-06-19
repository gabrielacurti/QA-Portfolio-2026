# ✅ Casos de Teste - Checkout

**Feature:** Checkout  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 9  

---

## Pré-condições
Usuário com produto(s) no carrinho. Endereço de entrega cadastrado. Forma de pagamento válida disponível.

---

## 🟢 Fluxo Positivo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CHECKOUT-001 | Finalizar compra com usuário autenticado | 1. Estar logado com produto no carrinho 2. Acessar checkout 3. Selecionar endereço e forma de pagamento 4. Confirmar compra | Pedido criado com sucesso; tela de confirmação exibida | ✅ Passou | Pedido criado e confirmação exibida com número do pedido. |
| CT-CHECKOUT-002 | Selecionar endereço de entrega cadastrado | 1. Acessar checkout 2. Selecionar endereço já cadastrado | Endereço selecionado exibido corretamente na revisão do pedido | ✅ Passou | Endereço exibido corretamente na etapa de revisão. |
| CT-CHECKOUT-003 | Selecionar forma de pagamento válida | 1. Acessar checkout 2. Selecionar cartão de crédito cadastrado | Forma de pagamento selecionada exibida na revisão do pedido | ✅ Passou | Forma de pagamento exibida corretamente. |
| CT-CHECKOUT-004 | Confirmar pedido com pagamento aprovado | 1. Completar etapas do checkout 2. Confirmar pagamento | Pedido criado; status "Aprovado" exibido | ✅ Passou | Pedido criado com status de pagamento aprovado. |

---

## 🔴 Fluxo Negativo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CHECKOUT-005 | Tentar finalizar checkout sem estar autenticado | 1. Acessar checkout sem login 2. Tentar avançar | Sistema redireciona para tela de login | ✅ Passou | Usuário redirecionado para login antes de continuar. |
| CT-CHECKOUT-006 | Tentar finalizar compra sem selecionar endereço | 1. Acessar checkout sem endereço cadastrado 2. Tentar confirmar pedido | Sistema impede; solicita cadastro de endereço | ✅ Passou | Sistema bloqueou avanço e solicitou endereço. |
| CT-CHECKOUT-007 | Finalizar compra com pagamento recusado | 1. Completar checkout 2. Usar cartão com saldo insuficiente ou recusado pela operadora | Pedido não finalizado; mensagem de pagamento recusado | ✅ Passou | Mensagem de pagamento recusado exibida; pedido não foi criado. |

---

## 🟡 Edge Cases

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-CHECKOUT-008 | Atualizar carrinho durante o checkout (outra aba) | 1. Iniciar checkout em uma aba 2. Em outra aba, remover item do mesmo carrinho 3. Voltar e tentar confirmar pedido | Sistema detecta alteração e atualiza o resumo do pedido antes de confirmar | ✅ Passou | Sistema atualizou o resumo do pedido refletindo a alteração feita na outra aba. |
| CT-CHECKOUT-009 | Tentar finalizar compra com produto que ficou sem estoque durante o checkout | 1. Iniciar checkout com produto em estoque 2. Produto esgota durante o processo (simulado) 3. Tentar confirmar pedido | Sistema informa indisponibilidade antes de concluir a compra | ✅ Passou | Mensagem de indisponibilidade exibida antes da confirmação final. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 9 |
| ❌ Falhou | 0 |
| 🔒 Bloqueado | 0 |
| **Total** | **9** |
