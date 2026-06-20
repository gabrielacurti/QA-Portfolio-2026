# 🔐 Casos de Teste - Login

**Feature:** Login  
**Projeto:** QA Portfolio - Mercado Livre  
**Total de casos:** 14  

---

## Pré-condições
Acessar a página de Login do Mercado Livre.

---

## 🟢 Fluxo Positivo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-LOGIN-001 | Login com e-mail e senha válidos | Usuário direcionado para página inicial já logado | ❌ Falhou | Sistema solicitou terceira verificação por reconhecimento facial. Novo CT criado: CT-LOGIN-013 |
| CT-LOGIN-002 | Recuperação de senha com e-mail válido | Usuário redirecionado para página de informar e-mail cadastrado | ❌ Falhou | reCAPTCHA solicitado após inserir o e-mail, impedindo seguir sem completar a verificação. |

---

## 🔴 Fluxo Negativo

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-LOGIN-003 | Login com e-mail não cadastrado | Mensagem de erro indicando e-mail não cadastrado; acesso bloqueado | ❌ Falhou | reCAPTCHA exibido; mensagem: "Verifique o dado ou digite o telefone associado à sua conta". Novo CT criado: CT-LOGIN-014 |
| CT-LOGIN-004 | Login com e-mail válido e senha incorreta | Mensagem: "Senha incorreta. Tente novamente."; login não realizado | ❌ Falhou | Sistema exibiu "Revise sua senha" com opção de outro método de acesso. Mensagem diferente da esperada, mas comportamento correto (acesso bloqueado). |
| CT-LOGIN-005 | Login com todos os campos em branco | Botão desabilitado ou mensagens "Campo obrigatório" em ambos campos | ❌ Falhou | Sistema usa fluxo em duas etapas (e-mail e senha são telas separadas). Ao avançar sem preencher, exibe "Preencha esse dado" apenas no campo visível. Pré-condição do CT precisa revisão. |
| CT-LOGIN-006 | Login com senha em branco | Mensagem vermelha "Preencha esse dado" abaixo do campo de senha | ✅ Passou | Mensagem exibida corretamente; não é possível continuar sem preencher. |
| CT-LOGIN-007 | Login com e-mail em formato inválido | Mensagem vermelha de validação de formato; não avança | ✅ Passou | Mensagem: "Verifique o dado ou digite o telefone associado à sua conta". |
| CT-LOGIN-008 | Recuperação de senha com e-mail não cadastrado | Mensagem de confirmação na tela; e-mail de redefinição recebido | ❌ Falhou | reCAPTCHA solicitado, impedindo seguir. Mesmo comportamento do CT-LOGIN-002. |

---

## 🟡 Edge Cases

| ID | Título | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|---------------------|--------|------------------------|
| CT-LOGIN-009 | Sessão mantida após fechar e reabrir aba | Usuário continua autenticado; nome exibido no header | ✅ Passou | Usuário continua autenticado; nome exibido no header sem solicitar novo login. |
| CT-LOGIN-010 | Logout e encerramento de sessão | Sessão encerrada; redirecionado para login ao acessar área restrita | ✅ Passou | Usuário redirecionado para tela de login ao tentar acessar área restrita. |
| CT-LOGIN-011 | Login com e-mail em letras maiúsculas | Login realizado; sistema ignora capitalização | ✅ Passou | Login realizado com sucesso. |
| CT-LOGIN-012 | Login com espaços antes/depois do e-mail | Sistema remove espaços (trim) e realiza login | ✅ Passou | Login realizado com sucesso. |
| CT-LOGIN-013 | Validar comportamento quando sistema solicita MFA por reconhecimento facial | Usuário direcionado para tela com câmera; verificação aceita | ✅ Passou | Sistema aceita a verificação e redireciona para a home autenticada. |
| CT-LOGIN-014 | Validar comportamento quando sistema exibe reCAPTCHA com e-mail não cadastrado | Mensagem de acesso bloqueado após reCAPTCHA | ✅ Passou | Mensagem exibida: "Verifique o dado ou digite o telefone associado à sua conta"; acesso bloqueado sem avançar para etapa de senha. |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 8 |
| ❌ Falhou | 6 |
| 🔒 Bloqueado | 0 |
| **Total** | **14** |
