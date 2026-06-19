# 🐛 BUG-BUSCA-001

**Título:** Busca → Mercado Livre retorna resultados irrelevantes ao buscar termo inexistente em vez de exibir mensagem de sem resultados

**Prioridade:** 🔴 Alta  
**Tipo:** Funcional  
**Ambiente de teste:** Produção · mercadolivre.com.br · Chrome · Windows 11 · São Paulo/SP  
**Caso de Teste relacionado:** CT-BUSCA-005 — Busca com termo inexistente · Passo 5.3

---

## Passos para reprodução
1. Acessar mercadolivre.com.br
2. Clicar no campo de busca
3. Digitar termo inexistente (ex: "xyzabcqwerty123")
4. Pressionar Enter ou clicar no botão de busca

## Resultado esperado
Sistema exibe mensagem informando que não há resultados para o termo pesquisado e sugere alternativas de busca.

## Resultado encontrado
Sistema retornou 50 resultados de anúncios de serviços com títulos aleatórios não relacionados ao termo buscado (ex: "Teste", "Teste Teste", "Bfhjjhffg"). Nenhuma mensagem de "sem resultados" foi exibida.

## Evidência
[Ver evidência](https://drive.google.com/file/d/16ObcmETakVlATfTqmgbJcRn393_MvQ4v/view?usp=sharing)

## Observação
O ML aparentemente utiliza anúncios de serviços como fallback quando não encontra produtos correspondentes ao termo buscado. Comportamento pode confundir o usuário e prejudica a experiência de busca.

