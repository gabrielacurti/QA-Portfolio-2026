# 🐛 BUG-BUSCA-003

**Título:** Busca → Sistema retorna resultados irrelevantes ao buscar apenas caracteres especiais em vez de exibir mensagem de sem resultados

**Prioridade:** 🟠 Média  
**Tipo:** Funcional  
**Ambiente de teste:** Produção · mercadolivre.com.br · Chrome · Windows 11 · São Paulo/SP  
**Caso de Teste relacionado:** CT-BUSCA-008

---

## Passos para reprodução
1. Acessar mercadolivre.com.br
2. Clicar no campo de busca
3. Digitar apenas caracteres especiais (ex: "@ $%&_")
4. Pressionar Enter

## Resultado esperado
Sistema trata a entrada sem erros; exibe mensagem de sem resultados ou sugestões alternativas.

## Resultado encontrado
Sistema retornou +9.999 resultados completamente irrelevantes para o termo. Nenhuma validação ou mensagem de erro exibida.

## Evidência
[Ver evidência](https://drive.google.com/file/d/1qDstRHrUaEaADOlHzza7D26YfsGp4-1a/view?usp=sharing)

## Observação
Mesmo comportamento identificado no BUG-BUSCA-001 — sistema não trata entradas inválidas na busca e retorna resultados irrelevantes como fallback. Padrão de falha recorrente no mecanismo de busca do ML.
