# Guia de Configuração do Firebase

Para que os arquivos sejam salvos na nuvem e acessíveis de qualquer computador, você precisa criar um projeto gratuito no Google Firebase.

## Passo 1: Criar o Projeto
1. Acesse [console.firebase.google.com](https://console.firebase.google.com) usando sua conta Google.
2. Clique em **"Adicionar projeto"** (ou "Create a project").
3. Dê um nome ao projeto (ex: `GeradorPlanoTrabalho`).
4. Desative o Google Analytics (não é necessário agora) e clique em **"Criar projeto"**.

## Passo 2: Configurar o Banco de Dados (Firestore)
1. No menu lateral esquerdo, clique em **Build** (Criação) > **Firestore Database**.
2. Clique em **"Criar banco de dados"**.
3. Escolha um local (ex: `nam5 (us-central)` ou `sao-paulo` se disponível).
4. **IMPORTANTE:** Na etapa "Regras de segurança", escolha **"Iniciar no modo de teste"** (Start in test mode) para começar rapidamente.
   * *Nota: Em produção real, configuraríamos regras mais estritas.*

## Passo 3: Configurar o Login (Authentication)
1. No menu lateral, clique em **Build** > **Authentication**.
2. Clique em **"Vamos começar"**.
3. Na aba **Sign-in method**, clique em **Google**.
4. Ative o interruptor **Enable**.
5. Configure o nome do suporte e escolha seu email. Clique em **Salvar**.

## Passo 4: Obter as Chaves (Config)
1. Clique na engrenagem ⚙️ no topo do menu lateral esquerdo.
2. No menu que abrir, clique em **"Geral"**.
3. Role a página até o final, onde diz **"Seus aplicativos"** (Your apps).
4. Se não houver app, clique no ícone **Web** (`</>`).
4. Dê um apelido para o app (ex: `Web App`) e clique em **Registrar app**.
5. Vai aparecer um código com `const firebaseConfig = { ... }`.
6. **COPIE** o conteúdo dentro das chaves `{ ... }` (apiKey, authDomain, etc).

## Passo 5: Colar no Código
1. Abra o arquivo `index.html`.
2. Procure por `// SUBSTITUA COM SUAS CHAVES DO FIREBASE AQUI`.
3. Substitua os valores placeholder pelos que você copiou.

## Passo 6: Autorizar Domínios (IMPORTANTE)
Se você viu um erro **"This domain is not authorized"**, é porque o Firebase bloqueia sites desconhecidos por segurança.

1. No Console do Firebase, vá em **Authentication** > **Configurações** (Settings).
2. Clique na aba **"Domínios autorizados"**.
3. Clique em **"Adicionar domínio"**.
4. Adicione o domínio que você está usando acessar o site.
   - Se estiver usando "Live Server" do VS Code, geralmente é `127.0.0.1`.
   - Se estiver rodando um servidor local, adicione `localhost`.
   - Se publicou no Netlify/Vercel, adicione o domínio do site (ex: `meusite.netlify.app`).

> [!WARNING]
> **Atenção:** O login com Google **NÃO FUNCIONA** se você apenas der dois cliques no arquivo `index.html` (o endereço começa com `file://`).
> Você precisa rodar um servidor local. Se tiver o VS Code, instale a extensão **Live Server** e clique em "Go Live".

