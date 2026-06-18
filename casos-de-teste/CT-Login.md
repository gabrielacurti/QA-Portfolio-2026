# 🔐 Casos de Teste — Login

**Feature:** Login  
**Projeto:** QA Portfolio — Mercado Livre  
**Total de casos:** 14  

---

## Pré-condições
Acessar a página de Login do Mercado Livre.

---

## 🟢 Fluxo Positivo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-LOGIN-001 | Login com e-mail e senha válidos | 1. Clicar em "Entre" no menu topbar 2. Inserir e-mail cadastrado e clicar em "Continuar" 3. Inserir senha correta e clicar em "Continuar" 4. Escanear QR Code com o app 5. Clicar em "Confirmar" | Usuário direcionado para página inicial já logado | ❌ Falhou | Sistema solicitou terceira verificação por reconhecimento facial. Novo CT criado: CT-LOGIN-013 |
| CT-LOGIN-002 | Recuperação de senha com e-mail válido | 1. Clicar em "Esqueceu sua senha?" 2. Inserir e-mail cadastrado e clicar em continuar 3. Clicar em "Enviar" | Mensagem exibida: "Enviar código para recuperação de email" | ❌ Falhou | reCAPTCHA solicitado após inserir o e-mail. Novo CT criado: CT-LOGIN-015 |

---

## 🔴 Fluxo Negativo

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-LOGIN-003 | Login com e-mail não cadastrado | 1. Inserir e-mail não cadastrado 2. Inserir qualquer senha 3. Clicar em "Continuar" | Mensagem de erro indicando que o e-mail não está cadastrado | ❌ Falhou | reCAPTCHA exibido com mensagem: "Verifique o dado ou digite o telefone associado à sua conta". Novo CT criado: CT-LOGIN-014 |
| CT-LOGIN-004 | Login com e-mail válido e senha incorreta | 1. Inserir e-mail cadastrado 2. Inserir senha incorreta 3. Clicar em "Continuar" | Mensagem: "Senha incorreta. Tente novamente." | ❌ Falhou | Sistema exibiu "Revise sua senha" com opção de outro método de acesso. Comportamento correto, mas mensagem diferente da esperada. |
| CT-LOGIN-005 | Login com todos os campos em branco | 1. Deixar campos em branco 2. Clicar em "Continuar" | Botão desabilitado ou mensagem "Campo obrigatório" | ❌ Falhou | ML usa fluxo em duas etapas — e-mail e senha são campos separados. Não é possível deixar ambos em branco simultaneamente. |
| CT-LOGIN-006 | Login com senha em branco | 1. Inserir e-mail válido 2. Deixar senha em branco 3. Clicar em "Continuar" | Mensagem vermelha: "Preencha esse dado" | ✅ Passou | Mensagem exibida corretamente; não é possível continuar sem preencher. |
| CT-LOGIN-007 | Login com e-mail em formato inválido | 1. Inserir texto sem formato de e-mail 2. Clicar em "Continuar" | Mensagem vermelha de validação de formato | ✅ Passou | Mensagem: "Verifique o dado ou digite o telefone associado à sua conta". |
| CT-LOGIN-008 | Recuperação de senha com e-mail não cadastrado | 1. Clicar em "Esqueceu sua senha?" 2. Inserir e-mail não cadastrado 3. Clicar em "Enviar" | Mensagem de confirmação na tela | ❌ Falhou | reCAPTCHA solicitado. Mesmo comportamento do CT-LOGIN-002. |

---

## 🟡 Edge Cases

| ID | Título | Passos | Resultado Esperado | Status | Resultado Encontrado |
|----|--------|--------|--------------------|--------|----------------------|
| CT-LOGIN-009 | Sessão mantida após fechar e reabrir aba | 1. Realizar login 2. Fechar aba 3. Reabrir mercadolivre.com.br | Usuário continua autenticado | ✅ Passou | Usuário continua autenticado; nome exibido no header. |
| CT-LOGIN-010 | Logout e encerramento de sessão | 1. Clicar em "Sair" no menu do usuário 2. Tentar acessar página autenticada | Sessão encerrada; redirecionado para login | ✅ Passou | Usuário redirecionado para tela de login. |
| CT-LOGIN-011 | Login com e-mail em letras maiúsculas | 1. Inserir e-mail em MAIÚSCULAS 2. Inserir senha correta | Login realizado; sistema ignora capitalização | ✅ Passou | Login realizado com sucesso. |
| CT-LOGIN-012 | Login com espaços antes/depois do e-mail | 1. Inserir e-mail com espaço no início ou fim 2. Inserir senha correta | Sistema remove espaços (trim) e realiza login | ✅ Passou | Login realizado com sucesso. |
| CT-LOGIN-013 | Autenticação MFA por reconhecimento facial | 1. Fazer login várias vezes 2. Sistema solicita reconhecimento facial 3. Completar verificação | Usuário direcionado para tela com câmera | ✅ Passou | Sistema aceita verificação e redireciona para home autenticada. |
| CT-LOGIN-014 | reCAPTCHA ao tentar login com e-mail não cadastrado | 1. Inserir e-mail não cadastrado 2. Clicar em "Continuar" 3. Resolver reCAPTCHA | Mensagem de acesso bloqueado | ✅ Passou | Mensagem: "Verifique o dado ou digite o telefone associado à sua conta". |

---

## 📊 Resumo

| Status | Quantidade |
|--------|------------|
| ✅ Passou | 7 |
| ❌ Falhou | 5 |
| 🔒 Bloqueado | 2 |
| **Total** | **14** |
