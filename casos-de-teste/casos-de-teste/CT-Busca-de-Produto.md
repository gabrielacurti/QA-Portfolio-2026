# 🔍 Casos de Teste — Busca de Produto

**Feature:** Busca de Produto  
**Projeto:** QA Portfolio — Mercado Livre  
**Total de casos:** 10  

---

## Pré-condições
Acessar a página do Mercado Livre. Não é necessário estar logado para buscar.

---

## 🟢 Fluxo Positivo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-BUSCA-001 | Busca com termo válido e existente | 1. Clicar no campo de busca 2. Digitar termo existente (ex: "iphone 15") 3. Pressionar Enter | Lista de produtos com título, preço e imagem exibida | ✅ Passou | Lista exibida corretamente. 532 resultados. Sistema exibiu banner de revendedor autorizado Apple não mapeado no resultado esperado. |
| CT-BUSCA-002 | Ordenar resultados por menor preço | 1. Buscar termo válido (ex: "fone de ouvido") 2. Selecionar ordenação "Menor preço" 3. Verificar ordem dos produtos | Produtos reordenados do menor para o maior preço | ✅ Passou parcialmente | Produtos reordenados por menor preço. Banner de revendedor JBL exibido no topo — itens patrocinados não seguem a ordenação. |
| CT-BUSCA-003 | Filtrar resultados por categoria | 1. Buscar termo amplo (ex: "notebook") 2. Selecionar categoria (ex: "Marca") 3. Verificar produtos exibidos | Apenas produtos da categoria selecionada; total de resultados reduz | ✅ Passou | Apenas produtos da marca DELL exibidos; total de resultados reduzido. |
| CT-BUSCA-004 | Filtrar resultados por faixa de preço | 1. Buscar termo válido (ex: "cadeira gamer") 2. Definir faixa de preço (ex: R$ 500 a R$ 1.000) 3. Verificar produtos exibidos | Todos os produtos dentro da faixa definida | ✅ Passou | Todos os produtos exibidos dentro da faixa de preço definida. |

---

## 🔴 Fluxo Negativo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-BUSCA-005 | Busca com termo inexistente | 1. Digitar termo sem resultados (ex: "xyzabcqwerty123") 2. Pressionar Enter | Mensagem informando que não há resultados; sugestões alternativas | ❌ Falhou | Sistema retornou 50 resultados de anúncios de serviços com títulos aleatórios não relacionados ao termo. Nenhuma mensagem de "sem resultados" exibida. 🐛 BUG-BUSCA-001 |
| CT-BUSCA-006 | Busca com campo vazio | 1. Deixar campo de busca vazio 2. Clicar no botão de busca | Sistema não realiza busca; botão desabilitado ou página não muda | ✅ Passou | Sistema não realizou busca vazia. |
| CT-BUSCA-007 | Filtro de faixa de preço com valor mínimo maior que máximo | 1. Buscar termo válido 2. Inserir valor mínimo maior que máximo (ex: mín R$ 1.900 / máx R$ 1.500) 3. Confirmar filtro | Mensagem de validação ou impedimento do filtro inválido | ❌ Falhou | Sistema aceitou a faixa invertida e retornou 1.509 resultados. Produtos fora da faixa apareceram nos resultados. Nenhuma mensagem de validação exibida. 🐛 BUG-BUSCA-002 |

---

## 🟡 Edge Cases

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-BUSCA-008 | Busca com caracteres especiais | 1. Digitar apenas caracteres especiais (ex: "@#$%&*") 2. Pressionar Enter | Sistema trata entrada sem erros; exibe mensagem de sem resultados ou sugestões | ❌ Falhou | ML retornou produtos completamente não relacionados. Nenhuma mensagem de erro exibida. Mesmo padrão do BUG-BUSCA-001. 🐛 BUG-BUSCA-003 |
| CT-BUSCA-009 | Busca com termo em letras maiúsculas | 1. Digitar termo em MAIÚSCULAS (ex: "TELEVISÃO SAMSUNG") 2. Pressionar Enter | Mesmos resultados de uma busca em minúsculas | ✅ Passou | Página de Televisões Samsung exibida normalmente. |
| CT-BUSCA-010 | Aplicar múltiplos filtros simultaneamente | 1. Buscar "smartphone" 2. Aplicar filtro de categoria 3. Aplicar filtro de faixa de preço 4. Aplicar filtro de localização 5. Verificar resultados | Produtos respeitam todos os filtros aplicados simultaneamente | ✅ Passou | Página de celulares de diversas marcas de lojas de São Paulo exibida corretamente. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 6 |
| ❌ Falhou | 3 |
| 🔒 Bloqueado | 0 |
| **Total** | **10** |
