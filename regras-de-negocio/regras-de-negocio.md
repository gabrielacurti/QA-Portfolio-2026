# 📋 Regras de Negócio - Mercado Livre

Levantamento das regras de negócio mapeadas antes da execução dos testes, cobrindo as principais funcionalidades do fluxo de compra do Mercado Livre.

---

## 🔐 Login

| Regra | Descrição |
|-------|-----------|
| Login Válido | Usuário deve conseguir acessar a conta com e-mail e senha válidos. |
| Login Inválido | Sistema deve impedir acesso com credenciais incorretas. |
| Campos Obrigatórios | E-mail e senha devem ser obrigatórios. |
| Recuperação de Senha | Usuário deve conseguir redefinir a senha via e-mail. |
| Sessão | Usuário permanece logado até logout. |

---

## 🔍 Busca de Produtos

| Regra | Descrição |
|-------|-----------|
| Busca por Palavra-chave | Sistema deve retornar produtos relacionados ao termo pesquisado. |
| Produto Inexistente | Sistema deve informar quando não houver resultados. |
| Ordenação | Usuário pode ordenar por: menor preço, maior preço ou relevância. |
| Filtros | Sistema deve permitir filtros por: categoria, faixa de preço, frete e localização. |
| Performance | Busca deve retornar resultados em tempo aceitável. |

---

## 🛒 Carrinho

| Regra | Descrição |
|-------|-----------|
| Adicionar Produtos | Usuário pode adicionar produtos disponíveis ao carrinho. |
| Controle de Estoque | Quantidade adicionada não pode ultrapassar o estoque disponível. |
| Atualização de Quantidade | Usuário pode aumentar ou diminuir quantidade. |
| Remoção | Usuário pode remover produtos do carrinho. |
| Persistência | Produtos permanecem no carrinho mesmo após atualizar a página. |
| Cálculo | Carrinho deve atualizar automaticamente: subtotal, frete e total da compra. |

---

## 🚚 Frete

| Regra | Descrição |
|-------|-----------|
| Cálculo por CEP | O valor e prazo do frete devem ser calculados com base no CEP de destino. CEPs inválidos ou inexistentes não devem gerar cálculo. |
| Frete Grátis | Quando disponível, deve ser exibido com destaque e o valor deve aparecer como R$ 0,00. |
| Múltiplas Opções de Entrega | O sistema deve exibir as opções disponíveis para o CEP informado (ex: Sedex, PAC, Mercado Envios Full, Mercado Envios Flex), com valor e prazo estimado. |
| Prazo Estimado | O prazo de entrega deve variar de acordo com o CEP, a modalidade escolhida e a localização do vendedor. Deve ser exibido em dias úteis. |
| CEP de Área Remota | Para CEPs remotos, o sistema deve informar restrição de entrega ou exibir prazo e valor diferenciados. |
| Produto sem Frete Disponível | Se nenhuma modalidade estiver disponível para o CEP, o sistema deve informar que a entrega não está disponível. |
| Peso e Dimensão | O valor do frete deve considerar o peso e as dimensões do produto. Produtos de grande porte podem ter restrições ou valor diferenciado. |
| Retirada na Agência | O sistema deve exibir a opção de retirada em agência dos Correios quando disponível. |
| Entrega a Combinar | Quando aplicável, não há cálculo automático de frete — o comprador deve entrar em contato com o vendedor para definir forma e valor da entrega. |
| Atualização ao Trocar CEP | Ao alterar o CEP, o sistema deve recalcular automaticamente o frete e atualizar as opções sem recarregar a página. |

---

## ✅ Checkout

| Regra | Descrição |
|-------|-----------|
| Usuário Autenticado | Checkout só pode ser concluído com usuário logado. |
| Endereço Obrigatório | Usuário deve selecionar endereço de entrega. |
| Forma de Pagamento | Sistema deve aceitar métodos válidos de pagamento. |
| Pagamento Recusado | Compra não deve ser finalizada em caso de falha no pagamento. |
| Confirmação | Pedido deve ser criado após pagamento aprovado. |
