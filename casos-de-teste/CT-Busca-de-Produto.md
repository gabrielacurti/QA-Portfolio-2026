# 🔍 Casos de Teste - Busca de Produto

**Feature:** Busca de Produto  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 10  

---

## Pré-condições
Acessar a página do Mercado Livre. Não é necessário estar logado para buscar.

---

## 🟢 Fluxo Positivo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-BUSCA-001 | Busca com termo válido e existente | Lista de produtos exibida com título, preço e imagem | ✅ Passou | 532 resultados para "iphone 15". Sistema exibiu banner de revendedor autorizado Apple no topo, comportamento adicional não mapeado no resultado esperado. |
| CT-BUSCA-002 | Ordenar resultados por menor preço | Produtos reordenados do menor para o maior preço | ✅ Passou | Produtos reordenados corretamente; primeiro item por R$ 2,00. Banner de revendedor JBL exibido no topo — itens patrocinados não seguem a ordenação, apenas os resultados orgânicos abaixo do banner. |
| CT-BUSCA-003 | Filtrar resultados por categoria | Apenas produtos da categoria selecionada exibidos; total reduz | ✅ Passou | Apenas produtos da marca DELL exibidos; total de resultados reduzido. |
| CT-BUSCA-004 | Filtrar resultados por faixa de preço | Todos os produtos dentro da faixa definida | ✅ Passou | Todos os produtos exibidos dentro da faixa de preço definida; nenhum item fora do intervalo. |

---

## 🔴 Fluxo Negativo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-BUSCA-005 | Busca com termo inexistente | Mensagem informando que não há resultados; sugestões alternativas | ❌ Falhou | Sistema retornou 50 resultados de anúncios de serviços com títulos aleatórios não relacionados ao termo. Nenhuma mensagem de "sem resultados" exibida. 🐛 BUG-BUSCA-001 |
| CT-BUSCA-006 | Busca com campo vazio | Sistema não realiza busca; botão desabilitado ou página não muda | ✅ Passou | Sistema não realizou busca vazia; comportamento esperado confirmado. |
| CT-BUSCA-007 | Filtro de faixa de preço com valor mínimo maior que máximo | Mensagem de validação ou impedimento do filtro inválido | ❌ Falhou | Sistema aceitou a faixa invertida e retornou 1.509 resultados. Produtos fora da faixa apareceram nos resultados. Nenhuma mensagem de validação exibida. 🐛 BUG-BUSCA-002 |

---

## 🟡 Edge Cases

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-BUSCA-008 | Busca com caracteres especiais | Sistema trata entrada sem erros; mensagem de sem resultados ou sugestões | ❌ Falhou | ML interpretou caracteres especiais como termo válido e retornou produtos não relacionados (sapatilhas, leggings, tecidos). Nenhuma mensagem de erro exibida. 🐛 BUG-BUSCA-003 |
| CT-BUSCA-009 | Busca com termo em letras maiúsculas | Mesmos resultados de uma busca em minúsculas | ✅ Passou | Página de Televisões Samsung exibida normalmente. |
| CT-BUSCA-010 | Aplicar múltiplos filtros simultaneamente | Produtos respeitam todos os filtros aplicados simultaneamente | ✅ Passou | Página de celulares de diversas marcas e lojas de São Paulo exibida corretamente. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 7 |
| ❌ Falhou | 3 |
| 🔒 Bloqueado | 0 |
| **Total** | **10** |
