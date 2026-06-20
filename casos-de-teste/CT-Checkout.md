# ✅ Casos de Teste - Checkout

**Feature:** Checkout  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 12  

---

## Pré-condições
Usuário logado. Produto adicionado ao carrinho. Endereço de entrega cadastrado na conta.

---

## 🟢 Fluxo Positivo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CHECK-001 | Iniciar checkout estando logado | Usuário direcionado para o checkout sem bloqueio; etapas de endereço e pagamento exibidas | ✅ Passou | Usuário direcionado a uma página oferecendo garantia estendida para a compra; opção de continuar sem essa garantia disponível no cabeçalho. Não é bug, é uma nova opção do Meli. |
| CT-CHECK-002 | Selecionar endereço de entrega cadastrado | Endereço selecionado com sucesso; prazo e frete atualizados | ✅ Passou | Além de entrega no endereço, também aparecem opções "Retirar na agência Mercado Livre" e "Retirar com o vendedor" (quando vendedor é da mesma cidade). |
| CT-CHECK-003 | Adicionar novo endereço de entrega no checkout | Novo endereço salvo e selecionado; frete recalculado | ✅ Passou | Novo endereço salvo e selecionado como destino; frete recalculado corretamente. |
| CT-CHECK-004 | Finalizar compra com cartão | Pedido criado; número exibido; e-mail de confirmação enviado | ✅ Passou | Pedido criado com sucesso, número exibido e e-mail de confirmação enviado. |
| CT-CHECK-005 | Finalizar compra com Pix | QR Code e chave Pix gerados; prazo de validade exibido; pedido aguardando pagamento | ✅ Passou | QR Code e chave Pix gerados corretamente; e-mail enviado avisando sobre a espera do pagamento via Pix. |

---

## 🔴 Fluxo Negativo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CHECK-006 | Adicionar produto sem estar logado | Usuário redirecionado para página de login | ✅ Passou | Usuário redirecionado para página de login. |
| CT-CHECK-007 | Tentar avançar no checkout sem selecionar endereço | Sistema bloqueia o avanço; mensagem de validação exibida | 🔒 Bloqueado | Sistema seleciona automaticamente um endereço cadastrado do usuário; não é possível testar o cenário sem endereço por esse comportamento. |
| CT-CHECK-008 | Pagamento recusado por dados de cartão inválidos | Pagamento recusado; mensagem de erro; pedido não criado | ✅ Passou | Sistema bloqueia a confirmação e direciona para página solicitando autorização com o banco; oferece opções de tentar outra forma de pagamento ou reinserir código de segurança. |
| CT-CHECK-009 | Tentar finalizar checkout sem selecionar forma de pagamento | Sistema bloqueia a confirmação; mensagem de validação exibida | 🆕 Novo | Caso de teste a ser executado/validado — ainda não testado em ambiente. |

---

## 🟡 Edge Cases

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-CHECK-010 | Produto esgota durante o checkout | Sistema alerta indisponibilidade; pedido não finalizado | ✅ Passou | Pedido não finalizado; usuário direcionado a página com mensagem informando indisponibilidade do produto. |
| CT-CHECK-011 | Pix não pago dentro do prazo de validade | Pedido cancelado automaticamente; estoque liberado; usuário notificado | ✅ Passou | Pedido cancelado automaticamente após expiração; estoque liberado; usuário notificado por e-mail e notificação do app. |
| CT-CHECK-012 | Voltar ao carrinho durante o checkout e retomar | Informações da compra preservadas; dados de pagamento podem exigir novo preenchimento | ✅ Passou | Produto, endereço e demais informações preservados; dados de pagamento foram removidos e precisaram ser preenchidos novamente. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 10 |
| 🔒 Bloqueado | 1 |
| 🆕 Novo (não executado) | 1 |
| **Total** | **12** |
