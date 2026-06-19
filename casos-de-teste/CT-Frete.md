# 🚚 Casos de Teste — Frete

**Feature:** Frete  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 9  

---

## Pré-condições
Acessar o Mercado Livre. Produto disponível em estoque. Não é necessário estar logado para calcular frete.

---

## 🟢 Fluxo Positivo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-FRETE-001 | Calcular frete com CEP válido | 1. Acessar página de um produto disponível 2. Inserir CEP válido (ex: 01310-100) 3. Clicar em "Calcular" | Opções de entrega exibidas com modalidade, valor e prazo em dias úteis | ✅ Passou | Página exibiu as duas modalidades de frete e prazos de entrega de ambas. |
| CT-FRETE-002 | Verificar exibição de frete grátis | 1. Buscar produto com tag "Frete grátis" 2. Acessar página do produto 3. Inserir CEP válido e calcular | Frete exibido como R$ 0,00 com destaque visual; prazo informado normalmente | ✅ Passou | Página exibiu prazo de entrega com 2 opções e entrega grátis em ambas. |
| CT-FRETE-003 | Verificar múltiplas opções de entrega | 1. Buscar qualquer produto | Ver todas as opções de frete (Full, Chega hoje, Frete Grátis) | ✅ Passou | Menu lateral exibindo todas as opções de envio do Meli. |
| CT-FRETE-004 | Recalcular frete ao trocar o CEP | 1. Inserir CEP e calcular (ex: SP) 2. Trocar para CEP diferente (ex: RJ) 3. Clicar em "Calcular" novamente | Valores e prazos atualizados automaticamente para o novo CEP | ✅ Passou | Valores e prazos atualizados automaticamente; resultado diferente do primeiro cálculo. |
| CT-FRETE-005 | Produto com entrega a combinar exibe informação correta | 1. Buscar produto de grande porte com "Entrega a combinar" 2. Acessar página do produto 3. Verificar seção de entrega | Sistema exibe "Entrega a combinar com o vendedor"; sem campo de CEP | ✅ Passou | Usuário direcionado a pop-up de perguntas ao vendedor com texto pré-preenchido sobre frete (requer login). |

---

## 🔴 Fluxo Negativo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-FRETE-006 | Calcular frete com CEP inválido | 1. Inserir CEP inválido (ex: 00000-000 ou 1234) 2. Clicar em "Calcular" | Mensagem de erro indicando CEP inválido; nenhum valor calculado | ✅ Passou | Sistema solicita número válido de CEP com 8 caracteres. |
| CT-FRETE-007 | Calcular frete com campo CEP vazio | 1. Deixar campo vazio 2. Clicar em "Calcular" | Botão desabilitado ou mensagem "Informe um CEP" | ✅ Passou | Mensagem em vermelho: "Preencha esse dado". |
| CT-FRETE-008 | Produto com entrega a combinar não exibe valor calculado | 1. Acessar produto com "Entrega a combinar" 2. Verificar campo de CEP ou valor calculado | Nenhum valor de frete exibido; apenas info "a combinar com vendedor" | ✅ Passou | Nenhum valor exibido; apenas informação "a combinar com o vendedor" e link para contato. |

---

## 🟡 Edge Case

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-FRETE-009 | Calcular frete com CEP contendo letras ou caracteres especiais | 1. Inserir valor com letras/caracteres especiais (ex: "ABCDE-FGH") 2. Clicar em "Calcular" | Campo não aceita; ou exibe mensagem de validação | ✅ Passou | Campo não aceita letras ou caracteres especiais; sistema pede apenas números. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 9 |
| ❌ Falhou | 0 |
| 🔒 Bloqueado | 0 |
| **Total** | **9** |
