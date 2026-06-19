# 🐛 BUG-BUSCA-002

**Título:** Busca → Sistema aceita filtro de faixa de preço com valor mínimo maior que o máximo e exibe produtos fora da faixa definida

**Prioridade:** 🟠 Média  
**Tipo:** Funcional  
**Ambiente de teste:** Produção · mercadolivre.com.br · Chrome · Windows 11 · São Paulo/SP  
**Caso de Teste relacionado:** CT-BUSCA-005 — Busca com termo inexistente · Passo 5.3

---

## Passos para reprodução
1. Acessar mercadolivre.com.br
2. Buscar por termo válido (ex: "notebook")
3. Localizar o filtro de faixa de preço no painel lateral
4. Inserir valor mínimo maior que o máximo (ex: mín R$ 1.500 / máx R$ 1.900, invertido intencionalmente)
5. Confirmar o filtro
6. Verificar os resultados exibidos e os valores dos produtos

## Resultado esperado
Sistema exibe mensagem de validação informando que o valor mínimo não pode ser maior que o máximo; filtro não é aplicado.

## Resultado encontrado
Sistema aceitou a faixa de preço invertida sem exibir nenhuma mensagem de validação e retornou 1.509 resultados. Produtos fora da faixa definida foram exibidos nos resultados (ex: R$ 2.199,99 e R$ 2.499,99 apareceram nos resultados de uma busca com máximo de R$ 1.900).

## Evidência
[Ver evidência](https://drive.google.com/file/d/1g9zVbAnpOchGtXeaAomIYbPjLVp2l4ov/view?usp=sharing)

## Observação
Bug duplo identificado: (1) sistema não valida faixa de preço invertida e (2) produtos fora da faixa definida aparecem nos resultados. Ambos os comportamentos prejudicam a experiência do usuário e a confiabilidade do filtro de preço.
