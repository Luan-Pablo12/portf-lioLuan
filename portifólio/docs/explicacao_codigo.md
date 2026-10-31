# 📖 Explicação Resumida dos Códigos

Este documento resume a função de cada trecho de código utilizado no projeto.

---

## 1. `HTML/index.html`

- **`<head>`**:
  - Configurações de viewport para celulares, CDNs do Bootstrap 5, Bootstrap Icons, Google Fonts e folha de estilos `style.css`.

- **`<nav class="navbar ...">`**:
  - Barra de navegação fixa com atalhos para todas as seções: **Sobre mim**, **Projetos**, **ACPs** e **Contato**.

- **`<section id="sobre" class="hero-section">`**:
  - Título com o nome interativo e Bento Grid de 3 cartões sobre formação, hobbies e foco.

- **`<section id="projetos" class="projects-section">`**:
  - Grade com os projetos de **PW1** (Bootstrap) e **ExpoEtec** (Bobina de Tesla com Arduino).

- **`<section id="acps" class="acps-section">`**:
  - Grade `.acp-grid` contendo 3 cartões de cursos e palestras realizadas na escola com empresas.

- **`<section id="contato" class="contact-section">`**:
  - Formulário com campos de **Nome Completo**, **Gmail/E-mail** e **Mensagem**, acompanhado de container `<div id="formStatus">` para mensagens de sucesso/erro sem sair da tela.
  - Card interativo com link e dados do **GitHub** (`https://github.com/Luan-Pablo12`).

- **Importação de Scripts**:
  - Scripts do Bootstrap e lógica interativa em `../JS/script.js`.

---

## 2. `CSS/style.css`

- **Configurações Gerais & Tema Escuro**:
  - Fundo preto absoluto (`#000000`), tipografia `Outfit` e ausência de overflow horizontal.
- **Navbar & Botões**:
  - Botões `.nav-btn-custom` com formato pílula e efeito hover neon verde.
- **Nome & Animações**:
  - Tipografia `Syne` com letras individuais interativas (`.char`) e animação `@keyframes letterJump`.
- **Cartões Bento, Projetos & ACPs**:
  - Efeito *glassmorphism*, bordas translúcidas, ícones estilizados (`.acp-icon`) e elevação com brilho neon no hover.
- **Formulário de Contato & Feedback**:
  - `.form-control-custom`: Campos de entrada escuros com borda verde neon no foco.
  - `.form-status-msg`: Mensagem de confirmação verde ou de erro que surge diretamente dentro do card.
  - `.contact-submit-btn`: Botão com efeito de carregamento e desativação temporária durante o envio.
  - `.github-card`: Card com ícone em destaque e efeito interativo para visitação de perfil.
- **Responsividade (`@media`)**:
  - Reorganização automática para 1 coluna em telas menores e ajuste de padding/fontes.

---

## 3. `JS/script.js`

- **Interatividade das Letras**:
  - Escuta cliques e toques nas letras do nome, disparando animação em cascata (efeito onda).
- **Envio Assíncrono do Formulário (AJAX / Fetch API)**:
  - `e.preventDefault()`: Impede que a página seja recarregada ou redirecionada.
  - Altera o botão para o estado "Enviando..." com spinner.
  - Envia os dados em formato JSON para o endpoint AJAX do FormSubmit (`https://formsubmit.co/ajax/ribeiroaine9@gmail.com`).
  - Em caso de sucesso, limpa os campos (`contactForm.reset()`) e exibe mensagem de confirmação diretamente na página.
